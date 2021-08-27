This is a python library to receive data from ifm O3M Lidars through Ethernet.
Currently only the main data channel (8) is implemented.

This code prints every first point of the scan.
```python
    ip = "169.254.160.76"
    port = 42000
    buffer_size = 1460
    lidar = O3MLidar(ip, port, buffer_size, output_mode="point_cloud")

    i = 0

    while True:
        point_cloud = lidar.next()
        if len(point_cloud) > 0:
            print(i, lidar.next()[0])
            i += 1
```