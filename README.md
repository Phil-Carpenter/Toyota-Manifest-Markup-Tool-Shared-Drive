# Automated PDF Manifest Labeling Tool

This project provides a robust Python solution for automatically processing and labeling multi-page PDF manifests, common in manufacturing and logistics operations. It addresses the challenge of handling consolidated PDF files that contain multiple distinct orders, eliminating the need for manual numbering and significantly speeding up documentation workflows.

**Key Features:**

* **Intelligent Data Extraction:** Utilizes PyMuPDF to precisely extract "Dock Code" (e.g., "P1") and "Order Number" (e.g., "2025062605") from specific regions of each PDF page.
* **Dynamic Grouping:** Automatically groups consecutive pages within a single PDF based on matching Dock Code and Order Number combinations.
* **Sequential "Skid X of Y" Numbering:** Applies "Current Skid of Total Skids" numbering to each page within its respective order group (assuming 2 pages per skid unit), ensuring accurate sequential labeling.
* **Network Drive Monitoring:** Employs the `watchdog` library to continuously monitor a designated network shared input folder for new PDF drops.
* **Automated Workflow:** Processes detected PDFs in real-time, saves the newly labeled files to a specified output folder, and deletes the original input files to maintain a clean directory.
* **Robust Logging:** Provides detailed logging for monitoring script activity, debugging extraction issues, and tracking processing status.

**Benefits:**

* **Significant Time Savings:** Automates a previously manual and time-consuming labeling process.
* **Increased Accuracy:** Reduces human error associated with manual numbering.
* **Streamlined Operations:** Ensures manifests are consistently and correctly labeled for smoother internal logistics.
* **Scalable:** Designed to handle large PDF files with numerous order groupings.

**Technologies Used:**

* **Python 3.x**
* **PyMuPDF (fitz):** For high-performance PDF manipulation and text extraction.
* **watchdog:** For real-time file system monitoring.
* **re (Python's regex module):** For advanced text pattern matching during extraction.
