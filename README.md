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
| `1.22` `1.22.0` `1.22.0-r0` `latest` `stable` | `sha256:ef371772f079eda2032bf021d9ce905e8b66d4032773973cb88e27833e74fceb`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:ef371772f079eda2032bf021d9ce905e8b66d4032773973cb88e27833e74fceb) | `amd64` `arm64` `armv7` |
| `1` `1.23` `1.23.1` `1.23.1-r0` `mainline` | `sha256:2dd54296dbb9284a8b4e7b196c7c06cea0fd12534d88b77dc5de6cb879c9e6f7`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:2dd54296dbb9284a8b4e7b196c7c06cea0fd12534d88b77dc5de6cb879c9e6f7) | `amd64` `arm64` `armv7` |


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
        "docker-manifest-digest": "sha256:ef371772f079eda2032bf021d9ce905e8b66d4032773973cb88e27833e74fceb"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "f7232dcb5195fc71302bfd1a2bfa23df79b198b1",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/nginx",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEUCIQCgTwXdy23UK5vPXs8a8oG5wtHwLqNzK9rWQ+N3qbMcEwIgOTqAVcHE4H9MCg/sVOB6u1RuX4Jxwfpme5INvswX6C4=",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiJlNTc4NjUxNmY5NDdkNzExNDNiZmI4YTIyODlmYTUxYmRiOTg5N2Y4NGQwYjJhZDMzNWEwMzQxNzc5YjBiYTAxIn19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJRUZIUEY3OUYvYXkvRVNrWURLbURmQWlqcENaTUhiT3diZElNODhMMmlGQkFpRUF0MWZGdEI5aVNYaWxucS94V0g5bFRqVkxjNGpwWjREaFpQVWVHeS9DWlk0PSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUnhha05EUVhrclowRjNTVUpCWjBsVlpITlFZa1JqZERRMUx6ZE1PR2R1TkVkdVoya3pkSEJJY0hwemQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFFUlhwTlJFVXdUVVJGTkZkb1kwNU5ha2w0VFVSRmVrMUVSVEZOUkVVMFYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVZNT1dVNEswVkxWVzFxUVZObFMyUnVhbFZOYUdwSVVUSktOSGszUTNsUlpVMVNSRlFLVjBWNVZqbE5NbHBrVjFseVYwRTJhREV3THpsTGFFVmxlbTA0VVdJNFVuSkVjVlpLTjJaaFJtbG9hRFV2YVM5TVJUWlBRMEZyTkhkblowcExUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlV2VFU5dUNsZGFaV0ZoWTJWNUx6UnBkR2xhVG05alF6TlpRak5yZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFwM1dVUldVakJTUVZGSUwwSkdNSGRYTkZwYVlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d5Tlc1aFZ6VTBUSGsxYm1GWVVtOWtWMGwyWkRJNWVXRXlXbk5pTTJSNlRETktiR0pIVm1oak1sVjFaVmRHZEdKRlFubGFWMXA2Q2t3eWFHeFpWMUo2VERJeGFHRlhOSGRQVVZsTFMzZFpRa0pCUjBSMmVrRkNRVkZSY21GSVVqQmpTRTAyVEhrNU1HSXlkR3hpYVRWb1dUTlNjR0l5TlhvS1RHMWtjR1JIYURGWmJsWjZXbGhLYW1JeU5UQmFWelV3VEcxT2RtSlVRVmRDWjI5eVFtZEZSVUZaVHk5TlFVVkRRa0ZvZWxreWFHeGFTRlp6V2xSQk1ncENaMjl5UW1kRlJVRlpUeTlOUVVWRVFrTm9iVTU2U1hwTmJWSnFXV3BWZUU5VVZtMVplbU40VFhwQmVWbHRXbXROVjBWNVdXMWFhRTFxVG10YWFtTTFDbGxxUlRWUFIwbDRUVUozUjBOcGMwZEJVVkZDWnpjNGQwRlJVVVZFYTA1NVdsZEdNRnBUUWxOYVYzaHNXVmhPYkUxRFZVZERhWE5IUVZGUlFtYzNPSGNLUVZGVlJVWXlUbTlaVjJ4MVdqTldhR050VVhSaFZ6Rm9XakpXZWt3eU5XNWhWelUwVFVJd1IwTnBjMGRCVVZGQ1p6YzRkMEZSV1VWRU0wcHNXbTVOZGdwaFIxWm9Xa2hOZG1KWFJuQmlha05DYVdkWlMwdDNXVUpDUVVoWFpWRkpSVUZuVWpoQ1NHOUJaVUZDTWtGQmFHZHJka0Z2VlhZNWIxSmtTRkpoZVdWRkNtNUZWbTVIUzNkWFVHTk5OREJ0TTIxMlEwbEhUbTA1ZVVGQlFVSm5PRGN2TTJSclFVRkJVVVJCUldOM1VsRkphRUZPYlhnMFltd3hkMnhvUm5oUFMyY0tUR2xEUlRkVWRucERjREl4YkZCV1dYTXdjRU5KTjIxVlpIcGFhVUZwUWpCT0wxbHJSVFJsWlN0dE4zZzNaRmhzTVRSbGFIUlNZMmRHTkdRd2JuaDFUZ3BQYURORVJ5dDVRV3hFUVV0Q1oyZHhhR3RxVDFCUlVVUkJkMDV3UVVSQ2JVRnFSVUZ4ZWpseVUwb3pVVnBCVmxFNU1HeExURVZqYlhZdk9FTXlMMUpoQ2xCQ1lqRktaRWdyYXpkRFoycGhOazEwZEVkQ09FNTNiVlkzZWpKVk1qVkpaalJYZGtGcVJVRnFRMU5rZDFBM1R6aHFjRGxtYjBWelNuSTFhekZvWWtvS2JVd3hNSEJ5ZW01eWQwZFpVSFphYnpWbmExYzJZa0pZY1habGVGRm1VVVpvV1VVMGRVaGpUd290TFMwdExVVk9SQ0JEUlZKVVNVWkpRMEZVUlMwdExTMHRDZz09In19fX0=",
          "integratedTime": 1665625235,
          "logIndex": 4997402,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/nginx/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/nginx",
      "githubWorkflowSha": "f7232dcb5195fc71302bfd1a2bfa23df79b198b1",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3239026144",
      "sha": "f7232dcb5195fc71302bfd1a2bfa23df79b198b1"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

