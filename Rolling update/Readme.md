# Rolling update

``maxSurgeb`` -> how many pods we can add at a time
``maxUnavailable`` -> how many pods can be unavailable during the rolling update

## Command in kubernetes

``kubectl rollout history deployment/rollingupdate-frontend-deploy`` -> Display of rolling update history
``kubectl rollout history deployment/rollingupdate-frontend-deploy --revision=<number_rolling_update>>`` -> Wyswietlenie szczegolow roling update o numerze <number_rolling_update>
### E.g.
``kubectl rollout history deployment/rollingupdate-frontend-deploy --revision=2`` -> Wyswietlenie szczegolow roling update o numerze 2