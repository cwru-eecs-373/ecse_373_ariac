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

The `sample_environment.launch` for the `osrf_gear` package was copied, renamed `ecse_373_ariac.launch` to provide the launch file for the course project environment, and edited to execute a local version of `gear.py` using  `trial_01_config.yaml` and `environment_config.yaml`.

The `gear.py` file from the `osrf_gear` package was copied and edited to create an environment with only one arm.  In addition, the `linear_arm_actuator.urdf.xacro` file and the `arm.urdf.xacro.template` files cally be `gear.py` were copied locally so that they could be altered to work with a single arm instead of a dual arm version of the environment.

The `trial_01_config.yaml` and `environment_config.yaml` files are derived from the `osrf_gear` `sample.yaml` and `sample_user_config.yaml` files altered to provide for an environment and orders to meet the needs of this package.

## Patches

Patches for the `gear.py`, `sample.yaml` and `sample_user_config.yaml` files were created so that the local `gear.py`, `trial_01_config.yaml`, and `environment_config.yaml` files could be easily recreated as necessary.

The process is not automated, but it could and probably should be in the future.
