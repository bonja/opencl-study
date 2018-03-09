
TARGET := hello

CPPOBJDIR := cppobjs

CPPSOURCES := $(wildcard *.cpp)
CPPOBJS := $(CPPSOURCES:%.cpp=$(CPPOBJDIR)/%.o)

CXXFLAGS := -m64 -DUNIX
LDFLAGS := -L/usr/lib64/ -lOpenCL

.PHONY: clean

$(CPPOBJDIR):
	@ mkdir -p $(CPPOBJDIR)

$(CPPOBJS): $(CPPOBJDIR)/%.o: %.cpp
	@echo "compile $@ $<"
	g++ -fPIC $(CXXFLAGS) -c $< -o $@

$(TARGET): $(CPPOBJDIR) $(CPPOBJS)
	g++ -fPIC -o $(TARGET) $(CPPOBJS) $(LDFLAGS) 

clean:
	rm $(TARGET) $(OBJ)
	rm -rf $(CPPOBJDIR)
