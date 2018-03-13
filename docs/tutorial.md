## Graphical User Interface

You can start the FMPy GUI with `python -m fmpy.gui`

![FMPy GUI](Rectifier_GUI.png)

## Python

To follow this example download `Rectifier.fmu` for your platform by clicking on the respective link:
[Linux](https://trac.fmi-standard.org/export/HEAD/branches/public/Test_FMUs/FMI_2.0/CoSimulation/linux64/MapleSim/2017/Rectifier/Rectifier.fmu),
[macOS](https://trac.fmi-standard.org/export/HEAD/branches/public/Test_FMUs/FMI_2.0/CoSimulation/darwin64/MapleSim/2017/Rectifier/Rectifier.fmu),
[Windows (32-bit)](https://trac.fmi-standard.org/export/HEAD/branches/public/Test_FMUs/FMI_2.0/CoSimulation/win32/MapleSim/2017/Rectifier/Rectifier.fmu),
[Windows (64-bit)](https://trac.fmi-standard.org/export/HEAD/branches/public/Test_FMUs/FMI_2.0/CoSimulation/win64/MapleSim/2017/Rectifier/Rectifier.fmu).
Change to the folder where you've saved the FMU and open a Python prompt.

```
>>> from fmpy import *
>>> fmu = 'Rectifier.fmu'
>>> dump(fmu)  # get information

Model Info

  FMI Version       2.0
  Model Name        Rectifier
  Description       Model Rectifier
  Platforms         win64
  Continuous States 4
  Event Indicators  6
  Variables         63
  Generation Tool   MapleSim (1267140/1267140/1267140)
  Generation Date   2017-10-04T12:07:10Z

Default Experiment

  Stop Time         0.1
  Step Size         1e-07

Variables (input, output)

Name                Causality          Start Value  Unit     Description
outputs             output        282.842712474619  V        Rectifier1.Capacitor1.v
>>> result = simulate_fmu(fmu)         # simulate the FMU
>>> from fmpy.util import plot_result  # import the plot function
>>> plot_result(result)                # plot two variables
```

![Rectifier Result](Rectifier_result.png)

## Command Line Interface

To get information about an FMU directly from the command line change to the folder where you've saved the
FMU and enter

```bash
fmpy info Rectifier.fmu
```

Simulate the FMU and plot the results

```bash
fmpy simulate Rectifier.fmu --show-plot
```

Get more information about the available options

```bash
fmpy --help
```

## Advanced Usage

To learn more about how to use FMPy in you own scripts take a look at the
[coupled_clutches.py](https://github.com/CATIA-Systems/FMPy/blob/master/fmpy/examples/coupled_clutches.py),
[custom_input.py](https://github.com/CATIA-Systems/FMPy/blob/master/fmpy/examples/custom_input.py) and
[parameter_variation.py](https://github.com/CATIA-Systems/FMPy/blob/master/fmpy/examples/parameter_variation.py) examples.
