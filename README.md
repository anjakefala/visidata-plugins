# VisiData Plugins

Custom plugins for https://github.com/saulpw/visidata/

## vds3 - Open Amazon S3 paths and objects directly

### Installation

0. Install VisiData. For now it's preferable to install the prerelease [2.x](http://visidata.org/v2.x/) version, which includes plugin support:

```
pip3 install git+git://github.com/saulpw/visidata@v2.-1
```

Once version 2.x goes stable, the simpler `pip3 install visidata` should be sufficient.

1. Install [s3fs](https://s3fs.readthedocs.io):

```
pip3 install s3fs
```

2. Copy `vds3.py` to your VisiData directory (by default, `~/.visidata`).

3. Add this line to your `~/.visidatarc` file:

```python
from vds3 import openurl_s3
```

### Usage

Because this plugin builds on top of s3fs and boto3, it takes advantage of standard AWS CLI configuration settings.

Be sure that the AWS CLI is [installed](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html) and [configured](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) to point to your desired AWS account.

#### Open a file stored in S3

```
vd 's3://my-bucket/path/to/file.json.gz'
```

#### Browse a bucket's contents

```
vd 's3://my-bucket'
vd 's3://my-bucket/path'
```
