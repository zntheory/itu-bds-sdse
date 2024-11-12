---
title: "Running a Dagger pipeline locally"
---

## Run the pipeline locally

Open the terminal and nagivate to the directory where the `pipeline.go` file is located and run:

```bash
dagger run go run pipeline.go
```

That is it!

The very first time you run a pipeline, Dagger will download the necessary Docker images and set up the environment. This may take a few minutes.

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

## Expected output

![Dagger run output](../../images/lessons/dagger/dagger-run-output.png)

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

Next, let's run the pipeline in a GitHub Action workflow.

</br>
</br>
