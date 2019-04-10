# Live Server for Julia

| Status (Linux/Mac) | Status (Windows) | Coverage | Docs |
| :----: | :----: | :----: | :----: |
| [![Build Status](https://travis-ci.org/asprionj/LiveServer.jl.svg?branch=master)](https://travis-ci.org/asprionj/LiveServer.jl) | [![AppVeyor](https://ci.appveyor.com/api/projects/status/github/asprionj/LiveServer.jl?branch=master&svg=true)](https://ci.appveyor.com/project/asprionj/LiveServer-jl) | [![codecov.io](http://codecov.io/github/asprionj/LiveServer.jl/coverage.svg?branch=master)](http://codecov.io/github/asprionj/LiveServer.jl?branch=master) | [![dev-doc](https://img.shields.io/badge/docs-dev-blue.svg)](https://asprionj.github.io/LiveServer.jl/dev/)

This is a simple and lightweight development web-server written in Julia, based on [HTTP.jl](https://github.com/JuliaWeb/HTTP.jl).
It has live-reload capability, i.e. when changing files, every browser (tab) currently displaying a corresponding page is automatically refreshed.

LiveServer is inspired from Python's [`http.server`](https://docs.python.org/3/library/http.server.html) and Node's [`browsersync`](https://www.browsersync.io/).

## Installation

The package is currently unregistered.
To install it in Julia ≥ 1.0, use the package manager with

```julia-repl
] add https://github.com/asprionj/LiveServer.jl
```

## Usage

The main function `LiveServer` exports is `serve` which starts listening to the current folder and makes its content available to a browser.
The following code creates an example directory and serves it:

```julia
julia> using LiveServer
julia> LiveServer.example() # creates an "example/" folder with some files
julia> cd("example")
julia> serve() # starts the local server & the file watching
✓ LiveServer listening on http://localhost:8000/ ...
  (use CTRL+C to shut down)
```

Open a Browser and go to `http://localhost:8000` to see the content being rendered; try modifying files (e.g. `index.html`) to see the changes being rendered immediately in the browser.