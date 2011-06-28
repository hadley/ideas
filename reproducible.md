Components for reproducible research
====================================

Extract out the essential components of sweave, so that it's possible to get the same benefits while keeping code and latex completely separate - instead of reproducibility being driven from the latex, make it driven from the code.  Sourcing your analysis code also outputs all selected pieces for inclusion into a latex document.

* cache(code, path)

* save_code(name, code, path)

* save_graphic(name, code, path)
  
  More general form of ggsave that works with any graphics package.
  
  Features:
    - Works out type of device from file name.
    - Takes care of closing dev.off(), even if errors occur.
    - Pulls height and width from current graphics device

Should be composable so you can easily save code, cache and save graphics.  

Should be able to specify output types.

Should provide output drivers for evaluate (plain text, html and latex).  (Extracts this out of decumar so it only does parsing of comments out of latex and leaves everything else to evaluate and reproducr)

Global settings control where objects are saved and what type of output. Should provide a wrapper that evaluates code with specified settings in place.