# drawing
Collaborative online drawing using HTML5 canvas

## User Stories
### Create a new drawing
1. Enter drawing name
2. Click create drawing button
3. Presented with new canvas

### Visit an existing drawing
1. View list of existing drawings
2. Click on one
3. Presented with a canvas rendered with stored drawing

### Draw
1. Visit a drawing
2. Presented with canvas
    - Choose brush size and color
    - Click and drag to draw
    - See changes by other users in realtime

(diagram.png)

## Model
- `stroke` hash with:
    - Mouse positions
    - Canvas drawing styles (hash)

- Ruby:
    - `Drawing` class with `name` and `stroke`s collection
    - `Drawing` is an `ActiveRecord`

## View
- Render `stroke`s onto canvas
- List existing drawings

## Controller
- Javascript:
    - Create strokes from mouse input
    - Send and receive strokes via web socket
    - Pass new strokes to View

- Ruby:
    - Broadcast received strokes to appropriate sockets
    - Regularly save `Drawing`s
