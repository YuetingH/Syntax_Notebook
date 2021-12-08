# Julia Syntax

</br>

## REPL

</br>

**Open Julia**: 
Open terminal, input '~/Julia/choose_version/bin/julia`

Notice that there are four modes in Julia. The default mode is Julia Mode. When you enter into other mode and you want to get out of it, press backspace at the beginning of the line.

- **The Julian Mode[Default]**

    Each new line initially starts with julia>. It is here that you can enter Julia expressions. Hitting return or enter after a complete expression has been entered will evaluate the entry and show the result of the last expression.

    ```Julia
    julia> string(1 + 2)
    "3"
    ```
- **Help Mode**

    When the cursor is at the beginning of the line, the prompt can be changed to a help mode by typing ?. Julia will attempt to print help or documentation for anything entered in help mode:

    ```julia
    julia> ? # upon typing ?, the prompt changes (in place) to: help?>

    help?> string
    search: string String Cstring Cwstring RevString randstring bytestring SubString

    string(xs...)

    Create a string from any values using the print function.
    ...
    ```
- **Shell Mode**

    Common task is to use the system shell to execute system commands. Just as ? entered help mode when at the beginning of the line, a semicolon (;) will enter the shell mode.

    ```julia
    shell> ls
    bin  etc  include  lib	LICENSE.md  share
    ```

- **Package Mode**
    
    Pkg is designed around “environments”: independent sets of packages that can be local to an individual project or shared and selected by name.

    The Package manager mode accepts specialized commands for loading and updating packages. It is entered by pressing the ].
    ```julia
    # add package
    # It is possible to add multiple packages in one command as pkg> add A B C.
    (v1.0) pkg> add package_name

    # remove package
    (v1.0) pkg> rm package_name

    # update package
    (v1.0) pkg> up package_name

    # check installed packages
    (v1.0) pkg> st

    # Update all installed packages
    (v1.0) pkg> update
    ```

    - **Package management in Jupter Notebook**
        ```julia
        using Pkg
        Pkg.add("Packagename")
        Pkg.rm("Packagename")
        Pkg.update("Packagename")
        Pkg.status()
        Pkg.update()
        ```
  
</br>

---

</br>

## Environment Setting

</br>

### **Create a project with its own environment**
```julia
# Create a new folder

# This will create a new folder in ~/Julia/choose_version
julia> mkdir("MyProject")
julia> cd("MyProject")

# We can also create a new folder in some other location
shell> cd ~/Documents/MA934
shell> mkdir MyProject



# Make this folder a Julia project
# This step will generate two files named Manifest.toml and Project.toml
(v1.0) pkg> activate .

(MyProject) pkg> st
    Status `~/Julia/julia-1.0.5/MyProject/Project.toml`
  (empty environment)
```

### **Introduction of Manifest.toml and Project.toml**

- Project.toml
  
    All dependencies of the package/project installed by the author are listed in the [deps] section. Each dependency is listed as a name-uuid pair, for example:

    Notice that uuid means universally unique identifier for the package/project.
    ```julia
    [deps]
    BenchmarkTools = "6e4b80f9-dd63-53aa-95a3-0cdb28fa8baf"
    DifferentialEquations = "0c46a032-eb83-5123-abaf-570d42b7fbaa"
    Distributions = "31c24e10-a181-5473-b8eb-7969acd0382f"
    DualNumbers = "fa6b7ba4-c1ee-5f82-b5fc-ecf0adba8f74"
    FFTW = "7a1cc6ca-52ef-59f5-83cd-3a7055c09341"
    GLPK = "60bf3e95-4087-53dc-ae20-288a0d20c6a6"
    JuMP = "4076af6c-e467-56ae-b986-b466b2749572"
    LaTeXStrings = "b964fa9f-0449-5b57-a5c2-d3ea65f4040f"
    LinearAlgebra = "37e2e46d-f89d-539d-b4ee-838fcccc9c8e"
    Plots = "91a5bcdd-55d7-5caf-9e0b-520d859cae80"
    Printf = "de0858da-6303-5e67-8744-51eddeeeb8d7"
    PyPlot = "d330b81b-6aea-500a-939a-2ce795aea3ee"
    Random = "9a3f8284-a2c9-5f02-9a11-845980a1fd5c"
    Revise = "295af30f-e4ad-537b-8983-00126c2a3abe"
    ```

- Manifest.toml
  
    Each dependency has its own section in the manifest file, and its content varies depending on how the dependency was added to the environment. 
    
    It contains more detailed information about dependencies than Project.toml. Because it may contain information about the dependencies of some dependencies.

    Every dependency section includes a combination of the following entries:

    - deps: a vector listing the dependencies of the dependency, for example deps = ["Example", "JSON"].

    - git-tree-sha1: a content hash of the source tree, for example git-tree-sha1 = "ca3820cc4e66f473467d912c4b2b3ae5dc968444".

    - uuid: the UUID for the dependency, for example uuid = "7876af07-990d-54b4-ab0e-23690620f79a".
  
    - version: a version number, for example version = "1.2.6".

    For example,
    ```julia
    [[IJulia]]
    deps = ["Base64", "Conda", "Dates", "InteractiveUtils", "JSON", "Libdl", "Markdown", "MbedTLS", "Pkg", "Printf", "REPL", "Random", "SoftGlobalScope", "Test", "UUIDs", "ZMQ"]
    git-tree-sha1 = "d8b9c31196e1dd92181cd0f5760ca2d2ffb4ac0f"
    uuid = "7073ff75-c697-5162-941a-fcdaad2a7d2a"
    version = "1.23.2"
    ```


### **Using someone else's project**
- Operate in Julia directly
    ```julia
    (v1.0) pkg> activate .

    (SomeProject) pkg> instantiate
    ```
- Operate in Jupyter Notebook
    ```julia
    # Recreate environment
    using Pkg
    Pkg.activate(".")
    Pkg.instantiate()

    # Since we will be loading external files containing Julia code, we need to tell Julia to add the current directory to its search path. Here's how to do that:

    push!(LOAD_PATH, pwd())
    ``` 
</br>

---

</br>

## Project Structure

</br>

To make the project more organized, the list of files contained in this project folder is usually like:

```
- Assignment.ipynb              # set environment and execute main.jl
- main.jl                       # code where functions in MyModule are used
- MyModule.toml                 # code containing a list of functions 

- Project.toml                  # File generated by system to set environment
- Manifest.toml                 # File generated by system to set environment
```


### **Construct Module for Funtions**

- Module Itself: MyModule.jl
    ```julia
    module MyModule # module name
    
    export example_plot 

    function example_plot(n)
    ...
    end


    function another_example_plot(n)
    ...
    end 

    end # End the module definition
    ```

- Using Module: main.jl
  - Method 1 
    ```julia
    include("MyModule.jl")      # More like just run the code in the file

    p = MyModule.example_plot(n)    # Use any function in ths module with MyModule.function
    ```

  - Method 2 
    ```julia
    include("MyModule.jl")
    using .MyModule

    p = example_plot(n)         # Use any function that is exported in ths module directly

    # P = another_example_plot(n) won't work
    ```

</br>

### **Include Functions**
- Module: StructuralRecursion.jl
  
  ```julia
  module StructuralRecursion

  # Include the files containing the code for various functions operating on these data types
  include(joinpath("functions", "LinkedList.jl")) # joinpath("Folder","file.jl")

  end
  ```
- Function: functions/LinkedList.jl
  
  ```julia
  # Define list type
  mutable struct LinkedList
      data::KeyValuePair
      next::Union{LinkedList,Nothing}
  end

  # Prepend data to list
  function prepend(list::Union{LinkedList,Nothing}, data::KeyValuePair) 
      new = LinkedList(data, Nothing())
      new.next = list
      return new
  end
  ```

</br>

### **Create Packages**

- Julia: How to Create a Package?
    ```julia
    (worksheet-3-not-assessed-YuetingH) pkg> generate HelloWorld         # 'HelloWorld' is a package name

    # Check structure
    shell> tree .
        .
        ├── Project.toml
        └── src
            └── HelloWorld.jl

        1 directory, 2 files

    # Get into the environment
    (worksheet-3-not-assessed-YuetingH) pkg> activate HelloWorld
    
    (HelloWorld) pkg> build

    # Add package into the project 
    (worksheet-3-not-assessed-YuetingH) pkg> dev /home/han/Documents/MA934/worksheet-3-not-assessed-YuetingH/StructuralRecursion
    ```

</br>
  
### **Set Environment and Execute Code: Assignment.ipynb**
```julia
# Recreate environment
using Pkg
Pkg.activate(".")
Pkg.instantiate()

# Since we will be loading external files containing Julia code, we need to tell Julia to add the current directory to its search path. Here's how to do that:
push!(LOAD_PATH, pwd())

# Execute code
include("main.jl")
```

</br>

---

</br>

## Packages

</br>

### **How to use packages**
- Using Packages: `Using packagename`

    Notice that functions in package will not need to be used like package.function(). We only need to mention function directly.

</br>

### **Plot Package**
**Plots is a visualization interface and toolset. It sits above other backends, like GR, PyPlot, PGFPlotsX, or Plotly, connecting commands with implementation.** If one backend does not support your desired features or make the right trade-offs, you can just switch to another backend with one command. No need to change your code. No need to learn a new syntax. 

```julia
# Once Plot and certain backend are installed in your project environment, then we can use them in the following way.
using Plots

# Use the pyplot backend
pyplot()




# Basic Concept
plot(args...; kw...)                  # creates a new Plot, and set it to be the `current`
plot!(args...; kw...)                 # modifies Plot `current()`
plot!(plt, args...; kw...)            # modifies Plot `plt`



# Scatter Plot & line Plot
function example_plot(n)
    title = "This is an example plot."
    x1 = collect(range(0.0, 2*π, length=n))
    y1 = sin.(x1)

    # Scatterplot
    p = plot(x1, y1, seriestype=:scatter,label="Some sample points",
    title=title, xlabel="x", ylabel="sin(x)", markersize=10, markercolor="red")

    # Now plot the true function

    # collect(collection): Return an Array of all items in a collection or iterator. For dictionaries,returns Pair{KeyType, ValType}. 
    x2 = collect(range(0.0, 2*π, length=1000))  # return an array equally splited from 0 to 2pi
    y2 = sin.(x2)
    plot!(x2, y2, label="Underlying function.", color="green", linewidth=2)
    return p
end



# Scatter Plot & Log Scale
using BenchmarkTools
times = Float64[]; sizes = [2^i for i in 1:8]
for n in sizes
    A = rand(n,n); B = rand(n,n)
    bm = @benchmark ($A)*($B)
    push!( times, median(bm.times))
    println(n, " ", median(bm.times))
end
println(times)

scatter(sizes, times, yscale=:log10, xscale=:log10, 
    label="Measured",ylabel="time (ns)", xlabel="n", markersize=8)
```

</br>


### **Benchmarking**

```julia
bm = @benchmark sin(1)            # ouput all kinds of benchmark
time = median(bm.times)           # output median of code running time

#If external variables are involved in the function that we intend to time, then variable must be started with '$' to avoid problems. 
A = rand(3, 3)
bm1 = @benchmark inv(A)           # Errors may be reported as A is not defined
bm2 = @benchmark inv($A)          # A is taken as a global variable
bm3 = @benchmark inv(rand(3, 3))  # the rand(3,3) call is included in the benchmark time
bm4 = @benchmark inv($rand(3, 3)) # the rand(3,3) call occurs before the benchmark time
```


</br>

### **JLD2 & FileIO Package**
This package is for saving and loading data. It usually cannot be read directly.


```julia
using JLD2, FileIO

# Save data
save("file.jld2", "arr_length", arr_length, "times_insert", times_insert, "times_merge", times_merge)

# Load data
arr_length_r, times_insert_r, times_merge_r= load("file.jld2", "arr_length", "times_insert", "times_merge")
```

</br>


### **YAML Package**
Notice that YAML is a markup language dependent from Julia. I only include it inside Julia because MA934 Worksheet include this language.

#### File: xxx.yaml
```yaml
# File Name: config.yaml

key1: 
    child-key1: value1
    child-key2: value2

key2:
    child-key1: value3
    child-key2: value4 
```

#### Use YAML File in Julia 
```Julia
using YAML

# Read the config file to get the parameters
args = YAML.load(open("config.yaml"))





# Use single parameter in YAML inside Julia
# output value2
n = args["key1"]["child-key2"]  

# output Dict{Any,Any}("child-key1"=>value1,"chile-key2"=>"value2")
dict = args["key1"]) 

# output Any["key2", "key1"]
keyset = keys(args)

# output Any["child-key2", "child-key1"]
childkeyset = keys(args["key1"]





# Use for loop to go through each parameter
for key1 in keys(args)
    for key2 in keys(args[key1])
        value = args[key1][key2]
        type = typeof(value)
        println("args[", key1, "][", key2, "] = ", value, "  Type = ", type)
        # output args[key1][child-key1] = value1  Type = String
    end
end
```

</br>

---

</br>

## Data Structure

</br>

### **Key Value, Linked List and Fenwick Tree**

This module contains data structure Key Value, Linked List and Fenwick Tree

-  StructuralRecursion.jl

    ```julia
    module StructuralRecursion

    export KeyValuePair, LinkedList, prepend, append, buildlist, FenwickTree, buildFTree


    # Define a simple composite datatype to hold an (Int64, Float64) key-value pair
    mutable struct KeyValuePair
        key::Int64
        value::Float64   
    end

    # Define list type
    mutable struct LinkedList
        data::KeyValuePair
        next::Union{LinkedList,Nothing}
    end

    # Define the FenwickTree data type
    mutable struct FenwickTree
        data::KeyValuePair
        Left::Union{FenwickTree, Nothing}
        right::Union{FenwickTree, Nothing}
    end

    # Include the files containing the code for various functions operating on these data types
    include(joinpath("functions", "LinkedList.jl")) # joinpath("Folder","file.jl")
    include(joinpath("functions", "FenwickTree.jl"))
    end
    ```

- LinkedList.jl

    ```julia
    # Define list type
    #mutable struct LinkedList
    #    data::KeyValuePair
    #    next::Union{LinkedList,Nothing}
    #end

    # Prepend data to list
    function prepend(list::Union{LinkedList,Nothing}, data::KeyValuePair) 
        new = LinkedList(data, Nothing())
        new.next = list
        return new
    end

    # Append data to list
    function append(list::Union{LinkedList, Nothing}, data::KeyValuePair) 
        if(list == Nothing())
            # Base case: this is the end of the list so add new node
            return LinkedList(data, Nothing())
        else
            # Recursive case: Append the data to the remainder of the list
            list.next = append(list.next, data)
            return list
        end
    end

    # Difference between prepend and append:
    # Prepend: Stack
    # Append: queue

    # Function to build a list from an array of Pair objects
    function buildlist(dataArray::Array{KeyValuePair, 1})
        L = LinkedList(dataArray[1], Nothing())
        for i in 2:length(dataArray)
            L=append(L, dataArray[i])
        end
        return L
    end
    ```

- FenwickTree.jl
    ```julia
    # Function to build a Fenwick tree from an array of KeyValuePair objects containing list of real numbers
    function buildFTree(dataArray::Array{KeyValuePair, 1})
        if length(dataArray) == 1
            # Base case: if dataArray has length 1, we simply return the tree containing this key-value pair
            return FenwickTree(dataArray[1], Nothing(), Nothing())
        else
            # Recursive case: this is the tricky bit. We first compute the sum, S, of the values contained in the elements of
            # dataArray. We then split dataArray into two approximately equal parts accounting for the possibility of an odd
            # number of elements. We then return a tree containin the KeyValuePair (-1, S) in its data field and the two 
            # parts of dataArray in its left and right sub-trees.
            S=0.0
            for i in 1:length(dataArray)
                S+=dataArray[i].value
            end
            k = KeyValuePair(-1, S)
        
            m = floor(Int64, length(dataArray)/2)
            L = dataArray[1:m]
            R = dataArray[m+1:end]
        
            return FenwickTree(k, buildFTree(L), buildFTree(R))
        end
    end
    ```

