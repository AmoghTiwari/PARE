# Debugging Help

## ModuleNotFoundError: No module named 'torchvision.models.utils'
``` (pare_env) amogh@LAPTOP-57KH24AC:~/study/projects/PARE$ python scripts/demo.py --vid_file data/sample_video.mp4 --output_folder logs/demo
Traceback (most recent call last):
  File "scripts/demo.py", line 28, in <module>
    from pare.core.tester import PARETester
  File "./pare/core/tester.py", line 32, in <module>
    from ..models import PARE, HMR
  File "./pare/models/__init__.py", line 1, in <module>
    from .hmr import HMR
  File "./pare/models/hmr.py", line 21, in <module>
    from .backbone import *
  File "./pare/models/backbone/__init__.py", line 2, in <module>
    from .resnet import *
  File "./pare/models/backbone/resnet.py", line 3, in <module>
    from torchvision.models.utils import load_state_dict_from_url
ModuleNotFoundError: No module named 'torchvision.models.utils'
```
Fix it using:
Replace `from torchvision.models.utils import load_state_dict_from_url` with `from torch.hub import load_state_dict_from_url`
