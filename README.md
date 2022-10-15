# nginx

<!---
Note: Do NOT edit directly, this file was generated using https://github.com/chainguard-images/readme-generator
-->

[![CI status](https://github.com/priyawadhwa/nginx/actions/workflows/release.yaml/badge.svg)](https://github.com/priyawadhwa/nginx/actions/workflows/release.yaml)

A minimal nginx base image rebuilt every night from source.

## Get It!

The image is available on `cgr.dev`:

```
docker pull cgr.dev/chainguard/nginx:latest
```

## Supported tags

| Tag | Digest | Arch |
| --- | ------ | ---- |
| `1.22` `1.22.0` `1.22.0-r0` `latest` `stable` | `sha256:a6c464e8ff27186fa6ebe0837a93c588e2982123989f07ed586ad39cb359b0bc`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:a6c464e8ff27186fa6ebe0837a93c588e2982123989f07ed586ad39cb359b0bc) | `amd64` `arm64` `armv7` |
| `1.23.1` `1.23.1-r0` | `sha256:e144faced32a874d5ac393c3800c5664404b996f11a62413d191cf1fc652999a`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:e144faced32a874d5ac393c3800c5664404b996f11a62413d191cf1fc652999a) | `amd64` `arm64` `armv7` |
| `1` `1.23` `mainline` | `sha256:f45669d78bbc90cc03d430a7276425adb013cb229998e79917c0f5d0c6049110`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:f45669d78bbc90cc03d430a7276425adb013cb229998e79917c0f5d0c6049110) | `amd64` `arm64` `armv7` |


## Usage

To try out the image, run:

```
docker run -p 8080:80 cgr.dev/chainguard/nginx
```

If you navigate to `localhost:8080`, you should see the nginx welcome page.

To run an example Hello World app, navigate to the root of this repo and run:

```
docker run -v $(pwd)/examples/hello-world/site-content:/var/lib/nginx/html -p 8080:80 cgr.dev/chainguard/nginx
```

If you navigate to `localhost:8080`, you should see `Hello World from Nginx!`.



## Signing

All Chainguard Images are signed using [Sigstore](https://sigstore.dev)!

<details>
<br/>
To verify the image, download <a href="https://github.com/sigstore/cosign">cosign</a> and run:

```
COSIGN_EXPERIMENTAL=1 cosign verify cgr.dev/chainguard/nginx:latest | jq
```

Output:
```
Verification for cgr.dev/chainguard/nginx:latest --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - Existence of the claims in the transparency log was verified offline
  - Any certificates were verified against the Fulcio roots.
[
  {
    "critical": {
      "identity": {
        "docker-reference": "ghcr.io/chainguard-images/nginx"
      },
      "image": {
        "docker-manifest-digest": "sha256:a6c464e8ff27186fa6ebe0837a93c588e2982123989f07ed586ad39cb359b0bc"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "422d80ba7bb2f0c9c0893493a6dbd50919a310c4",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/nginx",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEQCIAhyKKN8WgdLsvMZ+356FO/AU3Oi+3hb5Ko6sjGJaodrAiBjkNPyqjF/73TvwElcDlJOImCP6VHb3z4RAtmf4AVX0A==",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiI5ODgzOWQyZTdhZTQ5NjkwOWMwZDdlMWUxZmJjZmI0YTYyZjcyZjk2MTZhMTY3MTdiMDk5ZGJhMmNiNzc4MDE2In19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJRzNTK1VmYkpVZE9IdzV1WnJJdDlnNjUwZ01BbVJJTU1EWlpoenNlOTBrZEFpRUF3SXhuYlJ1czFDR3Y3NFl5dlRncmE0RU5Rcy9sNzNlWFBxUmNLVVN2am5rPSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUnhla05EUVhwRFowRjNTVUpCWjBsVlFrcGxieXMxUjBVMGJuTTVWWGt6U1RCVmREbGpUVGh2ZG5GQmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFFUlRGTlJFVXdUVVJKZDFkb1kwNU5ha2w0VFVSRk1VMUVSVEZOUkVsM1YycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVYwUzFWUmF6RkNjMDR6WkV0dVRHVjBLMWRpVDBOeFVUaDRjMnBWY0cxaVZGRkpWekFLT0VWNWRYQlNPVWw0ZUdGc1pVWm1SM1ZFZUhaMlkwbGFaWFYwTlZseFN6UnFlRkZXYWpCbGIyZGhWRVZtTTBwVlZuRlBRMEZyT0hkblowcE1UVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZFTDJ0RENtMUdVSGc0UjB0YVJUaFZNR0p2TkU4d2FHc3hVM1pGZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFwM1dVUldVakJTUVZGSUwwSkdNSGRYTkZwYVlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d5Tlc1aFZ6VTBUSGsxYm1GWVVtOWtWMGwyWkRJNWVXRXlXbk5pTTJSNlRETktiR0pIVm1oak1sVjFaVmRHZEdKRlFubGFWMXA2Q2t3eWFHeFpWMUo2VERJeGFHRlhOSGRQVVZsTFMzZFpRa0pCUjBSMmVrRkNRVkZSY21GSVVqQmpTRTAyVEhrNU1HSXlkR3hpYVRWb1dUTlNjR0l5TlhvS1RHMWtjR1JIYURGWmJsWjZXbGhLYW1JeU5UQmFWelV3VEcxT2RtSlVRVmRDWjI5eVFtZEZSVUZaVHk5TlFVVkRRa0ZvZWxreWFHeGFTRlp6V2xSQk1ncENaMjl5UW1kRlJVRlpUeTlOUVVWRVFrTm5NRTFxU210UFJFSnBXVlJrYVZscVNtMU5SMDAxV1hwQk5FOVVUVEJQVkU1b1RtMVNhVnBFVlhkUFZFVTFDbGxVVFhoTlIwMHdUVUozUjBOcGMwZEJVVkZDWnpjNGQwRlJVVVZFYTA1NVdsZEdNRnBUUWxOYVYzaHNXVmhPYkUxRFZVZERhWE5IUVZGUlFtYzNPSGNLUVZGVlJVWXlUbTlaVjJ4MVdqTldhR050VVhSaFZ6Rm9XakpXZWt3eU5XNWhWelUwVFVJd1IwTnBjMGRCVVZGQ1p6YzRkMEZSV1VWRU0wcHNXbTVOZGdwaFIxWm9Xa2hOZG1KWFJuQmlha05DYVhkWlMwdDNXVUpDUVVoWFpWRkpSVUZuVWpsQ1NITkJaVkZDTTBGQmFHZHJka0Z2VlhZNWIxSmtTRkpoZVdWRkNtNUZWbTVIUzNkWFVHTk5OREJ0TTIxMlEwbEhUbTA1ZVVGQlFVSm5PV3hOYmxOblFVRkJVVVJCUldkM1VtZEphRUZMTjBkNVIxRjZjVTluUm5aSFJrRUtkSEJuU205R2N6TTBSVlJLYldaTUswVjRhRVZRUTA5V1Mwa3plRUZwUlVGMVMwcFZVRlJJYjAxb0wybHJOV1pTUTA5WWJIWnRiRGRPTW5sRlpXZ3pOUXBEUldwcFVtSmlVME5PVVhkRFoxbEpTMjlhU1hwcU1FVkJkMDFFWVZGQmQxcG5TWGhCVGxOaFVTOVJNVkpUU3k5bGFqWjZSbGwyVG1zeldIZE5ZM0Z4Q25sS2RUSklPRWQ1VTNaRFpGQnRVVFpvY1ZkWU1WSmhVbGMzVFhoSFpsbElZMlJ3VVRkQlNYaEJTM1Y1VEdGSWVXVXZPVkZsVm1aQ2FDOW1MMVJsZUdnS1RYSlJUQ3RxV25CbWMyd3dlVUkwZEVSYU1WcFhPWGR3UWsxUVQzTjFLMmhaWTJOcGNqbHNLMmwzUFQwS0xTMHRMUzFGVGtRZ1EwVlNWRWxHU1VOQlZFVXRMUzB0TFFvPSJ9fX19",
          "integratedTime": 1665798029,
          "logIndex": 5128543,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/nginx/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/nginx",
      "githubWorkflowSha": "422d80ba7bb2f0c9c0893493a6dbd50919a310c4",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3253937788",
      "sha": "422d80ba7bb2f0c9c0893493a6dbd50919a310c4"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

