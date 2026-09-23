def write_readme():
    content = """# Localization of Mobile Robot using ArUco Marker

## The Challenge
1. Indoor robots need to know WHERE they are.
2. GPS FAILS inside buildings.
3. Existing solutions are EXPENSIVE or INACCURATE.

**Comparison of Existing Methods:**
| Method | Accuracy | Cost | Drift |
|---|---|---|---|
| GPS | 5-10m | Medium | No (outdoor) |
| LIDAR | 1-3cm | VERY HIGH | No |
| Wheel Odometry | 5-10% error | Low | YES |
| **Our Solution** | **1-3cm** | **LOW** | **NO** |

**Goal:** Low-cost, drift-free indoor localization.

## What are ArUco Markers?
* Binary square fiducial markers.
* Like QR code but SIMPLER.
* Each marker has:
    * Black border for easy detection.
    * Unique internal pattern = ID number.
* Developed by University of Cordoba (ArUco).

**Key Features:**
1. Unique ID for each marker.
2. Sub-pixel corner detection.
3. Works under partial occlusion.
4. Real-time pose estimation.

## System Architecture

### Hardware Components
| Component | Specification |
|---|---|
| Camera | IMX219-83 (8 MP, using one lens, CSI interface) |
| Processing Unit | Raspberry Pi 4 (4 GB/8 GB RAM, with cooling case) |
| Robot Platform | Differential drive with ArUco marker (5-10 cm) |
| Network | TP-Link Router (Wi-Fi/Ethernet, DHCP) |
| Display | Laptop with RealVNC Viewer |

### Software Tools Used
| Software Tool | Primary Purpose |
|---|---|
| Python 3 | Programming and algorithm implementation |
| OpenCV (with contrib) | Image processing and ArUco marker detection |
| ArUco Module | Marker identification and pose estimation (X, Y, Z) |
| RealVNC Server/Viewer | Remote desktop access to Raspberry Pi |
| Raspberry Pi OS | Operating system on Raspberry Pi 4 |

## Software Pipeline Workflow

1. **Initialize Camera:** Initializes IMX219 camera, captures frames at 15 fps.
2. **Image Preprocessing:** Converts to grayscale, applies noise reduction.
3. **ArUco Detection:** Detects markers using OpenCV, extracts corners and ID.
4. **Pose Estimation:** Computes translation vector $t=[X,Y,Z]^T$ via PnP.
5. **Visualization:** Displays live feed with axes and coordinates via RealVNC.

## Real-World Applications
1. **Warehouse Automation:** Robots transport goods in warehouses (Amazon, Flipkart). Markers fixed at positions for navigation.
2. **Autonomous Delivery Robots:** Food/package delivery in campuses and hospitals. Markers in corridors guide the robot.
3. **Drone Navigation (Indoor):** GPS-denied environments. Markers on floor/walls for positioning.
4. **Augmented Reality:** Camera pose estimation. Virtual objects placed accurately in real world.
5. **Indoor Navigation Systems:** Hospitals, airports, large buildings. Robots navigate where GPS fails.

## Advantages and Future Scope
| Advantages | Future Scope |
|---|---|
| Low Cost | Integration with SLAM |
| Easy Deployment | AI-based Navigation |
| High Accuracy (indoor) | Multi-Robot Coordination |
| Real-Time Processing | Improved Robustness |
| No Drift | IoT Integration |

## Conclusion
Successfully designed and implemented a low-cost, vision-based localization system for indoor mobile robots using ArUco markers.

**Key Achievements:**
* Designed low-cost vision-based localization system.
* Uses overhead camera + ArUco markers.
* Real-time pose estimation (x, y, z).
* No drift - accurate positioning.

## Bibliography
1. Thrun, S., Burgard, W., Fox, D. Probabilistic Robotics. MIT Press, 2005.
2. Siegwart, R., Nourbakhsh, I., Scaramuzza, D. Introduction to Autonomous Mobile Robots. MIT Press, 2011.
3. Garrido-Jurado, S. et al. "Automatic generation and detection of highly reliable fiducial markers under occlusion." Pattern Recognition, Elsevier, 2014.
4. Bradski, G., Kaehler, A. Learning OpenCV: Computer Vision with the OpenCV Library. O'Reilly Media.
5. OpenCV Official Documentation. Available at: https://opencv.org.
"""
    
    file_path = "/tmp/README.md"
    with open(file_path, "w") as f:
        f.write(content)
        
    print(f"[file-tag: {file_path}]")

write_readme()
