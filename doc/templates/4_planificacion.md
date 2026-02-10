# PROJECT PLANNING PHASE

## Project Objectives

## Project Planning Guide

### Methodology

The methodology selected for the development of this project is the waterfall model. This approach allows each stage to be clearly defined and ensures that the next phase does not begin until the current one has been completed satisfactorily.  

This guarantees a solid foundation at every step, and if any issue arises, the structured approach makes it easier to identify the root cause and correct it efficiently.

### Planned Phases

#### Phase 1: Idea

Description: In this phase, the initial problem is analyzed, needs are identified, and competitors are studied. Based on this analysis, the project idea is defined, the target audience is determined, an initial business model is planned, and the tools to be used are selected.

Hardware/Software Resources: Text editor, web browser, internet access.  
Human Resources: 1 person with a technical profile.  
Duration: 7 days.

---

#### Phase 2: Needs

Description: In this phase, the identified problems are analyzed. The needs to be addressed are defined, and the current context of SMEs is studied. A clear objective is established, along with the means, activities, and resources required to achieve it. Technical and economic feasibility are evaluated, and the solution is compared with competitors to assess strengths and weaknesses.

Hardware/Software Resources: Same as Phase 1.  
Human Resources: 1 person.  
Duration: 7 days.

---

#### Phase 3: Analysis

Description: In this phase, the system’s technical components are defined, selected tools and their interactions are specified. Core functionalities, user types, non-functional requirements, and the solution architecture are established. Potential future improvements are also considered.

Hardware/Software Resources: Same as Phase 2.  
Human Resources: 1 person.  
Duration: 7 days.

---

#### Phase 4: Planning

Description: In this phase, the entire project is structured and organized. Work phases, estimated timelines, resources, and task distribution are defined. A Gantt chart is created for project activities, and an estimated budget is calculated to ensure controlled and realistic development.

Hardware/Software Resources: Text editor, Canva, GanttProject, web browser.  
Human Resources: 1 person.  
Duration: 7 days.

---

#### Phase 5: Design

Description: In this phase, the solution architecture is defined. A main machine integrating services is established, the technical system design is completed, and user interfaces are presented.

Hardware/Software Resources: Text editor, VirtualBox, Ubuntu Server, Prometheus, Grafana.  
Human Resources: 1 person.  
Duration: 7 days.

---

#### Phase 6: Implementation

Description: In this phase, the project plan is put into practice. Virtualization software (VirtualBox) is installed and two machines are created: one centralizes services (Prometheus, Grafana, Alertmanager), while the other acts as the monitored node (Node Exporter). Services are installed, users are created, permissions are adjusted, and configuration between components is completed. Once the system is deployed, testing and verification are performed to identify and resolve potential errors.

Hardware/Software Resources: VirtualBox, Ubuntu Server, Ubuntu Desktop, Prometheus, Grafana, Node Exporter, web browser.  
Human Resources: 1 person.  
Duration: 7 days.

---

#### Phase 7: Presentation

Description: In this final phase, documentation is completed and the oral presentation is prepared. Visual support material is created to assist both the presenter and the audience in understanding the solution. This phase also includes final verification to ensure the solution is ready for testing and demonstration.

Hardware/Software Resources: Text editor, Canva, PowerPoint, VirtualBox.  
Human Resources: 1 person.  
Duration: 15 days.

---

### Gantt Chart

<img src="../img/diagrama_gantt.png">

## Budget

This project was designed to be carried out without incurring direct economic costs. All components used are open-source and free software, eliminating expenses related to licenses or specialized tools. Additionally, the base infrastructure was implemented in a VirtualBox virtual machine, avoiding costs associated with server rentals or hardware acquisition.

Regarding hardware, the project uses my personal workstation, which is fully equipped to perform the expected tasks. The specifications are listed below:

- **Processor**: Intel Core i7-12700K  
- **Motherboard**: ASUS TUF GAMING Z690-PLUS WIFI D4  
- **RAM**: Corsair Vengeance LPX DDR4 3200MHz 32GB (2x16GB) CL16  
- **Graphics card**: Nvidia GeForce RTX 3060 12GB  
- **Primary storage**: Kingston FURY Renegade 2TB SSD NVMe PCIe 4.0 M.2 Gen4  
- **Secondary storage**: Kioxia Exceria G2 1TB SSD NVMe M.2 2280  
- **Cooling**: Tempest Liquid Cooler 360  
- **Power supply**: Corsair RMx RM1000x 1000W  

### Investment / Expense Breakdown:

| Component               | Model / Specification                                          | Approximate Price (€) |
|------------------------|----------------------------------------------------------------|-----------------------|
| **Processor**         | Intel Core i7-12700K – 12 cores / 20 threads                   | 350 €                 |
| **Motherboard**       | ASUS TUF GAMING Z690-PLUS WIFI D4                              | 220 €                 |
| **Cooling**           | Tempest Liquid Cooler 360 – AIO liquid cooling                 | 90 €                  |
| **RAM**               | Corsair Vengeance LPX DDR4 3200MHz 32GB (2x16GB) CL16         | 90 €                  |
| **Primary SSD**       | Kingston FURY Renegade 2TB NVMe PCIe 4.0 M.2 Gen4              | 200 €                 |
| **Secondary SSD**     | Kioxia Exceria G2 1TB NVMe M.2 2280                             | 70 €                  |
| **Power Supply**      | Corsair RMx RM1000x 1000W 80 Plus Gold Modular                 | 160 €                 |
| **TOTAL**             |                                                                | **1,180 €**           |

### Labor Cost

Although this project does not involve direct costs in software or infrastructure, it is important to estimate the time invested in each phase, as this represents the primary consumed resource.  

The following table details the estimated work hours per phase, assuming a daily dedication of 8 hours between April 28 and June 15 (excluding weekends), with an estimated total of 250 hours. Labor cost is calculated at €10 per hour.

| Phase                                | Estimated Hours | Cost (€) |
|--------------------------------------|-----------------|----------|
| 1. Initial Idea and Motivation       | 10 h            | 100 €    |
| 2. Needs Gathering                   | 15 h            | 150 €    |
| 3. System Analysis                   | 25 h            | 250 €    |
| 4. Planning                          | 20 h            | 200 €    |
| 5. Solution Design                   | 30 h            | 300 €    |
| 6. Technical Implementation          | 70 h            | 700 €    |
| 7. Testing and Validation            | 30 h            | 300 €    |
| 9. Technical and Final Documentation | 50 h            | 500 €    |
| **TOTAL**                            | **250 h**       | **2,500 €** |

| **TOTAL PROJECT COST** | | **3,680 €** |
