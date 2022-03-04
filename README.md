# numpy-color

A numpy friendly color conversion and manipulation module in python.  
  
Usage:

```
import numpy_color as npc
import PIL
ts = np.linspace(-1, 1, 1920)
ds = np.sqrt(ts**2 + ts.reshape((-1,1))**2)
luma = (np.sin(ds * np.pi) + np.sin(ds * 3 * np.pi)) / 2
chroma = np.full(ds.shape, 1/3)
hue = np.full(ds.shape, 15/18)
alpha = np.ones(ds.shape)
bm = npc.LCh_to_RGB(np.dstack((luma, chroma, hue, alpha)), scale=255, dtype=np.uint8, clamp=(0, 255), errvalue=(0,0,0,0))
PIL.PImage.Pimage.fromarray(bm).show()

```
