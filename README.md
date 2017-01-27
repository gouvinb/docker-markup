# docker-markup

A Docker image for markup tools (pandoc and latex), command line Interface
for markup tools (pandoc and latex).

## Using the docker image

```bash
docker run --rm -v ${PWD}:/data gouvinb/docker-markup [command]
```

example :

```bash
docker run -it -v `pwd`:/data `id -u` gouvinb/docker-markup pandoc src/file.md -o build/"file.tex"
docker run -it -v `pwd`:/data `id -u` gouvinb/docker-markup xelatex -jobname="file" -synctex=1 -interaction=nonstopmode -file-line-error -output-directory="./build/" ./build/"file.tex"
```

## Building from a docker file

The following will tag and upload a new release. Replace X.Y.Z as appropriate
version.

```bash
docker build -t gouvinb/docker-markup:latest -t gouvinb/docker-markup:X.Y.Z .
docker push gouvinb/docker-markup:latest
docker push gouvinb/docker-markup:X.Y.Z
```

## Feedback

All feedback is welcome. Let me know if you have any suggestions, questions, or
criticisms. If something is not idiomatic to Docker, please let me know know so
we can make it better.

## Contributing

1.  Fork it!
2.  Create your feature branch: `git checkout -b my-new-feature`
3.  Commit your changes: `git commit -am 'Add some feature'`
4.  Push to the branch: `git push origin my-new-feature`
5.  Submit a pull request :D

## LICENSE

Copyright 2016 gouvinb. All rights reserved. Use of this source code is governed
by a BSD-style license that can be found in the LICENSE.md file.
