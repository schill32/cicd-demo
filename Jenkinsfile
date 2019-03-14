node {
    stage "Create docker image"
    
    // Create the docker image.
    sh "docker build -t cicd-demo ."

    stage "Upload image to registry"
    // Push up your image to your private registry
    sh "docker push http://myregistry:5000/cicd-demo"
    
    stage "Execute remote commands"
    // ssh to the target server. pull down the image, then run the container
    sh 'ssh targetMachine "docker stop cicd-demo && docker pull http://myregistry:5000/cicd-demo && docker run cicd-demo"'
}
