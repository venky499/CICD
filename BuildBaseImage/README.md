I - Setup Webhook pointing to the jenkins job
  - Enable only "Merge request events"
II - Create a Jenkins job to build base image:
* Give the following are the build steps for the Job
echo "triggering image build for Wezva CICD ..."
sh ./buildimage.sh $BaseImage $BuildImage $registrypassword
echo "Completed image build for Wezva CICD ..."

* Set Job Parameters i.e string parameter for BaseImage, BuildImage & password parameter for registrypassword & set the following as default values
  BASEIMAGE="jboss/base-jdk:11"
  BuildImage="wildfly"

* Source Code Management, git repo as "https://gitlab.com/scmlearningcentre/demo.git"
* Build when a change is pushed to GitLab under "Build Triggers"
  - Enable only " Accepted Merge Request Events" and in Advanced under "Allowed branches" give the branch name as prod

  Date: Apr 17
