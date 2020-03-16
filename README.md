# a__2020_data_science_template

**Our high level tech spec worldview**
```
python3.6
flask api for serving ml
sklearn style apis
command line flexibility for productizing programs
```

I hypothesize that a project template can be the thing that takes your work from great to epic. If you believe the same thing, take a look at my personal template.

# The Entry Point

`main.py` is the entrypoint to your PROJECT. You adjust the arguments via `argparse` in the `if __name__ == '__main__':` block and then ensure the proper logic happens in each of your respective `--mode` flags, each of which are a function in `main.py`. Once you do it once, it becomes a wonderfully conscise way of coding, so trust me in its value.

# The README.md's Purpose

The README explains the repository and how to use it. Never leave your users hanging. At least give them context about what your repo does. This one is a bit meta, so I've also included a "Psuedo-Readme" section below to give you a good example.

# Psuedo-Readme

This code base is a template for Data Science projects.

The entrypoint to using this code is `main.py` which enables the `train`, `test`, and `serve` functionatlity via the `--mode` flag. Each has their own set of unique imputs that help define
the problem in their respective sections.

## `--mode train`

`train` mode lets a user build AND output a new model based on some input data. At the end of the day, a ML project provides certain Algorithm that can be useful. `train` lets users access  that math and save a version of it.

## `--mode test` 

`test` lets a user test a model on specific inputs. Sadly, we limit the default input of this data to a very specific JSON format. You can add any metadata columns you want, but you always need an `X` assuming you include a pretrained model via the `--pretrained_path` and define a model to use it within `main.py`.

```
[
    "id" : 1,
    "X"  : [0.25, "Hello", 250, 0.5, 1, 0, 1]
    "Y"  : "Foo"
]
```

## `--mode serve`
`serve` starts a flask api

### additional arguments

#### `--host`
add a custom hostname
#### `--port`
add a custom port