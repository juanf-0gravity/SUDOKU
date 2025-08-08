# Sudoku Snap

A small desktop app that reads a Sudoku from a photo and solves it. It uses OpenCV for image processing and a simple ML model for digit recognition.

## Quick start

1. Install Python 3.8+.
2. (Optional) create and activate a virtual environment.
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Run the app:
   ```bash
   python Run.py
   ```

Notes:
- On first run, the recognition model file will be created. This can take a few minutes. Later runs are much faster.
- You can switch between KNN and CNN recognition in `Run.py` via `modeltype`.

## Using the app

- Open the app and pick a photo with a clear Sudoku grid.
- Step through the processing stages or skip straight to the parsed grid.
- Fix any wrong cells, then press Reveal Solution.

Screenshots:

![Home](Screenshots/1.png)
![Stage](Screenshots/4.png)
![Parsed](Screenshots/18.png)
![Solved](Screenshots/19.png)

## How it works (short version)

- Finds and flattens the grid area from the photo.
- Splits the grid into 81 cells and cleans each cell image.
- Recognizes digits with either a KNN classifier or a small CNN.
- Solves the puzzle and draws the result on the canvas.

## Structure

- Entry point: `Run.py`
- UI: `MainUI.py`
- Vision: `BoardExtractor.py`, `RecognizeAndConstructBoard.py`
- Recognition: `KNN.py`, `CNN.py`
- Solver: `SudokuSolver.py`

## License

CC0 1.0 Universal (see `LICENSE`).
