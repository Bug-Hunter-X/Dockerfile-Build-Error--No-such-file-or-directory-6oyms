# Dockerfile Build Error: No such file or directory

This repository demonstrates a common error when building Docker images: the `COPY` instruction fails because the specified file does not exist in the build context.

## Bug
The original `Dockerfile` attempts to copy a `requirements.txt` file, but this file is missing from the build context.  This results in a build error.

## Solution
The corrected `Dockerfile` includes the `requirements.txt` file in the build context and ensures the necessary Python packages are installed before copying the application code.

## How to reproduce

1. Clone this repository
2. Build the original `Dockerfile` (it will fail).
3. Build the `Dockerfile-solution` (it will succeed).

## How to fix

Always ensure that any files referenced in your `Dockerfile` (e.g., using `COPY` or `ADD`) are present in the directory from which you are building the image.