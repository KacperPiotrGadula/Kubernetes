# Best practises

With docker push always upload two versions of the image

- the first latest as a marker of the last added version of the application
- the second in the name of the commit number in order to be able to track the corresponding version of the docker file from which the image was built