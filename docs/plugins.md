# Peatio Plugins v2

Peatio plugins v2 is updated peatio plugin system. We distribute plugins as peatio gems.

## Development

1. List your plugins in Gemfile.plugins.

2. Install plugins `bundle install`.

3. Start your plugin development and integration.

## Build

### Using default Dockerfile

Default Dockerfile has two stages. First stage is base image build and second is installation plugins into base image.

* To build base image run `docker build --target base --tag peatio:base .`.
* To build image with plugins from scratch run `docker build --tag peatio:custom .`

### Using Dockerfile.plugin

If you want to use rubykube base image you can extend it by adding plugins into
`Gemfile.plugin`. You don't need whole peatio repository.

1. Copy `Dockerfile.plugin` and `Gemfile.plugin` into empty directory.

2. List yor plugins in `Gemfile.plugin`.

3. Change base image in `Dockerfile.plugin` (default is rubykube/peatio:latest).

4. Build your custom image `docker build --tag peatio:custom -f Dockerfile.plugin .`