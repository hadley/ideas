Components for reproducible research
====================================

Extract out the essential components of sweave, so that it's possible to get the same benefits while keeping code and latex completely separate.

* cache_code(code, name, path)

* save_code(fun, name, path)

* save_graphic(code, name, path)
  
  More general form of ggsave that works with any graphics package.
  
  Features:
    - Works out type of device from file name.
    - Takes care of closing dev.off(), even if errors occur.
    - Pulls height and width from current graphics device
