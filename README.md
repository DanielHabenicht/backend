# SimRa Backend

This project is part of the SimRa research project which includes the following subprojects:

- [sirma-android](https://github.com/simra-project/simra-android/): The SimRa app for Android.
- [simra-ios](https://github.com/simra-project/simra-ios): The SimRa app for iOS.
- [backend](https://github.com/simra-project/backend): The SimRa backend software.
- [dataset](https://github.com/simra-project/dataset): Result data from the SimRa project.
- [screenshots](https://github.com/simra-project/screenshots): Screenshots of both the iOS and Android app.
- [SimRa-Visualization](https://github.com/simra-project/SimRa-Visualization): Web application for visualizing the dataset.

In this project, we collect – with a strong focus on data protection and privacy – data on such near crashes to identify when and where bicyclists are especially at risk. We also aim to identify the main routes of bicycle traffic in Berlin. To obtain such data, we have developed a smartphone app that uses GPS information to track routes of bicyclists and the built-in acceleration sensors to pre-categorize near crashes. After their trip, users are asked to annotate and upload the collected data, pseudonymized per trip.
For more information see [our website](https://www.digital-future.berlin/en/research/projects/simra/).

## Development

Build: `docker run -it --rm --name my-maven-project -v "C:\Develop\DSP-2020\simra-backend:/usr/src/app" -w /usr/src/app maven:3.6-openjdk-15 mvn clean package` locally for a build.

Run `docker run -it --rm --name my-maven-project -v "C:\Develop\DSP-2020\simra-backend:/usr/src/app" -w /usr/src/app maven:3.6-openjdk-15 bash` for a local development environment.

## Usage

In order to make it harder abuse the public API we are using a token which is shared with the app. It should be added to each request, e.g. `https://example.com/10/ride?clientHash=<CLIENTHASH>`. The `CLIENTHASH` is configured in the [`simRa_security.config`](./simRa_security.config.example).

## Deployment

After building, just execute `java -jar app.jar`. Make sure to provide the `simRa_security.config` in the same folder as the `app.jar`.