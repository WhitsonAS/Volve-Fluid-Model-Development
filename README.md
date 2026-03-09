# Volve Fluid Model Development
Repository showing the data, predictions, and models for the Volve Field. The model development is based on a single MDT oil sample, and is validated by another MDT oil sample taken at the same time.

The model development utilizes the **whitson<sup>PVT</sup>** software, provided by **whitson**.

Want to learn more about **whitson<sup>PVT</sup>**? Feel free to contact us at support.pvt@whitson.com!

## PVT Data & Fluid Models

The PVT report for two MDT oil samples are given in the original PVT report format (PDF), and has already been converted to an Excel file for easier consumption. The PVT data can be found in the folder named `PVT-Data`.

The fluid models that were generated during the single-sample fluid model development are given in the folder named `Fluid-Models`, and contains EOS models, a black-oil table, an ECL100 RSVD table, and the detailed model slate sample compositions.

## Single Sample Fluid Model Development

The sample selected for this single-sample study is the sample named `6103-MA` and is an MDT oil sample contaminated with an oil-based mud. The sample has a constant composition expansion (CCE), a multi-stage separator (MSS), and a viscotiy experiment.

The second MDT oil sample given in the PVT report is named `4720-EA` and is also oil-based contaminated with only a single CCE experiment performed on it. This sample is used as a validation sample for the single-sample model developed using sample `6103-MA`. 

### Detailed Model Development



https://github.com/user-attachments/assets/2653ffd1-6e8c-4e5a-b3fb-67c70374e8a8

The detailed fluid model development was perforrmed using minimal tuning on the EOS model, but rather using a rigorous C7+ characterization approach, which both splits out the oil-based mud content and creates an initial EOS model simultaneously.

### Fluid Model Validation



https://github.com/user-attachments/assets/fce9266f-872d-4ceb-b4f9-078c7df3c2a9

After having made the single-sample fluid model for the sample named `6103-MA`, we want to validate the fluid model on the second MDT oil sample taken at the same depth at the same time. This sample (`4720-EA`) was then linked to the project where the fluid model was made, and predicted using the `Fluid Model Validation` feature in whitsonPVT.

### Black-Oil PVT Table Generation & Export



https://github.com/user-attachments/assets/2fd7ba8f-098c-4e96-b5aa-71ed2b3b7c26

After having created a detailed fluid model in whitsonPVT, it is simple to generate a black-oil PVT (BOPVT) table. Simply select your sample, the temperature, and the surface process, and whitsonPVT will generate a consistent extrapolated BOPVT table.

The exported black-oil PVT table can be found in the folder named `Fluid-Models`.

### Generate & Export Eclipse RSVD Tables

https://github.com/user-attachments/assets/7104dfd4-e877-43e2-964b-7f891e88cb03

In addition to the BOPVT table, we also want to generate Eclipse RSVD files, which help us initiate the reservoir model.

### Lumped EOS Model Generation & Export

Using a single detailed fluid model, it is easy to generate fit-for-purpose lumped models without the need to re-tune your EOS! Below, we show this process for lumped models that will be used for the surface processing, pipeline similations, and compositional reservoir simulations. All exported files can be found in the folder named `Fluid-Models`.

#### Surface Process Model

https://github.com/user-attachments/assets/f6c80b09-69a3-459d-b25f-fe979c83a981

The surface process model has the requirements that the number of components is less than or equal to 22, and that the lighter components be kept separate. We also fource the isomers for C4 to be grouped together, and the isomers for C5 to be grouped together.

#### Pipeline Model

https://github.com/user-attachments/assets/971b20ae-24bc-42d7-b993-212cefb62aab

The pipeline model does not have any constraints other than the number of components being less than or equal to 15. The export format in this case is to Prosper, so we decide to export to the `.prp` format.

#### Reservoir Model

https://github.com/user-attachments/assets/daf48a8b-e43a-4e2a-8a3f-e2ceec5e0256

For the reservoir model, we want to continue to decrease the number of components to see how few components we can get to. The we want to export the model to ECL300 format. For this case, we need to choose a temperature and a composition.

