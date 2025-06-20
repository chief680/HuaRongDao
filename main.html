<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hua Rong Dao - Klotski Puzzle</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            margin: 0;
            padding: 20px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .game-container {
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            text-align: center;
        }

        h1 {
            color: #333;
            margin-bottom: 10px;
            font-size: 2.5em;
        }

        .subtitle {
            color: #666;
            margin-bottom: 30px;
            font-style: italic;
        }

        .game-board {
            display: grid;
            grid-template-columns: repeat(4, 80px);
            grid-template-rows: repeat(5, 80px);
            gap: 2px;
            background: #8B4513;
            border: 4px solid #654321;
            border-radius: 10px;
            padding: 10px;
            margin: 20px auto;
            position: relative;
        }

        .piece {
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 14px;
            cursor: pointer;
            transition: all 0.2s ease;
            box-shadow: 0 4px 8px rgba(0,0,0,0.3);
            user-select: none;
            border: 2px solid rgba(0,0,0,0.2);
        }

        .piece:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.4);
        }

        .piece.cao-cao {
            background: linear-gradient(135deg, #ff6b6b, #ee5a52);
            color: white;
            grid-column: span 2;
            grid-row: span 2;
            font-size: 18px;
        }

        .piece.general {
            background: linear-gradient(135deg, #4ecdc4, #44a08d);
            color: white;
            grid-column: span 1;
            grid-row: span 2;
            font-size: 12px;
        }

        .piece.soldier {
            background: linear-gradient(135deg, #feca57, #ff9ff3);
            color: white;
            grid-column: span 1;
            grid-row: span 1;
            font-size: 12px;
        }

        .piece.horizontal {
            background: linear-gradient(135deg, #a8e6cf, #7fcdcd);
            color: white;
            grid-column: span 2;
            grid-row: span 1;
            font-size: 12px;
        }

        .empty {
            background: transparent;
        }

        .controls {
            margin-top: 20px;
        }

        button {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            margin: 0 10px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
        }

        .moves-counter {
            font-size: 18px;
            margin: 20px 0;
            color: #333;
        }

        .win-message {
            color: #4CAF50;
            font-size: 24px;
            font-weight: bold;
            margin: 20px 0;
        }

        .instructions {
            max-width: 500px;
            margin: 20px auto;
            color: #666;
            font-size: 14px;
            line-height: 1.6;
        }

        .keyboard-help {
            background: #f8f9fa;
            border: 1px solid #dee2e6;
            border-radius: 8px;
            padding: 15px;
            margin: 15px auto;
            max-width: 400px;
            font-size: 12px;
            color: #555;
        }

        .keyboard-help h4 {
            margin: 0 0 10px 0;
            color: #333;
            font-size: 14px;
        }

        .key-combo {
            background: #e9ecef;
            padding: 2px 6px;
            border-radius: 3px;
            font-family: monospace;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="game-container">
        <h1>華容道</h1>
        <div class="subtitle">Hua Rong Dao - Klotski Puzzle</div>
        
        <div class="instructions">
            Help Cao Cao (the red general) escape to the bottom exit! Click pieces to move them into empty spaces. The goal is to get the large red piece to the bottom opening.
        </div>

        <div class="keyboard-help">
            <h4>Keyboard Controls:</h4>
            <div><span class="key-combo">Tab</span> / <span class="key-combo">Shift+Tab</span> - Select next/previous piece</div>
            <div><span class="key-combo">Arrow Keys</span> - Move selected piece (↑↓←→)</div>
            <div><span class="key-combo">Space</span> - Cycle through available moves</div>
            <div><span class="key-combo">R</span> - Reset game</div>
            <div><span class="key-combo">H</span> - Show solution hint</div>
        </div>

        <div class="moves-counter">Moves: <span id="moveCount">0</span></div>
        
        <div class="game-board" id="gameBoard"></div>
        
        <div id="winMessage" class="win-message" style="display: none;">
            🎉 Congratulations! Cao Cao has escaped! 🎉
        </div>
        
        <div class="controls">
            <button onclick="resetGame()">Reset Game</button>
            <button onclick="showSolution()">Show Solution</button>
        </div>
    </div>

    <script>
        // Game state
        let board = [
            ['caocao', 'caocao', '', ''],
            ['caocao', 'caocao', '', ''],
            ['general1', 'horizontal', 'horizontal', 'general2'],
            ['general1', 'soldier1', 'soldier2', 'general2'],
            ['soldier3', '', '', 'soldier4']
        ];

        let pieces = {
            'caocao': { type: 'cao-cao', name: '曹操', width: 2, height: 2 },
            'general1': { type: 'general', name: '关羽', width: 1, height: 2 },
            'general2': { type: 'general', name: '黄忠', width: 1, height: 2 },
            'horizontal': { type: 'horizontal', name: '兵', width: 2, height: 1 },
            'soldier1': { type: 'soldier', name: '兵', width: 1, height: 1 },
            'soldier2': { type: 'soldier', name: '兵', width: 1, height: 1 },
            'soldier3': { type: 'soldier', name: '兵', width: 1, height: 1 },
            'soldier4': { type: 'soldier', name: '兵', width: 1, height: 1 }
        };

        let moveCount = 0;
        let gameWon = false;

        function renderBoard() {
            const gameBoard = document.getElementById('gameBoard');
            gameBoard.innerHTML = '';
            
            // Track which cells have been rendered to avoid duplicates
            const rendered = Array(5).fill().map(() => Array(4).fill(false));
            
            // Create grid cells
            for (let row = 0; row < 5; row++) {
                for (let col = 0; col < 4; col++) {
                    if (rendered[row][col]) continue;
                    
                    const cell = document.createElement('div');
                    const pieceId = board[row][col];
                    
                    if (pieceId && pieces[pieceId]) {
                        const piece = pieces[pieceId];
                        // Only render the piece at its top-left position
                        if (isPieceOrigin(pieceId, row, col)) {
                            cell.className = `piece ${piece.type}`;
                            cell.textContent = piece.name;
                            cell.onclick = () => movePiece(pieceId, row, col);
                            
                            // Highlight selected piece
                            if (selectedPiece === pieceId) {
                                cell.style.border = '3px solid #FFD700';
                                cell.style.boxShadow = '0 0 15px rgba(255, 215, 0, 0.7)';
                            }
                            
                            // Mark all cells occupied by this piece as rendered
                            for (let r = row; r < row + piece.height; r++) {
                                for (let c = col; c < col + piece.width; c++) {
                                    if (r < 5 && c < 4) rendered[r][c] = true;
                                }
                            }
                            
                            // Position the piece using CSS grid
                            cell.style.gridColumn = `${col + 1} / span ${piece.width}`;
                            cell.style.gridRow = `${row + 1} / span ${piece.height}`;
                        }
                    } else {
                        cell.className = 'empty';
                        cell.style.gridColumn = `${col + 1}`;
                        cell.style.gridRow = `${row + 1}`;
                        rendered[row][col] = true;
                        
                        // Show move options for selected piece
                        if (selectedPiece && selectedPosition) {
                            const piece = pieces[selectedPiece];
                            const directions = [
                                {name: 'up', dr: -1, dc: 0, symbol: '↑'},
                                {name: 'down', dr: 1, dc: 0, symbol: '↓'},
                                {name: 'left', dr: 0, dc: -1, symbol: '←'},
                                {name: 'right', dr: 0, dc: 1, symbol: '→'}
                            ];
                            
                            for (let dir of directions) {
                                const targetRow = selectedPosition.row + dir.dr;
                                const targetCol = selectedPosition.col + dir.dc;
                                
                                // Check if this empty cell is where the piece would move to
                                if (canMovePiece(selectedPiece, selectedPosition.row, selectedPosition.col, targetRow, targetCol)) {
                                    // Check if this empty cell is part of the target position
                                    if (row >= targetRow && row < targetRow + piece.height &&
                                        col >= targetCol && col < targetCol + piece.width) {
                                        cell.className = 'empty move-option';
                                        cell.textContent = dir.symbol;
                                        cell.onclick = () => moveToDirection(selectedPiece, selectedPosition.row, selectedPosition.col, dir.name);
                                        cell.style.background = 'rgba(255, 215, 0, 0.3)';
                                        cell.style.cursor = 'pointer';
                                        cell.style.fontSize = '24px';
                                        cell.style.color = '#FFD700';
                                        cell.style.border = '2px solid #FFD700';
                                        break;
                                    }
                                }
                            }
                        }
                    }
                    
                    gameBoard.appendChild(cell);
                }
            }
        }

        function isPieceOrigin(pieceId, row, col) {
            // Check if this is the top-left corner of the piece
            if (row > 0 && board[row-1][col] === pieceId) return false;
            if (col > 0 && board[row][col-1] === pieceId) return false;
            return true;
        }

        let selectedPiece = null;
        let selectedPosition = null;
        let pieceOrder = ['caocao', 'general1', 'general2', 'horizontal', 'soldier1', 'soldier2', 'soldier3', 'soldier4'];
        let currentPieceIndex = 0;

        // Keyboard event handling
        document.addEventListener('keydown', function(event) {
            if (gameWon) return;
            
            // Prevent default behavior for game keys
            if (['ArrowUp', 'ArrowDown', 'ArrowLeft', 'ArrowRight', 'Tab', ' ', 'r', 'R', 'h', 'H'].includes(event.key)) {
                event.preventDefault();
            }
            
            switch(event.key) {
                case 'Tab':
                    if (event.shiftKey) {
                        selectPreviousPiece();
                    } else {
                        selectNextPiece();
                    }
                    break;
                    
                case 'ArrowUp':
                    if (selectedPiece && selectedPosition) {
                        moveToDirection(selectedPiece, selectedPosition.row, selectedPosition.col, 'up');
                    }
                    break;
                    
                case 'ArrowDown':
                    if (selectedPiece && selectedPosition) {
                        moveToDirection(selectedPiece, selectedPosition.row, selectedPosition.col, 'down');
                    }
                    break;
                    
                case 'ArrowLeft':
                    if (selectedPiece && selectedPosition) {
                        moveToDirection(selectedPiece, selectedPosition.row, selectedPosition.col, 'left');
                    }
                    break;
                    
                case 'ArrowRight':
                    if (selectedPiece && selectedPosition) {
                        moveToDirection(selectedPiece, selectedPosition.row, selectedPosition.col, 'right');
                    }
                    break;
                    
                case ' ':
                    cycleAvailableMoves();
                    break;
                    
                case 'r':
                case 'R':
                    resetGame();
                    break;
                    
                case 'h':
                case 'H':
                    showSolution();
                    break;
            }
        });

        function selectNextPiece() {
            currentPieceIndex = (currentPieceIndex + 1) % pieceOrder.length;
            selectPieceByIndex(currentPieceIndex);
        }

        function selectPreviousPiece() {
            currentPieceIndex = (currentPieceIndex - 1 + pieceOrder.length) % pieceOrder.length;
            selectPieceByIndex(currentPieceIndex);
        }

        function selectPieceByIndex(index) {
            const pieceId = pieceOrder[index];
            const position = findPiecePosition(pieceId);
            if (position) {
                selectedPiece = pieceId;
                selectedPosition = position;
                currentPieceIndex = index;
                renderBoard();
            }
        }

        function findPiecePosition(pieceId) {
            for (let row = 0; row < 5; row++) {
                for (let col = 0; col < 4; col++) {
                    if (board[row][col] === pieceId && isPieceOrigin(pieceId, row, col)) {
                        return {row, col};
                    }
                }
            }
            return null;
        }

        function cycleAvailableMoves() {
            if (!selectedPiece || !selectedPosition) {
                selectNextPiece();
                return;
            }
            
            const directions = ['up', 'down', 'left', 'right'];
            for (let dir of directions) {
                if (canMoveInDirection(selectedPiece, selectedPosition.row, selectedPosition.col, dir)) {
                    moveToDirection(selectedPiece, selectedPosition.row, selectedPosition.col, dir);
                    break;
                }
            }
        }

        function canMoveInDirection(pieceId, row, col, direction) {
            const directions = {
                'up': [-1, 0],
                'down': [1, 0], 
                'left': [0, -1],
                'right': [0, 1]
            };
            
            const [dr, dc] = directions[direction];
            const newRow = row + dr;
            const newCol = col + dc;
            
            return canMovePiece(pieceId, row, col, newRow, newCol);
        }

        function movePiece(pieceId, row, col) {
            if (gameWon) return;
            
            // If clicking the same piece, deselect it
            if (selectedPiece === pieceId) {
                selectedPiece = null;
                selectedPosition = null;
                renderBoard();
                return;
            }
            
            // Select the piece and show possible moves
            selectedPiece = pieceId;
            selectedPosition = {row, col};
            
            // Update current piece index for keyboard navigation
            currentPieceIndex = pieceOrder.indexOf(pieceId);
            renderBoard();
        }

        function moveToDirection(pieceId, row, col, direction) {
            if (gameWon) return;
            
            const directions = {
                'up': [-1, 0],
                'down': [1, 0], 
                'left': [0, -1],
                'right': [0, 1]
            };
            
            const [dr, dc] = directions[direction];
            const newRow = row + dr;
            const newCol = col + dc;
            
            if (canMovePiece(pieceId, row, col, newRow, newCol)) {
                // Clear old position
                clearPiece(pieceId);
                // Set new position
                placePiece(pieceId, newRow, newCol);
                
                moveCount++;
                document.getElementById('moveCount').textContent = moveCount;
                selectedPiece = null;
                selectedPosition = null;
                renderBoard();
                checkWin();
            }
        }

        function canMovePiece(pieceId, oldRow, oldCol, newRow, newCol) {
            const piece = pieces[pieceId];
            
            // Check bounds
            if (newRow < 0 || newRow + piece.height > 5 || 
                newCol < 0 || newCol + piece.width > 4) {
                return false;
            }
            
            // Temporarily clear the piece from its current position
            const tempBoard = board.map(row => [...row]);
            for (let r = 0; r < 5; r++) {
                for (let c = 0; c < 4; c++) {
                    if (tempBoard[r][c] === pieceId) {
                        tempBoard[r][c] = '';
                    }
                }
            }
            
            // Check if new position is empty
            for (let r = newRow; r < newRow + piece.height; r++) {
                for (let c = newCol; c < newCol + piece.width; c++) {
                    if (tempBoard[r][c] !== '') {
                        return false;
                    }
                }
            }
            
            return true;
        }

        function clearPiece(pieceId) {
            for (let r = 0; r < 5; r++) {
                for (let c = 0; c < 4; c++) {
                    if (board[r][c] === pieceId) {
                        board[r][c] = '';
                    }
                }
            }
        }

        function placePiece(pieceId, row, col) {
            const piece = pieces[pieceId];
            for (let r = row; r < row + piece.height; r++) {
                for (let c = col; c < col + piece.width; c++) {
                    board[r][c] = pieceId;
                }
            }
        }

        function checkWin() {
            // Check if Cao Cao is at the bottom exit (row 3-4, col 1-2)
            if (board[3][1] === 'caocao' && board[3][2] === 'caocao' &&
                board[4][1] === 'caocao' && board[4][2] === 'caocao') {
                gameWon = true;
                document.getElementById('winMessage').style.display = 'block';
            }
        }

        function resetGame() {
            board = [
                ['caocao', 'caocao', '', ''],
                ['caocao', 'caocao', '', ''],
                ['general1', 'horizontal', 'horizontal', 'general2'],
                ['general1', 'soldier1', 'soldier2', 'general2'],
                ['soldier3', '', '', 'soldier4']
            ];
            
            moveCount = 0;
            gameWon = false;
            selectedPiece = null;
            selectedPosition = null;
            currentPieceIndex = 0;
            document.getElementById('moveCount').textContent = moveCount;
            document.getElementById('winMessage').style.display = 'none';
            renderBoard();
        }

        function showSolution() {
            alert('The minimum solution requires 81 moves! Try different strategies:\n\n1. Move the small soldiers first to create space\n2. Use the vertical generals to help create pathways\n3. Work systematically to clear a path for Cao Cao\n4. Be patient - this is one of the most challenging puzzles!');
        }

        // Initialize game
        renderBoard();
    </script>
</body>
</html>
