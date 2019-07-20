# Image::Info::XS - Extract meta information from image files.
Perl module for extracting various kind of meta information from image files.
XS implementation of Image::Info. 

##Installation
```shell
perl Makefile.PL
make
make test
make install

#or 

cpan -i Image::Info::XS
```


## Examples
```perl
use Image::Info::XS qw(image_info image_type);

my $info = image_info('image.jpg');
if (!$info) 
{
  die "Can't parse image info\n";
}
my $color = $info->{'color_type'};

my $type = image_type("image.jpg");
if (!$type) 
{
   die "Can't determine file type\n";
}

die "No gif files allowed!" if $type eq 'GIF';
```

## Methods

image_info( $file )

image_info( \$imgdata )

image_type( $file )

image_type( \$imgdata )

## Supported Image Formats

* BMP
* GIF
* ICO
* JPEG
* PNG
* TIFF
* PSD


