# 41934 Advanced BIM, Assaignment 3 Use case
## Group 16: Isabella Vad (s183616) and Amalie Hartvig Jensen (s183619)

**3A**

Goal: The goal of this tool is to provide an overview of LCA results (CO2 emissions) on building elements within a building project from an IFC- file.

Model Use (Bim Uses):  
BIM model which is IFC compatible with the information level comparable with DiKon LOD 200 - 400. 
LCAByg v5.1

**3B**

Process: A process diagram of the use case has been modeled in BPMN.io and is displayed below. 
A *tool* is to be developed, however the tool will be implemented in a workflow consisting of the processes specified below when working with LCA.  
![current use case](diagram_before)
<img src=" diagram_before.svg">

![Use case for proposed tool](diagram_tool)
<img src=" diagram_tool.svg">

Description of the process of the tool:
The expected/identified processes of the use case which appear in the process diagram are described below:
*Establish CO2 benchmark* : Requirements to the building’s level of CO2-emissions are established by the Contractor most likely from looking at reference projects and by complying with requirements on the subject as presented in the Danish Building Regulations effective from 2023 (BR23). 
*Design proposal* : From “Design concepts and requirements” provided by the Contractor, the designers (Architects/Engineers) will develop a design proposal for respective building parts or for the building as a whole and thus generate a BIM model in an IFC-file format as output.  
*Application of tool* : By inputting the IFC-file, the developed tool is expected to extract all relevant building elements and associated data and reorganize it in an excel-sheet in a specific way that is readable to LCAbyg v5.1.
*Convert Excel to JSON file* : As it is possible to integrate the json format directly in LCAbyg v5.1, a simple conversion of the generated output excel file to a json file format is done e.g. using online services.
*JSON import to LCAbyg v5.1* : the generated json file is imported into LCAbyg and results on CO2 emissions are generated and interpreted by the designer (Architect/Engineer). 
*Consult contractor for revision of “Design concepts and requirements”* : If the output CO2 emissions do NOT meet the established project benchmark, the contractor is consulted to check if the benchmark is realistic within the “Design concepts and requirements” of the project. If this is the case, the process loops back to the “Design proposal” phase where architects/engineers would need to adjust the design for a more sustainable design solution that conforms with the CO2 benchmark. 
*Final Design* : If the tool’s output (CO2 emission results from LCAbyg) DOES meet the CO2 benchmark established by the Contractor, the “loop” is broken and a potentially final design of the building project has been found. 

Note that the tool application as proposed in the process diagram above requires that the designers (architects/engineers) are experienced with LCAbyg or at least have knowledge of the interpretation of results in LCAbyg. 

**3C** 
We've filled out the DiKon excel template with the required LOD for our use case in the 5 stages of building execution 
Our proposed tool can be used in all 5 stages hence the LOD varyies accordantly together with the accruacy of the LCA results. 

IFC: 
- The data needed in the IFC-file are all physical elements and respective dimensions, quantities and materials. 
- No external sources are needed in the script of the tool as the “analysis” happens in LCAbyg. 
- Assumptions can be made when being in the early stages. 


**3D**

*Business value:* 
The tool enables designers (architects/engineers) to gain insights on CO2 emissions while they design through simple conversion steps.
This method is less time consuming than the traditional generation of LCA results within LCAbyg. 
Furthermore, this might encourage designers to have an iterative approach to sustainable design already in the early design phases, e.g. by enabling quick comparison on emissions from different material use within the model or by keeping track of continuous CO2 check points.  
As a consequence, application of the tool would possibly reduce the extent of and costs associated with design modifications in late design stages due to exceedance of the established CO2 benchmark. In other words the tool encourages a proactive instead of reactive sustainable design workflow. 
Thus the tool holds great business value in terms of cost and time efficiency.

By generating numbers on CO2-emissions during the design stages, the tool will contribute to inform and support decision making processes towards more sustainable design. This is beneficial as sustainable design increases competitiveness in the modern building industry. 

*Societal value:* 
The topicality of the presented tool originates from the increased focus on sustainable development needed in society which is also reflected onto green transition in the building industry. 
The tool supports sustainable building design, by enabling quick display of CO2-emissions with intent to encourage the more sustainable choice of materials.
By contributing to sustainable building, the tool inevitably provides societal value.
With the coming Danish law regulation starting from 2023 on making LCA an obligatory part of new construction, the tool becomes increasingly interesting.

Additionally, potential cost savings from use of the tool as mentioned above in “Business value” might benefit the user of the building e.g. lowering housing prices.  

**3E**


9. Our tool won't be able to replace the use of LCAByg as it can't generate LCA resutls directly. Thus our tool optimizes the workflow and limits the time used on generating results through LCAbyg. 


10. The development of the tool is expected to follow a somewhat backwards approach. 

Taking starting point in exported json files from a project and associated results in LCAbyg v.5.1. Then we'll understand the hierarchical structure of the json format as generated by LCAbyg. (Looking into the json file guide provided on: https://www.lcabyg.dk/en/vejledning/user-manuals-and-other-tools/). 
From the understading of the structure of the json files we'll make a script that can translate an arbitrary IFC model into similar json files to be uploaded by LCAbyg.
The results are then up to interpretation for the sustainability architects/engineers. 
