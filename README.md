# Kubernetes Cluster API Provider Libvirt

[![Go Report Card](https://goreportcard.com/badge/github.com/multi-arch/cluster-api-provider-libvirt)](https://goreportcard.com/report/github.com/multi-arch/cluster-api-provider-libvirt)

<img src="https://github.com/kubernetes/kubernetes/raw/master/logo/logo.png" width="100" height="100" /><a href="https://libvirt.org"><img height="96" hspace="96px" src="https://libvirt.org/logos/logo-square-96.png" alt="Powered by Libvirt" /></a>

Kubernetes-native declarative infrastructure for Libvirt.

## What is the Cluster API Provider Libvirt

The [Cluster API][cluster_api] brings declarative, Kubernetes-style APIs to cluster creation, configuration and management. Cluster API Provider for libvirt is a concrete implementation of Cluster API
for libvirt.

The API itself is shared across multiple cloud providers allowing for libvirt deployments of Kubernetes. It is built atop the lessons learned from previous cluster managers such
as [kops][kops] and [kubicorn][kubicorn].

## Launching a Kubernetes cluster on Libvirt

Check out the [getting started guide](./docs/getting_started.md) for launching a cluster on libvirt.

## Features

- Native Kubernetes manifests and API
- Manages the bootstrapping of VMs on cluster.
- Doesn't use SSH for bootstrapping nodes.
- Installs only the minimal components to bootstrap a control plane and workers.

------

## Compatibility with Cluster API and Kubernetes Versions

This provider's versions are compatible with the following versions of Cluster API:

|                     | Cluster API v1beta1 (v1.3) | Cluster API v1beta1 (v1.4) | Cluster API v1beta1 (v1.5) | Cluster API v1beta1 (v1.6) |
|---------------------|:--------------------------:|:--------------------------:|:--------------------------:|:--------------------------:|
| Version PLACEHOLDER |             ☓              |             ☓              |             ☓              |             x              |

The provider doesn't dictate supported K8s versions, and it supports whatever CAPI supported. For more information about the provider's compatibility with K8s versions, please refer
to [CAPI Supported Kubernetes Versions](https://cluster-api.sigs.k8s.io/reference/versions.html).

Basically:

- 4 Kubernetes minor releases for the management cluster (N - N-3)
- 6 Kubernetes minor releases for the workload cluster (N - N-5)

**NOTE:** As the versioning for this project is tied to the versioning of Cluster API, future modifications to this policy may be made to more closely align with other providers in the Cluster API
ecosystem.

## Kubernetes versions with published images

Note: These OVAs are not updated for security fixes and it is recommended to always use the latest patch version for the Kubernetes version you wish to run. For production-like environments, it is
highly recommended to build and use your own custom images.

#A full list of the published machine images for CAPV may be obtained with the following command:

#```shell
#gsutil ls gs://capv-templates/*
#```

#Or, to produce a list of URLs for the same image files (and their checksums), the following command may be used:

#```shell
#gsutil ls gs://capv-templates/*/*.{ova,sha256} | sed 's~^gs://~https://storage.googleapis.com/~'
#```

## Documentation

Further documentation is available in the `/docs` directory.

## Getting involved and contributing

If you're interested in contributing to cluster-api-provider-libvirt, we would love your suggestions, contributions, and help! Also, the maintainers can be contacted at
any time to learn more about how to get involved.

In the interest of getting more new people involved we tag issues with [`good first issue`][good_first_issue]. These are typically issues that have smaller scope but are good ways to start to get
acquainted with the codebase.

We also encourage ALL active community participants to act as if they are maintainers, even if you don't have "official" write permissions. This is a community effort, we are here to serve the
Kubernetes community. If you have an active interest and you want to get involved, you have real power! Don't assume that the only people who can get things done around here are the "maintainers".

We also would love to add more "official" maintainers, so show us what you can do!

This repository uses the Kubernetes bots. See a full list of the commands [here][prow].

## Code of conduct

Participating in the project is governed by the Kubernetes code of conduct. Please take some time to read the [code of conduct document][code_of_conduct].

### Implementer office hours

# consider launching something for this
- Previous meetings: \[ [notes][meeting_notes] \]

### Other ways to communicate with the contributors
# TODO have a slack presence
#Please check in with us in the [#cluster-api-libvirt][slack] channel on Slack or email us at our [mailing list][mailing_list]

## Github issues

### Bugs

If you think you have found a bug please follow the instructions below.

- Please spend a small amount of time giving due diligence to the issue tracker. Your issue might be a duplicate.
- Get the logs from the cluster controllers. Please paste this into your issue.
- Follow the helpful tips provided in the [troubleshooting document][troubleshooting] as needed.
- Open a [new issue][new_issue].
- Remember that users might be searching for your issue in the future, so please give it a meaningful title to help others.
- Feel free to reach out to the cluster-api community on the [kubernetes slack][slack_info].

### Tracking new features

We also use the issue tracker to track features. If you have an idea for a feature, or think you can help this provider become even more awesome follow the steps below.

- Open a [new issue][new_issue].
- Remember that users might be searching for your issue in the future, so please give it a meaningful title to help others.
- Clearly define the use case, using concrete examples. EG: I type `this` and cluster-api-provider-libvirt does `that`.
- Some of our larger features will require some design. If you would like to include a technical design for your feature please include it in the issue.
- After the new feature is well understood, and the design agreed upon, we can start coding the feature. We would love for you to code it. So please open up a **WIP** *(work in progress)* pull
  request, and happy coding.

<!-- References -->

[cluster_api]: https://github.com/kubernetes-sigs/cluster-api

[code_of_conduct]: https://git.k8s.io/community/code-of-conduct.md

[good_first_issue]: https://github.com/kubernetes-sigs/cluster-api-provider-libvirt/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22

[kops]: https://github.com/kubernetes/kops

[kubicorn]: http://kubicorn.io/

#[mailint_list]: https://groups.google.com/forum/#!forum/kubernetes-sig-cluster-lifecycle

[meeting_notes]: none

[new_issue]: https://github.com/kubernetes-sigs/cluster-api-provider-libvirt/issues/new

[prow]: https://prow.k8s.io/command-help?repo=multi-arch%2Fcluster-api-provider-libvirt

#[slack]: slack

[slack_info]: https://github.com/kubernetes/community/tree/master/communication#communication

[troubleshooting]: ./docs/troubleshooting.md

# community meeting [zoom_meeting]: 

[time_zone_converter]: http://www.thetimezoneconverter.com/?t=08:00&tz=PT%20%28Pacific%20Time%29
