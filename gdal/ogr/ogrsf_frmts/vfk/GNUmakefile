include ../../../GDALmake.opt

CORE_OBJ = vfkreader.o vfkreadersqlite.o \
	vfkdatablock.o vfkdatablocksqlite.o \
	vfkpropertydefn.o \
	vfkfeature.o vfkfeaturesqlite.o \
	vfkproperty.o

OGR_OBJ = ogrvfkdriver.o ogrvfkdatasource.o ogrvfklayer.o

OBJ = $(CORE_OBJ) $(OGR_OBJ)

ifeq ($(HAVE_SQLITE),yes)
CPPFLAGS +=  -DHAVE_SQLITE
endif

CPPFLAGS := -I.. -I../.. $(GDAL_INCLUDE) $(SQLITE_INC) $(CPPFLAGS)

default: $(O_OBJ:.o=.$(OBJ_EXT))

clean:
	rm -f *.o $(O_OBJ)

$(O_OBJ): ogr_vfk.h vfkreader.h vfkreaderp.h
