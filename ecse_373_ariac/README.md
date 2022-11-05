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

### ROS Noetic

This package was created for the ARIAC 2019 package which natively supported ROS Melodic.  That package has been updated, but incompletely because of a bug in the Python3 package of `empy`.  That bug has been fixed but not released in Ubuntu Focal at this time.

Static files for `arm1.urdf.xacro`, `gear.urdf.xacro`, and `gear.world` have been generated and copied into this package as a work around to the bug.  The `gear.launch` file was also generated and copied into this package and is now included directly from the `ecse_373_ariac.launch` file.  The `ecse_373_ariac.launch` file was updated to be able to use the static files.  In order to use the work around, use this launch command with an argument for the launch file.

> `roslaunch ecse_373_ariac ecse_373_ariac.launch python:=false`

Included in this package is a patch that can be applied to the em.py file if administrative privileges are available.

> ```sudo patch /usr/lib/python3/dist-packages/em.py < `rospack find ecse_373_ariac`/patches/empy.patch ```

If this patch is applied, the package will work as usual.  When the bug in `empy` is fixed, the elements of this package that exist to work around it will be removed.

## Explanation

The `sample_environment.launch` for the `osrf_gear` package was copied, renamed `ecse_373_ariac.launch` to provide the launch file for the course project environment, and edited to execute a local version of `gear.py` using  `trial_01_config.yaml` and `environment_config.yaml`.

The `gear.py` file from the `osrf_gear` package was copied and edited to create an environment with only one arm.  In addition, the `linear_arm_actuator.urdf.xacro` file and the `arm.urdf.xacro.template` files cally be `gear.py` were copied locally so that they could be altered to work with a single arm instead of a dual arm version of the environment.

The `trial_01_config.yaml` and `environment_config.yaml` files are derived from the `osrf_gear` `sample.yaml` and `sample_user_config.yaml` files altered to provide for an environment and orders to meet the needs of this package.

## Patches

Patches for the `gear.py`, `sample.yaml` and `sample_user_config.yaml` files were created so that the local `gear.py`, `trial_01_config.yaml`, and `environment_config.yaml` files could be easily recreated as necessary.

The process is not automated, but it could and probably should be in the future.
