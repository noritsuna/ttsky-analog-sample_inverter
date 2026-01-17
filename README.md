![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg)

# Tiny Tapeout Analog Project Sample
This is a sample project for the analog circuit of the TinyTapeout SKY130.  


# Set up the Development Environment
## Using the ISHI-Kai's setup script

- [ISHI-Kai setup script](https://github.com/ishi-kai/OpenEDA-PDK_SetupScript)


- Execute the following command on the command line.  
```
git clone https://github.com/ishi-kai/OpenEDA-PDK_SetupScript
cd OpenEDA-PDK_SetupScript
bash eda-setup.sh
bash pdk_sky130-setup.sh
```


## Using the ISHI-Kai's WSL Image
- [Image for WSL version of SKY130 (TinyTapeout)](https://www.noritsuna.jp/download/ubuntu2204_ishi-kai_EDA.WSL_SKY130.tar.xz)
    - ID: ishi-kai
    - Pass: ishi-kai

### Installing WSL Image
`wsl --import-in-place ubuntu2204_ishi-kai_EDA .\ubuntu2204_ishi-kai_EDA\ext4.vhdx`

The above command will be recognised. To execute it, please use the included "ubuntu2204_ishi-kai_EDA.lnk".  


### Deleting WSL Image
Please note that image files will also be deleted.  

`wsl --unregister ubuntu2204_ishi-kai_EDA`


# Create a Submission File
Since it must be executed on magic, please launch magic.  
- If you created the GDS file using Klayout, please read it as a GDS file.


## Delete "metX.pin" layers
Please delete all label pin layers added for PEX.  


## Make a LEF file
- If created with Klayout, flatten it.  
- Execute the following command on the magic command line.  

`lef write ../lef/tt_um_project_name.lef -pinonly`


## Make a Submission GDS file
- Execute the following command on the magic command line.  

`gds write tt_um_project_name.gds`
