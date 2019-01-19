# ghost-helm

This is an opinionated Ghost Helm chart. I primarily developed it for my own
use, but if you find it useful feel free to use it yourself. Pull requests
are welcome.

Some features of this helm chart:

- Built in support for pulling database and mail password from secrets.
- Use of ClusterIP and ingress for routing requests into the Ghost service.
  You must have an ingress controller configured on your cluster.
- PersistentVolumeClaim configuration. The default configuration will work on
  DigitalOcean. You will need to alter the relevant values if you wish to
  deploy elsewhere. You can also disable the use of a PVC and just use an
  emptyDir for testing, if you like.
- Items under the `ghost` value are turned into JSON and used as your config
  file for running ghost.
- The Recreate strategy is used by default due to limitations on DigitalOcean's
  block volumes.
- This chart doesn't deploy a database for you. You'll need to deploy and
  provide connection details for your database.

Review the items in [values][values] for things you might want to change
in your deployment.

[values]: https://github.com/farmdawgnation/ghost-helm/blob/master/values.yaml

## About the author

Matt Farmer is a software engineer at [Mailchimp][mailchimp], the marketing
platform that empowers the underdog. He occasionally writes at [Farmdawg Nation][fdn].

[mailchimp]: https://mailchimp.com
[fdn]: https://farmdawgnation.com
