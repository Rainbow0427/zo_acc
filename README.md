## Kerzoo 
 You can use code by running the following.
```bash
# ft
MODEL=facebook/opt-2.7b TASK=SST2 MODE=ft LR=1e-6 EPS=1e-3 STEPS=4000 bash mezo.sh
# lora
MODEL=facebook/opt-2.7b TASK=SST2 MODE=lora LR=1e-6 EPS=1e-3 STEPS=4000 bash mezo.sh

```

## Some tips in training:
* `ZO` is sensitive to hyperparameter settings (including seeds,important!!!).
* For kerzoo, different datasets may need different time for convergence, for r in kernel function, you can use [-1,1] or [-1/2,1/2](greatly recommend) to initialize the interval and gradually shrink as steps increase. Clip constant may need change as model changes.

## How to add kerzoo to my own code?

Our implementation of kerzoo is based on [MeZO](https://github.com/princeton-nlp/MeZO). For the adding parts, please refer to `trainer.py` for details.
