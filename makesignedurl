import boto3
from botocore.config import Config

my_config = Config(
    region_name = 'us-east-1',
    signature_version = 'v4',
    retries = {
        'max_attempts': 10,
        'mode': 'standard'
    }
)

# Get the service client with sigv4 configured
s3 = boto3.client('s3', config=Config(signature_version='s3v4'))

# Generate the URL to get 'key-name' from 'bucket-name'
# URL expires in 604800 seconds (seven days)
url = s3.generate_presigned_url(
    ClientMethod='get_object',
    Params={
        'Bucket': 'bjacobi01bucket',
        'Key': 'README.md'
    },
    ExpiresIn=604800
)

print(url)