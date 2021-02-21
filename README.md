# homework-for-goldcattle-s-python-class
def get_pixel_at(pixel_grid, i, j):
    """
    Returns the pixel in pixel_grid at row i and column j (zero-indexed).
    Returns 0 if i or j is out of bounds for the given pixel_grid.
    Returns 0 if i or j is a negative value.
    """
    if i < 0 or j < 0:
        return 0
    elif i > len(pixel_grid)-1:
        return 0
    elif j > len(pixel_grid[0])-1:
        return 0
    else:
        return pixel_grid[i][j]





def average_of_surrounding(pixel_grid, n, m):
    """
    Returns the unweighted average of the values of the pixel at row i
    and column j and the eight pixels surrounding it.
    """
    
    pixel_sum = 0
    integer = get_pixel_at(pixel_grid, n, m)
    integer1 = get_pixel_at(pixel_grid, n-1, m-1)
    integer2 = get_pixel_at(pixel_grid, n-1, m)
    integer3 = get_pixel_at(pixel_grid, n-1, m+1)
    integer4 = get_pixel_at(pixel_grid, n, m-1)
    integer5 = get_pixel_at(pixel_grid, n, m+1)
    integer6 = get_pixel_at(pixel_grid, n+1, m-1)
    integer7 = get_pixel_at(pixel_grid, n+1, m)
    integer8 = get_pixel_at(pixel_grid, n+1, m+1)
    pixel_sum += integer + integer1 + integer2 + integer3 + integer4 + integer5 + integer6 + integer7 + integer8
    return pixel_sum // 9


def blur(pixel_grid):
    """
    Given pixel_grid (a grid of pixels), returns a new grid of pixels
    that is the result of blurring pixel_grid. In the output grid,
    each pixel is the average of that pixel and its eight neighbors in
    the input grid.
    """
    blurred_grid = []

    rows = len(pixel_grid)
    columns = len(pixel_grid[0])
    for a in range(rows):
        for k in range(columns):
            number = average_of_surrounding(pixel_grid,a,k)
            blurred_grid.append(number)

    # The returned grid should contain NEW lists and not any copies
    # of parts of pixel_grid. See Problem 4 on the spec for more on this.
    return blurred_grid
test_grid = [
    [1,2,3],
    [4,5,6],
    [7,8,9]
]
print(blur(test_grid))
