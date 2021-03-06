## coreos-pypy

Based on the [coreos-pypy][coreos-pypy].
Installation of PYPY for CoreOS to get Ansible work.

## Usage

### On CoreOS

```bash
    docker run --rm -v /opt:/tmp/core_volume skopciewski/coreos-pypy
```

### ansible configuration

For ansible >= v2.1 set:

```
    ansible_python_interpreter: "/opt/pypy/bin/pypy"
```

## Entrypoint

Any params passed to the container are ignored (except `escto`). Entrypoint will:
* copies current verion of PyPy to the mounted volume
* creates symbolic link `pypy` to the current PyPy version

### Escape to

If you want to inspect container, run docker with `escto` as first param:

```bash
    docker run -it --rm -v /opt:/tmp/core_volume skopciewski/coreos-pypy escto sh
```

[coreos-pypy]: https://github.com/SergeyZh/coreos-pypy
