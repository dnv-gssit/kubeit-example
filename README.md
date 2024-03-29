# Simple kube-it example

1. Build and publish docker image

   Source folder: docker

   Pipeline: .github/workflows/image.yml

2. Helm chart for application

   Source folder: helm/example

   Created by `helm create` command and tuned for KubeIT: use Virtualservice for istio

3. Deploy ArgoCD application as apps of apps

   Source folder: argocd

# Development environment

1. IDE for coding: Eclipse or Visual Studio Code

2. git

3. [pre-commit](https://pre-commit.com/)

# Workshop tasks

1. Expose your docker image via ACR or GitHub packages (public).

2. In case of using your own Dev ACR:

* please assign role **ACRpull** to Service Principle **Az_KubeIT_AcrReader_Env_Dev**

* create credentials to your ACR, add as gitbub secrets, modify `.github/image.yml` pipeline to push into ACR

  ```
      ... # instead of Log in to the Container registry task
      uses: docker/login-action@v2
      with:
        registry: ${{ env.ACR_NAME }}
        username: ${{ secrets.ACR_USERNAME }}
        password: ${{ secrets.ACR_PASSWORD }}
  ```

3. Modify `argocd/values.yaml`, **image.repository** to use your own image.

4. Do more modifications in helm chart `helm/` or `argocd` and play with KubeIT.

# References:

1. [Intro Guide to Dockerfile Best Practices](https://www.docker.com/blog/intro-guide-to-dockerfile-best-practices)

2. [A Beginner-Friendly Introduction to Kubernetes](https://towardsdatascience.com/a-beginner-friendly-introduction-to-kubernetes-540b5d63b3d7)

3. [Helm best practices](https://helm.sh/docs/chart_best_practices/)
   [13 Best Practices for using Helm - DEV Community](https://dev.to/coder_society/13-best-practices-for-using-helm-2mac)

4. [GitOps with ArgoCD](https://codefresh.io/learn/argo-cd/)
   [ArgoCD best practices](https://codefresh.io/blog/argo-cd-best-practices)

5. [argoproj/argocd-example-apps: Example Apps to Demonstrate Argo CD (github.com)](https://github.com/argoproj/argocd-example-apps)
