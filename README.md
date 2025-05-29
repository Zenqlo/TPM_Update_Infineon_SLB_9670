# Infineon TPM SLB 9670 TPM Chip FW Update Guide and Links 

**Important Prerequisites:**
* Disable BitLocker and any program using TPM
* Check your OEM vender for updates if available, only use following guide if no OEM updates available
* Use as your own risk.
* May use Windows-To-Go USB to update in Windows if no Windows OS is on the current system.
* If perfer command line or only use Linux, UEFI updates are also available in the package; read readme inside the zip.
* Disable and clear TPM in BIOS

Please use the links below sections to download FW update programs from authorized OEM vendors. 

**Notice:**
* These files are proprietary, and uploading them to a public repository could infringe on the vendors’ intellectual property rights. 
* Public availability for download does not automatically permit redistribution.

## Section A: Early Versions Update to 7.62.3126.0

### Package: "AOM-TPM-9670VH_7.62.3126.0.zip"

This package contains FW upgrade from the following versions to 7.62.3126.0:

### TPM1.2
* 6.40.190.0
* 6.41.197.0
* 6.41.198.0
* 6.42.204.0
* 6.43.243.0

### TPM2.0
* 7.40.2098.0
* 7.41.2375.0
* 7.60.2677.0
* 7.61.2785.0
* 7.61.2789.0
* 7.62.3126.0

Any of the above versions can be updated to 7.62.3126.0

### Update Instructions:
1. Disable BitLocker and any program using TPM
2. Disable and clear TPM in BIOS
3. Navigate to SuperMicro: https://www.supermicro.com/wdl/driver/TPM/
4. Download "AOM-TPM-9670VH_7.62.3126.0.zip"

        Checksums: 
            CRC32: F031BC2F
            MD5: 2C9FC9111EA46200C11DBBB5579DAD36

        Source: https://www.supermicro.com/wdl/driver/TPM/CheckSum.txt

5. Extract all files from zip
6. Locate the correct BIN version needed in `.\Firmware\` folder, put it in `.\Tools\WinPE\Bin\x64\` folder
7. Run CMD with admin rights in `.\Tools\WinPE\Bin\x64\` folder
8. Run `TPMFactoryUpd.exe -h` to learn how to update TPM inside Windows
9. Update with `TPMFactoryUpd.exe -update <update-type> -firmware <Your chosen firmware>`

        Example for update from 7.40.2098.0 to 7.62.3126.0:

        TPMFactoryUpd.exe -update tpm20-emptyplatformauth -firmware TPM20_7.40.2098.0_to_TPM20_7.62.3126.0.BIN

10. Wait for update to finish
11. Restart to BIOS and enable discrete TPM, run tpm.msc to load TPM

## Section B: Update to 7.85.4555.0, from 7.62.3126.0 or later 

### Package: "sp94937.exe"

This package contains FW Upgrade from any of the following versions to 7.85.4555.0:

### TPM1.2
* 6.43.243.0
* 6.43.244.0
* 6.43.245.0
* 6.43.246.0

### TPM2.0
* 7.62.3126.0
* 7.63.3144.0
* 7.63.3353.0
* 7.83.3358.0

### Update Instructions:
1. Download "sp94937.exe" from HP: https://ftp.hp.com/pub/softpaq/sp94501-95000/sp94937.exe

        Checksum:
            MD5: 5e3ac9f6b308ce69cff0d736875af58f

        Source: https://support.hp.com/soar-attachment/923/col106405-ob-272765-1-ob-272765-1_sp94937_releasedoc.html

2. Run "sp94937.exe" and click continue to the end.
3. Navigate to "C:\SWSetup\sp94937" to find firmware files
4. Follow the steps in Section A, download "AOM-TPM-9670VH_7.62.3126.0.zip" and put the chosen firmware file to .\Tools\WinPE\Bin\x64\ the extracted zip folder.
5. Follow the steps in Section A, use "TPMFactoryUpd.exe" to load your firmware
6. Remove "C:\SWSetup" folder

## Section C: For Lenovo M710/M910 Series Only
Official update from 7.62.3126.0 to 7.85.4555.0 for Lenovo

1. Manual download from Lenovo:
https://pcsupport.lenovo.com/us/en/products/desktops-and-all-in-ones/thinkcentre-m-series-desktops/thinkcentre-m910t/downloads/ds557757-tpm-firmware-update-tool-for-windows-11-64-bit-10-64-bit-thinkcentre-and-thinkstation-systems

        Checksums:
        - SHA256: fea68e3652671910d85bfe3cce00b9196d56efac9197e68b7b71c8854e06d341 
        - SHA1: 64bd6711c311abba8e3aebf6ea879b2f167df09e 
        - MD5: 9bb0f5dd77626a2652b5283216c5108b

2. Extract all files from "tpmfwcapupd_m910_tpm20_7.85.4555.0.zip"
3. Follow "Readme.txt" to update in Windows

## Section D: For Lenovo M720/M920 Series Only
Official update from 7.63.3353.0 to 7.85.4555.0 for Lenovo

1. Manual download from Lenovo:
https://pcsupport.lenovo.com/us/en/products/desktops-and-all-in-ones/thinkcentre-m-series-desktops/thinkcentre-m920t/downloads/ds557767-tpm-firmware-update-tool-for-windows-11-64-bit-10-64-bit-thinkcentre-systems

        Checksums:
        - SHA256: 90c31b7ab4a16d9fc6b669fd4910540f574d76f23cd9d343e6f61b278539ef12 
        - SHA1: 8842c59ea6b3cf8ea70d3374882e2886a9e53b5e 
        - MD5: 7faa237ddbd390e51c47b14dfd2b0ec7

2. Extract all files from "tpmfwcapupd_m920_tpm20_7.85.4555.0.zip"
3. Follow "Readme.txt" to update in Windows 
