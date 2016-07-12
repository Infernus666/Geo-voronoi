[![NPM](https://nodei.co/npm/geovoronoi.svg?downloads=true&downloadRank=true)](https://nodei.co/npm/geovoronoi/)&nbsp;&nbsp;


# GeoVoronoi
Voronoi Diagram is partitioning of a plane with n points into convex polygons such that each polygon contains exactly one generating point and every point in a given polygon is closer to its generating point than to any other. A Voronoi diagram is sometimes also known as a Dirichlet tessellation. GeoVoronoi is an extension of Voronoi optimized for geo locations.
 

 
Example usage
-------------
 
 ```javascript
 var sites = [];
 sites.push({x:32.123456, y:-175.654321});
 sites.push({x:32.214365, y:162.123234});
 sites.push({x:32.907856, y:-162.098765});
 sites.push({x:32.019283, y:172.102938});
 sites.push({x:32.444555, y:-176.555444});
 sites.push({x:32.333222, y:-179.222333});

 var geoVoronoi = require('geovoronoi');
 var voronoiGraph = geoVoronoi.getGeoVoronoiGraph(sites);
 ```

Above code will generate generate [this data](https://dl.dropboxusercontent.com/u/49221136/sample_voronoi_graph.txt)

This Voronoi graph will contain following main components

1. **cells:** This contains information for all the polygons(zone) along with their owner sites. A polygon is represented by halfedges (called so as most of them are shared among two adjacent polygons). Each half edge has start and end vertices called va and vb respectively. Set of start vertices of all **half-edges** will be all the vertices of the polygon. Information of cells is enough for basic calculations.
2. **edges:** This contains information about start and end points of all the edges in the resulting Voronoi diagram.
3. **vertices:** This contains information about all the vertices in the resulting Voronoi diagram.

See this blogpost for further explanation [GitHub]()

Also check out [Raycast](https://www.npmjs.com/package/raycast) as it goes very well with Voronoi.