# Creating config/env.json, a properties file to read in typescript

This property file must be create to store all the required credentials such API keys, passwords and other enviornmental setup so that it can be outside the source code and be changed anytime.

### Accessing properties file "env.json" using services

```
    this.httpClient.get<any>('./assets/env/env.json').subscribe((data) =>{ 
        this.zomatoAPIkey= data['zomato_api'];});

```

### Accessing properties file through import

```
import * as data from '../assets/env/env.json';

    @NgModule({
        declarations: [ ],
    imports: [
    AgmCoreModule.forRoot({
      apiKey: data.googleMaps_apiKey

    })] ......

```

In **tsconfig.json**, under *compilerOptions* section do add the following

```
"resolveJsonModule": true,
"esModuleInterop": true,

```

Reference: https://stackoverflow.com/questions/49996456/importing-json-file-in-typescript