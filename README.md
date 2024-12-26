# Genome Assembly Workshop Guide

## Prerequisites

### Option 1: Using Conda (Recommended for Linux users)
1. **Install Miniconda**:
   - Open a terminal (`Ctrl+T`) and run the following command:
     ```bash
     curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
     ```
   - Navigate to your home directory and execute the installation script:
     ```bash
     sh Miniconda3-latest-Linux-x86_64.sh
     ```
     - Approve all prompts by typing `Y`.

2. **Set Up the Conda Environment**:
   - Create and activate an environment for genome assembly:
     ```bash
     conda create -n assembly -y
     conda activate assembly
     ```
   - Configure Conda channels:
     ```bash
     conda config --add channels defaults
     conda config --add channels bioconda
     conda config --add channels conda-forge
     conda config --set channel_priority strict
     ```

3. **Install Required Tools**:
   - Install essential bioinformatics tools within the `assembly` environment:
     ```bash
     conda install -y bioconda::fastqc
     conda install -y bioconda::multiqc
     conda install -y bioconda::trimmomatic
     conda install -y bioconda::spades
     ```
   - **Note for QUAST and RagTag**:
     - If you encounter issues with `quast`, install it in a separate Conda environment:
       ```bash
       conda create -n quast -y
       conda activate quast
       conda install -y bioconda::quast
       ```
     - Similarly, install `ragtag` in its own environment:
       ```bash
       conda create -n ragtag -y
       conda activate ragtag
       conda install -y bioconda::ragtag
       ```

4. **Install GenoVi**:
   - Follow the instructions at the [GenoVi GitHub page](https://github.com/robotoD/GenoVi) to install GenoVi.

5. **Install Python Bio Module**:
   - Run the following command to install the `Bio` module:
     ```bash
     pip3 install Bio
     ```

---

### Option 2: Using Galaxy (Recommended for non-Linux users)
1. **Create a Galaxy Account**:
   - Visit [Galaxy](https://usegalaxy.org/) and sign up for an account.

2. **Upload Data**:
   - Use the provided link to download sample data and the reference genome. Then upload them to your Galaxy account.
   - [Sample and Reference Genome](#)

---

## Notes
- If you're attending the workshop on a Linux system, the Conda-based setup is recommended.
- For MacOS users, the Conda setup can also work. Adjust the Miniconda installer URL accordingly.
- Non-Linux users can leverage Galaxy's user-friendly interface for all steps in the workflow.

Happy assembling!

---
