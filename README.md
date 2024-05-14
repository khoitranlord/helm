![img.png](https://media.licdn.com/dms/image/C5612AQExKGYCYu_F7Q/article-inline_image-shrink_1000_1488/0/1642391063595?e=1703721600&v=beta&t=Q7mbBXdAm_Y-PDh_1p_XyXmu8TbVemsFcG8IAUy2vIY)

# Introduction

The Helm Chart provides a comprehensive solution for deploying and managing [Your Application] on Kubernetes clusters. 
This Helm chart simplifies the deployment process by encapsulating all the necessary Kubernetes manifests and configuration into a single package.

## Helm Chart File Structure

All codebases **must** keep in GitHub repository.

### Overall Folder Structure

Following is overall folder structure to describe how Helm charts will be located:

    infra-helm/   # The master folder of Helm charts using for the project
      charts/     # Folder that will include all private charts, created and maintained by Infra team, following the structure mentioned in custom chart section
      hosting     # Folder consists of packaged charts and a special file called index.yaml which contains an index of all of the charts in the repository.
      README.md   # Guidelines for working on this repository

### Custom Chart
Custom charts will follow the Helm official File Structure as below:

    /spartan
      README.md           # OPTIONAL: A human-readable README file
      Chart.yaml          # A YAML file containing information about the chart
      values.yaml         # The default configuration values for this chart
      templates/          # A directory of templates that, when combined with values, will generate valid Kubernetes manifest files.
      templates/NOTES.txt # OPTIONAL: A plain text file containing short usage notes