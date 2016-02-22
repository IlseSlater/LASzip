As before the LiDAR points are compressed in completely independent chunks that default to 50,000 points per chunk. Each chunk can be decompressed "on its own" once the start byte is know. As before the first point of each chunk is stored raw. The attributes of all following points are broken into several layers. Only the first layer containing the x and y coordinates (and a few pieces of information) is mandatory to be read  mandartory. The remaining layers containing independently useful attributes such as elevation, intensity, GPS times, colors, point source ID, classifications and flags do not necessarily need to be read from disk and be decompressed.

Chunk Layout:
-------------
1) Raw point [30 - 68 (or more) bytes]
2) Number of remaining points [4 bytes]
3) XY layer
  a) Number of bytes in XY layer [4 bytes]
  b) bytes for XY layer
4) Z layer
  a) Number of bytes in Z layer [4 bytes]
  b) bytes for Z layer
5) intensity layer
  a) Number of bytes in intensity layer [4 bytes]
  b) bytes for intensity layer
6) classification and flags layer
  a) Number of bytes in classification and flags layer [4 bytes]
  b) bytes for classification and flags layer
7) point source ID layer
  a) Number of bytes in point source ID layer [4 bytes]
  b) bytes for point source ID layer
8) user data layer
  a) Number of bytes in user data layer [4 bytes]
  b) bytes for user data layer
9) GPS time stamp layer
  a) Number of bytes in GPS time stamp layer [4 bytes]
  b) bytes for GPS time stamp layer
10) RGB layer
  a) Number of bytes in RGB layer [4 bytes]
  b) bytes for RGB layer
11) NIR layer
  a) Number of bytes in NIR layer [4 bytes]
  b) bytes for NIR layer
12) WavePacket layer
  a) Number of bytes in WavePacket layer [4 bytes]
  b) bytes for WavePacket layer
13) ExtraBytes layer
  a) Number of bytes in ExtraBytes layer [4 bytes]
  b) bytes for ExtraBytes layer