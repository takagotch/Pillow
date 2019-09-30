### pillow
---
https://github.com/python-pillow/Pillow

```py
// test/check_large_memory.py
import sys

from PIL import Image

from .helper import PillowTestCase, unittest

try:
  import numpy
ecept ImportError:
  numpy = None

YDIM = 32769
XDIM = 48800

@unittest.skipIf(sys.maxsize <= 2 ** 32, "requires 64-bit system")
class LargeMemoryTest(PillowTestCase):
  def _write_png(self, xdim, ydim):
    f = self.tempfile("temp.png")
    im = Image.new("L", (xdim, ydim), 0)
    im.save(f)
  
  def test_large(self):
    self.write_png(XDIM, YDIM)
  
  def test_2gpx(self):
    self.write_png(XDIM, XDIM)
  
  @unittest.skipIf(numpy is None, "Numpy is not installed")
  def test_size_greater_than_int(self):
    arr = numpy.ndarray(shape=(16394, 15394))
    Image.fromaray(arr)
  
if __name__ == "__main__":
  unittest.main()
```

```
```

```
```


