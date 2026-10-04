# Awesome-Cloud-Object-Storage

# Awesome-Cloud-Object-Storage

**Curated List of SaaS Products & Open-Source GitHub Projects**
*Focused on S3-Compatible Object Storage, Egress-Free Delivery & Self-Hosted Alternatives*
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Cloud Object Storage**. These tools help developers store and serve unstructured data at scale — images, videos, backups, logs, and ML datasets — with S3-compatible APIs and predictable pricing.

**Examples** include Amazon S3, Azure Blob Storage, Google Cloud Storage, Cloudflare R2, Backblaze B2, Wasabi Hot Cloud Storage, DigitalOcean Spaces, MinIO, Linode Object Storage, and Scaleway Object Storage (the category leaders).

**Open-source emphasis**: The open-source object storage ecosystem is **exceptionally mature**. **MinIO** is the de facto standard for S3-compatible self-hosted object storage, with **Ceph RGW** providing a more complex but fully open-source alternative for large-scale deployments. **RustFS** has emerged as a high-performance MinIO alternative written in Rust . However, **no open-source alternative matches the global distribution and managed infrastructure** of AWS S3, Cloudflare R2, or Google Cloud Storage.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## 📖 Table of Contents

- [☁️ SaaS/Hosted Platforms](#-saas-hosted-platforms)
- [🔓 Open-Source GitHub Projects](#-open-source-github-projects)
- [🤝 How to Contribute](#-how-to-contribute)
- [⚠️ Disclaimer](#-disclaimer)

## ☁️ SaaS/Hosted Platforms

> **📊 Market Context**: The global object storage market is estimated at **~$12B in 2026**, growing toward **~$30B by 2032**. The sector is **moderately concentrated** — AWS S3 holds the dominant share, while **Cloudflare R2** has disrupted the market with **zero egress fees** . **Egress is the primary cost driver** for most workloads: S3 charges **$0.09/GB** for egress, meaning a SaaS storing 50 GB but serving 500 GB/month pays **31x more for egress than storage** . This has driven adoption of R2 (zero egress), Backblaze B2 (3x free egress), and Wasabi (flat-rate with no egress fees) . No single vendor holds a winner-take-all position; enterprises typically run multi-provider strategies based on workload characteristics.

| Platform | Description | Pricing (Starting Tier) | Free Tier Limits | Company Size |
|----------|-------------|------------------------|------------------|--------------|
| **[Amazon S3](https://aws.amazon.com/s3/)** | The original and most widely adopted object storage service. 99.999999999% durability, 350+ edge locations. | **S3 Standard**: **$0.023/GB-month** (first 50 TB) . **Egress**: **$0.09/GB** after 100 GB/month free. **Glacier Deep Archive**: **$0.00099/GB-month** . | **AWS Free Tier**: **5 GB** S3 Standard for **12 months** (new accounts). **100 GB** egress free/month. **2,000 free PUT requests**, **20,000 GET requests** . | **~$638B revenue (Amazon FY2025)** |
| **[Cloudflare R2](https://www.cloudflare.com/developer-platform/r2/)** | **The egress-free object storage disruptor.** S3-compatible, no egress fees, globally distributed. | **Standard**: **$0.015/GB-month** storage . **Class A (write)**: **$4.50/million** requests. **Class B (read)**: **$0.36/million** requests . **Egress**: **$0/GB** . | **Free tier**: **10 GB-month** storage, **1 million** Class A operations, **10 million** Class B operations per month . | **~$2.17B revenue (Cloudflare FY2025)** |
| **[Backblaze B2](https://www.backblaze.com/cloud-storage)** | **Predictable pricing with 3x free egress.** S3-compatible, no minimum file size or storage duration. | **Storage**: **$6.95/TB/month** (~**$0.00695/GB**) . **API calls**: **Free** . **Egress**: **Free up to 3x** average monthly storage; then **$0.01/GB** . | **First 10 GB storage always free** . **Unlimited free egress** to CDN/compute partners (Fastly, Cloudflare, bunny.net, Vultr, etc.) . | **Public (BLZE), ~$100M+ revenue est.** |
| **[Wasabi Hot Cloud Storage](https://wasabi.com/)** | **Flat-rate pricing with no egress fees.** S3-compatible, no minimum storage duration. | **$7.99/TB/month** (~**$0.00799/GB**) . **No egress fees**. **No API request fees**. | **1 TB free trial** for 30 days. **No perpetual free tier** . | **Private (~$250M+ revenue est.)** |
| **[Google Cloud Storage](https://cloud.google.com/storage)** | Google's object storage with four storage classes for different access patterns. 11 nines durability. | **Standard**: **$0.020/GB-month** (regional US). **Nearline**: **$0.010/GB-month**. **Coldline**: **$0.004/GB-month**. **Archive**: **$0.0012/GB-month** . **Minimum storage periods**: 30/90/365 days . | **Google Cloud Free Tier**: **$300 credit for 90 days**. **Always Free**: **5 GB** Cloud Storage, **1 GB** network egress/month . | **~$350B revenue (Alphabet FY2025)** |
| **[Azure Blob Storage](https://azure.microsoft.com/en-us/products/storage/blobs/)** | Microsoft's object storage with hot, cool, cold, and archive tiers. Deep integration with Azure. | **Hot tier**: **~$0.018/GB-month** (LRS). **Cool**: **~$0.01/GB-month**. **Archive**: **~$0.00099/GB-month**. **Egress**: **~$0.087/GB** after 100 GB free. | **Azure free account**: **$200 credit for 30 days**. **5 GB** Blob storage for **12 months** (new accounts). | **~$281B revenue (Microsoft FY2025)** |
| **[DigitalOcean Spaces](https://www.digitalocean.com/products/spaces)** | S3-compatible object storage with built-in CDN. Simple, predictable pricing. | **Base subscription**: **$5.00/month** (includes **250 GiB** storage + **1,024 GiB** outbound transfer) . **Additional storage**: **$0.02/GiB/month**. **Additional transfer**: **$0.01/GiB** . | **None** — $5/month minimum. **No free tier**. | **Public (DOCN), ~$700M+ revenue** |
| **[Linode Object Storage (Akamai)](https://www.linode.com/products/object-storage/)** | Akamai's S3-compatible object storage. Simple flat-rate pricing. | **$5/month** (includes **250 GB** storage + **1 TB** outbound transfer) . **Additional storage**: **$0.02/GB**. **Additional transfer**: **$0.005/GB** . | **None** — $5/month minimum. **No free tier**. | **Part of Akamai (~$4B+ revenue)** |
| **[Scaleway Object Storage](https://www.scaleway.com/en/object-storage/)** | European S3-compatible object storage. Multi-AZ and One Zone options. | **Standard Multi-AZ**: **€0.01606/GB-month** (~$0.017) . **Standard One Zone**: **€0.00803/GB-month** (~$0.0087) . **Egress**: **75 GB free/month**, then **€0.01/GB** . **Glacier**: **€0.00254/GB-month** . | **75 GB free egress/month** . **No perpetual free storage tier**. | **Private (part of Iliad Group)** |

## 🔓 Open-Source GitHub Projects

Sorted by star count (descending). Star badge links to each repo's stargazers page.

| Repo | Description | Stars |
|---|---|---|
| **[MinIO](https://github.com/minio/minio)** — **The de facto standard for S3-compatible self-hosted object storage.** High-performance, Kubernetes-native, erasure coding, versioning, object locking, and replication. The most widely deployed open-source object storage platform. AGPL-3.0. | [![Stars](https://img.shields.io/github/stars/minio/minio?style=social&color=white)](https://github.com/minio/minio/stargazers) | ~48,000 |
| **[Ceph](https://github.com/ceph/ceph)** — **Unified distributed storage system** providing object (RGW), block (RBD), and file (CephFS) storage in a single cluster. S3 and Swift compatible, self-healing, self-managing. **Enterprise-grade** but operationally complex. LGPL-2.1. | [![Stars](https://img.shields.io/github/stars/ceph/ceph?style=social&color=white)](https://github.com/ceph/ceph/stargazers) | ~15,000 |
| **[RustFS](https://github.com/opc-source/rustfs)** — **High-performance distributed object storage written in Rust.** Positioned as a **MinIO alternative** with multi-architecture support (amd64, arm64), Docker/Kubernetes/Helm deployment, Nix Flake, and OIDC integration (Microsoft Entra ID). **AGPL-3.0** . | [![Stars](https://img.shields.io/github/stars/opc-source/rustfs?style=social&color=white)](https://github.com/opc-source/rustfs/stargazers) | ~1,000 |
| **[SeaweedFS](https://github.com/seaweedfs/seaweedfs)** — **Fast distributed storage system for blobs, objects, and files.** S3-compatible API, optimized for high throughput and low latency. Scales to billions of files. Apache-2.0. | [![Stars](https://img.shields.io/github/stars/seaweedfs/seaweedfs?style=social&color=white)](https://github.com/seaweedfs/seaweedfs/stargazers) | ~24,000 |
| **[Garage](https://github.com/deuxfleurs/garage)** — **S3-compatible distributed object store for self-hosted deployments.** Designed for geo-distributed clusters, lightweight, runs on commodity hardware. AGPL-3.0. | [![Stars](https://img.shields.io/github/stars/deuxfleurs/garage?style=social&color=white)](https://github.com/deuxfleurs/garage/stargazers) | ~5,000 |

**Additional open-source options worth exploring:**

| Repo | Description |
|---|---|
| **[OpenIO](https://github.com/openio-sds/openio)** — S3-compatible object storage with grid architecture. Designed for large-scale, on-premises deployments. AGPL-3.0. | [![Stars](https://img.shields.io/github/stars/openio-sds/openio?style=social&color=white)](https://github.com/openio-sds/openio/stargazers) |
| **[Zenko](https://github.com/scality/Zenko)** — Multi-cloud data controller for S3-compatible storage. Enables replication and tiering across providers. Apache-2.0. | [![Stars](https://img.shields.io/github/stars/scality/Zenko?style=social&color=white)](https://github.com/scality/Zenko/stargazers) |

## 🤝 How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## ⚠️ Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Cloud object storage platforms handle potentially sensitive organizational data; ensure proper access controls, encryption, and compliance with data protection regulations.
- **Open-source reality**: The open-source ecosystem for object storage is **exceptionally mature**. **MinIO** is the de facto standard for S3-compatible self-hosted storage, with **Ceph RGW** providing a more complex but fully open-source alternative for large-scale deployments . **RustFS** has emerged as a high-performance MinIO alternative written in Rust with Docker/Kubernetes/Nix support . However, **no open-source alternative matches the global distribution, managed infrastructure, and edge caching** of AWS S3, Cloudflare R2, or Google Cloud Storage. The open-source path is **genuinely viable** for self-hosted storage, on-premises deployments, or organizations with strong infrastructure engineering capacity.
- **Pricing caveat**: All pricing figures above are **verified against cited search results** but may change without notice. **Egress costs are the primary driver** for most workloads — a SaaS storing 50 GB but serving 500 GB/month pays **31x more for egress than storage** on S3 . Always model your egress volume before committing to a provider.

---

**Made for backend engineers, DevOps teams, platform engineers, and infrastructure architects.**
Let's make cloud object storage more open, transparent, and egress-friendly.
