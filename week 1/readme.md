# PIXELS FILE 

- followed code in class
- no adjustments made

# GRADIENT FILE

- followed code in class
- changed colours to pink red and white 
changed code to:
    int red = int(255); // red stays at max
    int green = int(165 * (1 - normalizedY)); // green varies for red to orange
    int blue = int(200 * (1 - normalizedY));
- changed gradient from horizontal to vertical:
    float normalizedY = map(y, 0, height - 1, 0, 1);
