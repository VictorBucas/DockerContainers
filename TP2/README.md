# What are testcontainers?

Test containers are used to create temporary docker containers, very useful to test our applications 

# 2-2 For what purpose do we need to use secured variables ?

Here, we want to hide critical information such as our Dockerhub token and password, these informations if public would allow anyone to take control of our Dockerhub, pushing, deleting images, changing visibility even placing a backdoor in a docker image.
That's why we need to make these varaibles private

# 2-3 Why did we put needs: build-and-test-backend on this job? Maybe try without this and you will see!

We want to check if our code compile before creating and pushing the image to our Dockerhub. without this line we can end up with an image that doesnt run!

# 2-4 For what purpose do we need to push docker images?

Pushing our images on Dockerhub allows other machines to access it making our application deployable easily. Other advantages are versionning and reliable storage.

