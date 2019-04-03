# CPL-Data
The Common Parts Library is a set of commonly used electronic components for designing and manufacturing connected device products. This library has [CPL for Production](https://octopart.com/common-parts-library/production) and [CPL for Prototyping](https://octopart.com/common-parts-library/prototyping) data in YAML format.

For more information about the Common Parts Library, please check this [page](https://octopart.com/common-parts-library/about). For CAD models in various PCB design tools, refer to individual part detail pages on Octopart such as [this](https://octopart.com/lpc1768fbd100%2C551-nxp+semiconductors-11854624#ecad) one. 

Sign up for Octopart Slack channel [here](https://join-chat.octopart.com/), and share any questions, feedback or thoughts with us there. 

YAML data can be parsed in all the major languages. An example on how to parse the YAML data in Python is shown below. It returns all capacitor MPNs with a value of 1 pF in the CPL for Production:  



```
import yaml
with open('CPL-Data/CPL for Production/Capacitors.yaml', 'r') as f:
    doc = yaml.load(f)

def findmpn(value):
    for row in doc["rows"]:
        if row["extravals"]["Capacitance"] == value:
            for part in row["parts"]:
                print(part["mpn"])


if __name__ == "__main__":
    findmpn("1 pF") 
```
