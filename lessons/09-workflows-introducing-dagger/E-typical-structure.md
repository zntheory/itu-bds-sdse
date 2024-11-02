---
title: "Typical Dagger pipeline structure"
---

## Before we dive in

We will be using Go for the example pipeline definition.

There are currently two ways to define a Dagger pipeline:

1. Dagger functions, e.g. a function for each stage (build, test, deploy etc.).
2. A single Dagger pipeline function that contains all the stages.

Because Dagger functions are still under development as of this writing, we will use the single Dagger pipeline function for the exercises.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## Typical Dagger pipeline structure

1. A pipeline in Go in its simplest form is a single file, e.g. `pipeline.go`.
2. The pipeline starts through the entry point function `main()`.
3. A Dagger client and background context is created. This is what orchestates Docker under the hood and is responsible for building the execution graph.
4. Pipeline stages are defined. These consist of the code you want to run, e.g. shell commands.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

![Show me more](https://media1.tenor.com/m/4EYaYAMus0cAAAAd/michael-scott-the-office.gif)

</br>
</br>

Ok.. Let's continue and start building a pipeline! <i class="fa-solid fa-rocket"></i>

</br>
</br>
