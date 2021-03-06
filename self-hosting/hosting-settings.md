---
description: Information about hosting settings
---

# Hosting settings

Every self hosted Budibase platform comes by default with some settings which we recommend you familiarise yourself with as well as updating to suit your needs. All of these settings are passed to your cluster through the use of [environment variables](https://en.wikipedia.org/wiki/Environment_variable), in this section we'll cover the purpose of each of these.

It should be noted that if you wish to modify any of these settings then you will need to restart your Budibase platform for it to recognise these new settings. If you have been running it already then changing some of these settings may affect the user experience, for example changing the `JWT_SECRET` will log everyone out.

The full set of variables can be found in our repo, in the file [`hosting/hosting.properties`](https://github.com/Budibase/budibase/blob/master/hosting/hosting.properties) which should be included in your hosting solution.

1. `MAIN_PORT` - this is the main port that your platform will run on, we have exposed this incase you need to change this.
2. `HOSTING_KEY` - to secure your app deployments we have introduced a key, which can be used to essentially password protect your Budibase platform. This means that only users with the key will be able to deploy from their builder; in the future we will expand on this to offer much more granular control.
3. `JWT_SECRET` - a secret used to secure the [JSON Web Tokens \(JWT\)](https://jwt.io/) generated by the platform for user authentication, we recommend changing this to something random, ideally a UUID.
4. `MINIO_ACCESS_KEY` - the platform makes use of the open source S3 alternative [Minio ](https://min.io/)for object storage, this specifies the access key used to secure the cluster. We recommend changing this.
5. `MINIO_SECRET_KEY` - as above, this is another component used to secure [Minio](https://min.io/), we recommend changing this.
6. `COUCH_DB_PASSWORD` - the password used to secure your hosted [CouchDB ](https://couchdb.apache.org/)service, we recommend changing this.
7. `COUCH_DB_USER` - the username used to secure your hosted [CouchDB ](https://couchdb.apache.org/)service, we recommend changing this.
8. `WORKER_API_KEY` - a key used to secure one of the internal services of our platform, we recommend generating something random for this, ideally a [UUID](https://www.uuidgenerator.net/).

Other settings in the file do not need to be changed but are simply provided in case you which to change the port a service is made available on, we provide access to all the various services our cluster uses directly on a port number for administration purposes \(e.g. logging into [Fauxton](https://couchdb.apache.org/fauxton-visual-guide/index.html) on [CouchDB](https://couchdb.apache.org/)\).

