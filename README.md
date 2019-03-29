# Layout-Design-of-an-8x8-SRAM-array
The project is about building an 8-row by 8-bit SRAM memory array, using 65nm CMOS technology. Using a 3-to-8 decoder, the SRAM array is accessed by a 3-bit address. The SRAM cells are designed to achieve lowest power consumption and suitable static noise margin, while operating at 100 MHz Read &amp; Write cycles. The test-bench, the implementation, and the layout of the SRAM array and the decoder are done using Cadence Virtuoso’s Analog-Design Environment (ADE). Static Noise Margin plots &amp; calculation are obtained through Matlab scripts.<br/>
<br/>
## System Block Diagram
![Slide2](https://user-images.githubusercontent.com/27668656/55211574-d8cac100-51a9-11e9-8345-f443d01c8c7c.JPG)

## 6T SRAM Cell Design
### 1) Static Noise Margin
Use the Read & the Write testbenches on Virtuoso to sweep Vout against Vin, & save the waveforms as csv files. 
Then, SNM is found by running the Matlab script "snm.m" for Read SNM & "snm_write.m" for Write SNM. 
The idea is to draw 45 degree lines that intersect with the 2 characteristic curves of the SRAM cell obtained from Virtuoso's csv files. The intersections are found using "InterX.m" script (https://github.com/mattools/matGeom/blob/master/matGeom/polygons2d/private/InterX.m)<br/> & the longest diagonal between the characteristic curves is used to draw the SNM squares.<br/> <br/>
Check this document for more on how to find the SNM of the SRAM cell:<br/>
https://www.researchgate.net/file.PostFileLoader.html?id=54be4ae2d2fd64fb0d8b45cf&assetKey=AS%3A273675910090788%401442260829994 <br/><br/>
![Read SNM](https://user-images.githubusercontent.com/27668656/55212962-05350c00-51af-11e9-843f-4e41a78781e0.png)
![Write SNM](https://user-images.githubusercontent.com/27668656/55213132-9e642280-51af-11e9-8ed1-b9fe4fbab234.png)
(You can just download my Matlab folders that include the csv files & Matlab scripts, & run "snm.m" & "snm_write.m" on Matlab to see the output as an example) <br/>

### 2) Transient Simulations
![Transient Test](https://user-images.githubusercontent.com/27668656/55213492-a40e3800-51b0-11e9-84b5-b157aec59dba.png)<br/>

## 3-to-8 Decoder
![Slide7](https://user-images.githubusercontent.com/27668656/55213643-27c82480-51b1-11e9-937f-543d1e646df7.JPG)<br/>

## Whole System's Layout
![WholeLayout0](https://user-images.githubusercontent.com/27668656/55213729-783f8200-51b1-11e9-9fd0-a85754b970ef.png)
 
---------------------------------

# References
- EE224 Material:<br/>
https://drive.google.com/drive/folders/1Zzhp3N0b08uaHG6FsoPNOPavNcZDvxHt?usp=sharing <br/>
- Project's drive:<br/>
https://drive.google.com/drive/folders/1NHy1KgwGcolrpJ8-mpBILm4kuQtalKxd?usp=sharing <br/>
- Video on how to do layout on Cadence Virtuoso:<br/>
https://www.youtube.com/watch?v=W5aglIZuel4
