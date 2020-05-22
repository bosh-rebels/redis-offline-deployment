# redis-offline-deployment
Repository for redis bosh deployment in air-gapped environment.

Redis offline packages is available under `S3://binary-releases-repo-rebels/offline-releases/redis/`

Concourse pipeline required two input resources
  * redis manifest( we have placed manifest & pipeline.yml in this repository)
  * redis offline bucket location (offline package been created in redis-boshrelease pipeline and upload to S3)

You can set concourse pipeline using below command,

  `fly -t sandbox sp -p redis-deployment -c pipeline.yml`

NOTES: Offline package archive, should have following folder structure. 

  Example : redis offline release folder structure
 
  ├── redis-offline-release-0.14.3.tgz
  ├── releases
  │   ├── bpm-1.1.8-ubuntu-xenial-621.74-20200518-125405-440051502.tgz
  │   └── redis-0.14.3-ubuntu-xenial-621.74-20200518-125356-964701539.tgz
  └── stemcells
      └── stemcell.tgz

