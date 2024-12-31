# Tumor Detection in Medical Images

This MATLAB script processes and detects tumors in medical images using anisotropic diffusion filtering and morphological operations.

## Prerequisites

- MATLAB
- Image Processing Toolbox

## Usage

1. **Run the script**: Open MATLAB and run the script. It will prompt you to select an input image.
2. **Filter the image**: The script preprocesses the selected image using anisotropic diffusion filtering.
3. **Thresholding**: The filtered image is thresholded to create a binary image.
4. **Morphological operations**: The binary image is processed to detect tumor regions based on solidity and area.
5. **Bounding box**: A bounding box is drawn around the detected tumor.
6. **Tumor outline**: The tumor outline is extracted and displayed.
7. **Overlay outline**: The tumor outline is overlaid on the filtered image in red.

## Steps

### Input

- The script prompts the user to select a `.jpg` image file.

### Filtering

- Anisotropic diffusion filtering is applied to the image to reduce noise while preserving edges.

### Thresholding

- The image is thresholded to create a binary image.

### Morphological Operations

- Label the connected components in the binary image.
- Calculate the solidity and area of each component.
- Identify the component with the highest density and area as the tumor.

### Bounding Box

- Draw a bounding box around the detected tumor.

### Tumor Outline

- Fill the tumor region, erode it, and subtract the eroded image to get the tumor outline.

### Overlay Outline

- Overlay the tumor outline on the filtered image in red.

## Functions

### `anisodiff`

- Performs anisotropic diffusion filtering on the input image.

```matlab
function diff_im = anisodiff(im, num_iter, delta_t, kappa, option)
% im: input image
% num_iter: number of iterations
% delta_t: time step
% kappa: conductance coefficient
% option: diffusion function option (1 or 2)
