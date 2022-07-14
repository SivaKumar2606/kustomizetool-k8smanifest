```` bash
.
├── base
│   ├── deployment.yaml
│   ├── kustomization.yaml
│   └── service.yaml
└── overlays
    ├── dev
    │   ├── kustomization.yaml
    │   └── patches
    │       └── dev-replica-count.yaml
    ├── prod
    │   ├── kustomization.yaml
    │   └── patches
    │       └── prod-replica-count.yaml
    └── stag
        ├── kustomization.yaml
        └── patches
            └── stag-replica-count.yaml

#### Commands used
kustomize version
kustomize build overlays/stag
kustomize build overlays/stag > stag-deployment.yaml
ku apply -f stag-deployment.yaml
kustomize build overlays/stag | ku apply -f -
kubectly apply --kustomize overlays/stag
(or)
ku apply -k overlays/stag

Similarly all above commands are applicable to other environments too.
````
</br>
