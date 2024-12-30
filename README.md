# gormgis

This repository is a fork of the original gormGIS package, modified to provide enhanced PostGIS support for the GORM library in Go.

## Overview
gormGIS adds PostGIS geometric type support to [GORM](https://gorm.io), allowing you to easily work with geographic data in your Go applications using PostgreSQL's PostGIS extension.

## Features
- Support for PostGIS geometric types in GORM models
- Simple and straightforward API
- Compatible with GORM v2
- Supports SRID 4326 (WGS 84) coordinate system

## Supported Types
Currently supported PostGIS types:
- `geometry(Geometry,4326)` - Geometric points with latitude and longitude

## Usage Example

```go
type Location struct {
    ID uint
    Point gormgis.Point `gorm:"type:geometry(Point,4326)"`
}
    // Create a new point
location := Location{
    Point: &gormgis.Point{
        Lng: -73.935242,
        Lat: 40.730610,
},
}
```

## Installation

```bash
go get github.com/9ssi7/gormgis
```


## Modifications from Original
This fork includes several modifications from the original package:
- Simplified type handling
- Focus on Point geometry type
- SRID 4326 specific implementation

## License
Apache License 2.0

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.