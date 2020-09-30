# charts

`choco install kubernetes-helm`

### How It Works

I set up GitHub Pages to point to the `docs` folder. From there, I can
create and publish docs like this:

```console
helm create noct-cloud
helm package noct-cloud  


mv mychart-0.1.0.tgz docs
helm repo index docs --url https://github.com/noct-cloud/charts
git add -i
git commit -av
git push origin master
```

Updating char dependencies 
```console
helm dep update noct-cloud
helm package noct-cloud  
mv noct-cloud-0.1.0.tgz docs
```

From there, I can do a `helm repo add tscharts
https://noct-cloud.github.io/charts/`