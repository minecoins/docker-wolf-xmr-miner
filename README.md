# What is wolf-xmr-miner?

wolf-xmr-miner is Wolf's OpenCL XMR Miner for AMD GPUs.

## Links

- [Discussion](https://forum.getmonero.org/9/work-in-progress/2400/open-source-amd-miner-by-wolf0)
- [Source Code](https://github.com/wolf9466/wolf-xmr-miner)
- [Dockerfile](https://github.com/minecoins/docker-wolf-xmr-miner)

# How to use this image

## Configuration file

Create `xmr.conf` configuration file and adapt to your need before running.
You can copy file from a container:

```console
$ docker run --name some-wolf-xmr-miner-config minecoins/wolf-xmr-miner
$ docker cp some-wolf-xmr-miner-config:/opt/wolf-xmr-miner/xmr.conf .
$ docker stop some-wolf-xmr-miner-config
$ docker rm some-wolf-xmr-miner-config
```

or copy example from [GitHub](https://github.com/wolf9466/wolf-xmr-miner/blob/master/xmr.conf).

Use a GPU index of -1 to run on the CPU. The only other config item needed is "threads", but rawIntensity and worksize must still be set to a non-zero value.

## Running

Run in background:

```console
$ docker run -td --name some-wolf-xmr-miner -v "$PWD"/xmr.conf:/opt/wolf-xmr-miner/xmr.conf minecoins/wolf-xmr-miner xmr.conf
```

Fetch logs of a container:

```console
$ docker logs some-wolf-xmr-miner
```

# Donations

Donations for work on dockerizing are accepted at:

- BTC: `1NUMFM6UTv9iRVVzjsfhzbAGjwNxQRA8Qz`
- XMR: `49TfoHGd6apXxNQTSHrMBq891vH6JiHmZHbz5Vx36nLRbz6WgcJunTtgcxnoG6snKFeGhAJB5LjyAEnvhBgCs5MtEgML3LU`
