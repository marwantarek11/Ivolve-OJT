# Source-to-Image (S2I) Workflow

**Objective:** Use Source-to-Image (S2I) to build container images directly from application source code. Deploy an application using the S2I workflow.

1. **Clone the HTML application repository from GitHub:**  
   [https://github.com/IbrahimmAdel/html.git](https://github.com/IbrahimmAdel/html.git)

2. **Create a BuildConfig in OpenShift to build the HTML application using the Nginx builder image.**  
   Name the BuildConfig `my-html-app`.

3. **Start the build process for the BuildConfig `my-html-app`.**

4. **View the build logs and monitor the progress.**

5. **Once the build is complete, expose the service and access the website.**

### There are two ways to create BuildConfig in OpenShift:

1. **From `oc` CLI**

2. **From OpenShift Console**

## 1. From `oc` CLI

### First, log in to your cluster

### Create a new app as:

```
oc new-app --image=registry.access.redhat.com/rhscl/nginx-114-rhel7:latest --code=https://github.com/IbrahimmAdel/html.git --name=my-html-app -n marwantarek
```

### Start a new build

```
oc start-build my-html-app -n marwantarek
```

### View logs

```
oc logs -f bc/my-html-app -n marwantarek
```

### Expose the app service

```
oc expose svc my-html-app

oc get route
```

## 2. From OpenShift Console

### Follow these steps:


#### Step 1
![Step 1]![1](https://github.com/marwantarek11/Ivolve-OJT/assets/167176241/2f1d6e12-67a2-427d-952f-3f7f5ca43931)


#### Step 2
![Step 2]![2](https://github.com/marwantarek11/Ivolve-OJT/assets/167176241/1f98c14c-901c-4db0-a1e5-9c098c6007aa)


#### Step 3
![Step 3]![3](https://github.com/marwantarek11/Ivolve-OJT/assets/167176241/be9e1a9d-5a82-4b64-b5f8-7a8b29c9d770)


#### Step 4
![Step 4]![4](https://github.com/marwantarek11/Ivolve-OJT/assets/167176241/2a512a63-ae6e-4537-b7aa-797947b8d495)


#### Step 5
![Step 5]![5](https://github.com/marwantarek11/Ivolve-OJT/assets/167176241/395e6977-cf90-4542-91fb-459fc4037e13)


#### Step 6
![Step 6]![6](https://github.com/marwantarek11/Ivolve-OJT/assets/167176241/326b1050-3094-40e7-a6e9-ebdc4425d5d0)


#### Step 7
![Step 7]![7](https://github.com/marwantarek11/Ivolve-OJT/assets/167176241/5a58d102-59fc-40ff-9bdf-b57c17b6aca6)