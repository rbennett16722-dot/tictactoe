# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-file vanilla JavaScript Tic Tac Toe web application (`tictactoe.html`). No build system, package manager, or external dependencies. Open directly in any browser.

## Running the App

Open `tictactoe.html` in a browser. No server required.

## Architecture

All code lives in `tictactoe.html` — HTML structure, CSS styles, and JavaScript logic are co-located in one file.

**Game state:**
- `board`: 9-element array (`null | 'X' | 'O'`)
- `current`: active player (`'X'` or `'O'`)
- `over`: boolean flag for game-over state
- `scores`: object tracking `{ X, O, D }` wins/draws across games

**Key functions:**
- `init()` — resets board and DOM for a new game (scores persist)
- `checkWinner()` — checks all 8 win patterns; returns `{ winner, line }` on win, `{ winner: null, line: [] }` on draw, or `null` if game continues

**Win detection** uses a static `WINS` array of 8 index triplets (3 rows, 3 columns, 2 diagonals).

**CSS classes on `.cell` elements:** `x`/`o` (player color), `taken` (prevents re-click), `win` (highlights winning line with pulse animation).
