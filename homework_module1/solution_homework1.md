## Task 1
**Question 1**
Run docker with the python:3.13 image. Use an entrypoint bash to interact with the container.
What's the version of pip in the image?
**Solution**
`docker run --rm -it --entrypoint bash python:3.13 -c "pip --version"`
<img src="images/task1_1.jpg" width="800" height="220" alt="docker run"/>
**Answer**
25.3