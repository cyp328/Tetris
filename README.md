# Tetris
Works exactly like Tetris game in terms of speed progression might be slower than usual but the game works.

Core Architecture Breakdown
1. Board State Representation

The playing field is represented by a 2D array (grid) of fixed rows and columns.

Empty cells contain zeros, while occupied cells hold color or piece ID values.

2. Active Piece Management

The current piece (tetromino) is tracked as an object containing its shape matrix, color, and current grid position (x, y).

Movement (left, right, down) updates the coordinates, while rotation transforms the piece's 2D array matrix.

3. Collision Detection

Before applying any movement or rotation, a collision check tests whether the updated coordinates or matrix overlap with the boundaries of the grid or already-filled cells in the board array.

4. Merging & Line Clearing

When a piece moves down and hits an obstacle, it is merged directly into the board array.

The code scans the board row by row: full rows are removed, higher rows shift down, and score/level counters are updated.

A new piece is spawned at the top. If it immediately collides upon spawning, the game triggers a Game Over.

5. The Game Loop (requestAnimationFrame)

The loop continuously clears the HTML5 canvas and redraws both the fixed board state and the active falling piece.

A timing mechanism updates the piece downward automatically based on a tick interval (which speeds up as levels increase).
