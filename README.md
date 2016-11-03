# CPL-Data
The Common Parts Library is a set of commonly used electronic components for designing and manufacturing connected device products. This library has [CPL for Production](https://octopart.com/common-parts-library/production) and [CPL for Prototyping](https://octopart.com/common-parts-library/prototyping) data in YAML format.

For more information about the Common Parts Library, please check out our [blog](https://blog.octopart.com/archives/category/tools/common-parts-library). For symbols and footprints, please refer to SnapEDA's [library](https://snapeda.com/libraries/octopart/common-parts-library/) for PCB Design tools such as Altium Designer, KiCad and Eagle. 

YAML data can be parsed in all the major languages. An example on how to parse the YAML data in Python is shown below. It returns all capacitor MPNs with a value of 1 pF in the CPL for Production:  



```
import yaml
with open('CPL-Data/CPL for Production/Capacitors.yaml', 'r') as f:
    doc = yaml.load(f)

def findmpn(value):
    for row in doc["rows"]:
        if row["extravals"]["Capacitance"] == value:
            for part in row["parts"]:
                print part["mpn"]


if __name__ == "__main__":
    findmpn("1 pF") 
```
