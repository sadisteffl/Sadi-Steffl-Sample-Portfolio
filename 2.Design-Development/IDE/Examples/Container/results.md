docker build -t trivy-test .
trivy image trivy-test
[+] Building 0.1s (1/1) FINISHED                                                                 docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                             0.0s
 => => transferring dockerfile: 2B                                                                               0.0s
ERROR: failed to build: failed to solve: failed to read dockerfile: open Dockerfile: no such file or directory
2025-10-23T18:12:10-05:00       INFO    [vulndb] Need to update DB
2025-10-23T18:12:10-05:00       INFO    [vulndb] Downloading vulnerability DB...
2025-10-23T18:12:10-05:00       INFO    [vulndb] Downloading artifact...        repo="mirror.gcr.io/aquasec/trivy-db:2"
73.44 MiB / 73.44 MiB [-------------------------------------------------------------------] 100.00% 21.04 MiB p/s 3.7s
2025-10-23T18:12:14-05:00       INFO    [vulndb] Artifact successfully downloaded       repo="mirror.gcr.io/aquasec/trivy-db:2"
2025-10-23T18:12:14-05:00       INFO    [vuln] Vulnerability scanning is enabled
2025-10-23T18:12:14-05:00       INFO    [secret] Secret scanning is enabled
2025-10-23T18:12:14-05:00       INFO    [secret] If your scanning is slow, please try '--scanners vuln' to disable secret scanning
2025-10-23T18:12:14-05:00       INFO    [secret] Please see https://trivy.dev/v0.67/docs/scanner/secret#recommendation for faster secret detection
2025-10-23T18:12:14-05:00       FATAL   Fatal error     run error: image scan error: scan error: unable to initialize a scan service: unable to initialize artifact: unable to initialize container image: unable to find the specified image "trivy-test" in ["docker" "containerd" "podman" "remote"]: 4 errors occurred:
        * docker error: unable to inspect the image (trivy-test): Error response from daemon: No such image: trivy-test:latest
        * containerd error: containerd socket not found: /run/containerd/containerd.sock
        * podman error: unable to initialize Podman client: no podman socket found: stat podman/podman.sock: no such file or directory
        * remote error: GET https://index.docker.io/v2/library/trivy-test/manifests/latest: UNAUTHORIZED: authentication required; [map[Action:pull Class: Name:library/trivy-test Type:repository]]