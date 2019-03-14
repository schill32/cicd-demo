node {
    stage "Create docker image"
    
    // Create the docker image.
    sh "docker build -t cicd-demo ."

    // Push up your image to your private registry
    sh "docker push http://myregistry:5000/cicd-demo"
    
    // ssh to the target server. pull down the image, then run the container
    sh 'ssh targetMachine "docker pull http://myregistry:5000/cicd-demo && docker run cicd-demo"'
}
