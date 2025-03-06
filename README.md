# Transmission Tower Project - Image Processing and File Organization

**Name:** Srinivas D  
**Semester:** 6th Sem  
**College:** BNMIT  
**GitHub:** [TransmissionTowerProject](https://github.com/Srinivas23132/TransmissionTowerProject.git)

---

## Project Overview

This project processes a set of transmission tower images provided in both thermal and RGB formats. The primary objectives are to:

- **Organize the Data:**  
  Images are systematically grouped by their capture session, sorted into date-based folders, separated into visible (V) and thermal (T) images, and further organized by GPS coordinates (if available). A consistent naming convention is applied so that each filename includes the capture date, time, GPS coordinates, and a unique identifier.

- **Extract Metadata:**  
  Key metadata (e.g., DateTime, GPS information, and camera details) is extracted from the images using EXIF data. This metadata is compiled into a CSV file to serve as an index linking each image pair to its corresponding details.

- **Analyze the Data (Optional):**  
  A threshold-based hotspot detection algorithm is implemented to identify bright regions (hotspots) in thermal images, which are indicative of potential overheating. Detected hotspots are annotated on the thermal images with red circles, and the corresponding visible images are resized and annotated with green circles for comparison.

- **Optimize the Workflow:**  
  The project proposes an automation script that categorizes and structures image data for easy upload. Additionally, it suggests further improvements for efficient image handling in a web portal, such as integrating cloud-based storage, adaptive thresholding, and real-time processing via APIs.

---

## File Structure

The project is organized as follows:

- **`dataset/transformer/`:**  
  Contains raw input images. Each image pair (thermal and visible) is named with a common base name.

- **`output/`:**  
  Contains processed files, including:
  - **Date-based folders:** Sorted by capture date (e.g., `output/date/2025-02-12/`).
  - **Type-based folders:** All visible images are stored in `output/V_images/` and all thermal images in `output/T_images/`.
  - **GPS-based folders:** When available, images are grouped by GPS coordinates (e.g., `output/GPS/17.9735_76.4514/`).
  - **Hotspot Annotated Images:** Annotated images with hotspots are stored in `output/hotspots/V/` (visible) and `output/hotspots/T/` (thermal).
  - **`metadata.csv`:** A CSV file that compiles all the extracted metadata for each image pair.

---

## How to Run the Project

1. **Prerequisites:**
   - Python 3.x
   - Required Python libraries: `opencv-python`, `Pillow`, `pandas`, `numpy`, `fpdf2`
   - Install the dependencies via:
     ```bash
     pip install -r requirements.txt
     ```

2. **Processing the Data:**
   - Place the raw images in the `dataset/transformer/` directory.
   - Run the main processing script to organize the images, extract metadata, detect hotspots, and generate the CSV file. (The script is included in this repository.)

3. **Reviewing the Output:**
   - The processed images and CSV file will be located in the `output/` directory.
   - The folder structure is automatically created to facilitate easy navigation and further analysis.

---

## Future Improvements

- **Enhanced ROI Refinement:**  
  Focus the hotspot detection exclusively on the transformer to minimize false positives.
- **Adaptive Thresholding:**  
  Implement adaptive methods to improve detection under varying conditions.
- **Cloud Integration:**  
  Automate file uploads to a cloud storage service and integrate real-time processing via web APIs.
- **Detailed GPS Analysis:**  
  Parse more detailed GPS data for improved geospatial analysis.

---

## Conclusion

This project demonstrates a structured approach to organizing, processing, and analyzing transmission tower images. By leveraging techniques such as EXIF metadata extraction, systematic file structuring, and threshold-based hotspot detection, a robust framework has been established. The project lays the groundwork for future automation and real-time monitoring enhancements.

