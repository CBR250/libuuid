first_rule: all

all: build

PACKAGE_NAME := libuuid-1.0.3
PACKAGE_DIR  := libuuid-1.0.3

# Configuration
PACKAGE_CONF := \
    --prefix=$(CURDIR)/../../OBJ/ \

test_directory:
	if [ ! -d $(CURDIR)/../../TARGET ]; then \
	   mkdir $(CURDIR)/../../TARGET/; \
	fi
	if [ -d $(CURDIR)/../../TARGET/$(PACKAGE_DIR) ]; then \
	       echo "Folder existed"; \
	else \
	       tar xvf $(CURDIR)/$(PACKAGE_NAME).tar.gz -C $(CURDIR)/../../TARGET/; \
	fi

build_lib: test_directory
	cd $(CURDIR)/../../TARGET/$(PACKAGE_DIR)/  && ./configure  $(PACKAGE_CONF); \

build: build_lib
	$(MAKE) -C $(CURDIR)/../../TARGET/$(PACKAGE_DIR)/ all

install:
	$(MAKE) -C $(CURDIR)/../../TARGET/$(PACKAGE_DIR)/ install
	
config_rule:

clean_rule:

uninstall_rule:
