library(
  // identifier: 'jenkins-pipeline-library@master',
  identifier: "jenkins-pipeline-library@pull/44/head",
  retriever: modernSCM(
    [
      $class: 'GitSCMSource',
      remote: 'https://github.com/viafoura/jenkins-pipeline-library.git',
      credentialsId: 'github-app'
    ]
  )
)

// will publish an @vf npm package to CodeArtifact
vfStandardJSBuildPipeline(
  buildImageName: 'jenkins-agents/jenkins-node12-awscli',
)

/**
 * TODO:
 *   - when library is merged, update to point to main
 */
