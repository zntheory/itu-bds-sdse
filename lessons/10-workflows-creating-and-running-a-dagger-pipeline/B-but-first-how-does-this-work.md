---
title: "But first, how does this work?"
---

## Hold on, what is all this code about?

</br>

We have a couple of things going on here.

Let's take a look at the code in the `pipeline.go` file.

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

## The pipeline stage

The commands are essentially mapped to what becomes a Dockerfile.

This is all orchestrated by Dagger and we will never see the Dockerfile as such, but under the hood that is more or less what is happening.

![Dagger go to Dockerfile](../../images/lessons/dagger/dagger-go-to-dockerfile.svg)

</br>

And—it is the same principle when writing the Dagger workflow code in Python or TypeScript.

</br>
</br>
