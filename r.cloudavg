#!/usr/bin/env python
########################################################################
#
# MODULE:       r.cloudavg
# AUTHOR:       Devin Whitney
# PURPOSE:      Averages two months of Landsat data to remove cloud cover
# COPYRIGHT:    (C) 2017 Devin Whitney
#               This program is free software under the GNU General
#               Public License (>=v2). Read the file COPYING that
#               comes with GRASS for details.
#
########################################################################

#%module
#% description: Averages two months of Landsat data
#% keyword: Landsat
#% keyword: raster
#% keyword: cloud
#%end
#%option G_OPT_R_INPUT
#% key: rastera
#% description: Month One Red Band
#%end
#%option G_OPT_R_INPUT
#% key: rasterb
#% description: Month One Blue Band
#%end
#%option G_OPT_R_INPUT
#% key: rasterc
#% description: Month One Green Band
#%end
#%option G_OPT_R_INPUT
#% key: rasterd
#% description: Month Two Red Band
#%end
#%option G_OPT_R_INPUT
#% key: rastere
#% description: Month Two Blue Band
#%end
#%option G_OPT_R_INPUT
#% key: rasterf
#% description: Month Two Green Band
#%end
#%option G_OPT_R_OUTPUT
#% key: routput
#% description: Red Output
#%end
#%option G_OPT_R_OUTPUT
#% key: boutput
#% description: Blue Output
#%end
#%option G_OPT_R_OUTPUT
#% key: goutput
#% description: Green Output
#%end

import sys

import grass.script as gscript

def main():
	options, flags = gscript.parser()
	rastera = options['rastera']
	rasterb = options['rasterb']
	rasterc = options['rasterc']
	rasterd = options['rasterd']
	rastere = options['rastere']
	rasterf = options['rasterf']
	routput = options['routput']
	boutput = options['boutput']
	goutput = options['goutput']

	gscript.mapcalc('{rr} = (({a} + {d})/2)'.format(rr=routput, a=rastera, d=rasterd))
	gscript.mapcalc('{rb} = (({b} + {e})/2)'.format(rb=boutput, b=rasterb, e=rastere))
	gscript.mapcalc('{rg} = (({c} + {f})/2)'.format(rg=goutput, c=rasterc, f=rasterf))

	return 0
if __name__ == "__main__":
	sys.exit(main())
	