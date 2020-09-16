# ECSE/CSDS 373/473 ARIAC 2019 Package

This package is a companion package for the CWRU ECSE/CSDS 373/474 *Modern Robot Programming* course.  It removes the second arm from the environment and provides a set environments.

The website for the ARIAC competion held in 2019 can be found at:
>  [https://bitbucket.org/osrf/ariac/wiki/2019/Home](https://bitbucket.org/osrf/ariac/wiki/2019/Home)

## Dependencies

The package depends on the ARIAC 2019 competition packages.  They are available from the OSRF/NIST repositories on Bitbucket ([installation instructions](https://bitbucket.org/osrf/ariac/wiki/2019/tutorials/installation)).

Follow the installation guide there.

## Use

To run the modified ARIAC simulation, use the following command:

> `roslaunch ecse_373_ariac ecse_373_ariac.launch`

## Explanation

The `sample_environment.launch` for the `osrf_gear` package was copied, renamed `ecse_373_ariac.launch` to provide the launch file for the course project environment, and edited to execute a local version of `gear.py` using local version of `sample.yaml` and `sample_user_config.yaml`.

The `gear.py` file from the `osrf_gear` package was copied and edited to create an environment with only one arm.

The `sample.yaml` and `sample_user_config.yaml` files have been copied locally to be altered to suit the course project.
