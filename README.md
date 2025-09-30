# RMW Implementation Fork for RMW Wrapper

This repository is a fork of https://github.com/ros2/rmw_implementation , maintained to provide an extra feature of a `RMW_IMPLEMENTATION_WRAPPER` shim library that can be loaded in addition to the `RMW_IMPLEMENTATION` (DDS, etc.).

This enables e.g. the https://github.com/ros-tooling/graph-monitor/tree/main/rmw_stats_shim to intercept calls to RMW and provide statistics about every node/subscription/publisher in the system.


## Development

1. All live rosdistros are supported
1. Branches are called `${ROS_DISTRO}-rmw-wrapper`
2. As few modifications are added here as possible
3. All changes here are backported to all live distros
4. Upstream branches are periodically merged in


### Updating to latest from upstream

Get sources set up

```bash
git clone https://github.com/robograph-project/rmw_implementation
cd rmw_implementation
git remote add ros2 https://github.com/ros2/rmw_implementation
```

Merge in latest and open PR

```bash
git checkout ${ROS_DISTRO}-rmw-wrapper
git checkout -b ${ROS_DISTRO}-merge-latest
git fetch ros2
git merge ros2/${ROS_DISTRO}
# push that branch and open PR
```

Perform for every distro.
