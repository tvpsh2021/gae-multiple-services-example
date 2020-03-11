# Google App Engine Multiple Services Example in Node.js

In this example project will show you:

- Two App Engine Services configurations, one is `default`, the other is called `blog`
  - `default` service will point to `jimmmmy.com/*` (change it with your own domain)
  - `blog` service will point to `blog.jimmmmy.com/*` (change it with your own domain)
- A `dispatch.yaml` to map the route with custom domain
- A `cloudbuild.yaml` required by Google Cloud Build to trigger the deploy when this repository push new commit to origin

Please notice the free tier of Google App Engine is 28 Instance hours per day, and this example will make you create two instances, it's more consume than one instance indeed.

## Pre-requirement

- Download Google Cloud SDK and auth with `gcloud init`
- Add custom domain in Google App Engine's setting page, also update your DNS setting
- Connect your GitHub repository with Google Cloud Build, add a trigger with cloudbuild.yaml when push new commit to origin

## Deploy manually

```bash
# update route mapping
$ gcloud app deploy dispatch.yaml
# update GAE services
$ gcloud app deploy resume/app.yaml blog/app.blog.yaml
```

## Reference
- [Structuring Web Services in App Engine](https://cloud.google.com/appengine/docs/standard/nodejs/configuration-files)
- [How Requests are Routed](https://cloud.google.com/appengine/docs/standard/nodejs/how-requests-are-routed)
