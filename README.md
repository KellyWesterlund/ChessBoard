# ChessBoard
Check to see if a chessboard is valid
board = {'h1': 'bKing', 'c6': 'wQueen', 'g2': 'bBishop', 'h5': 'bQueen', 'e3': 'wKing'}

def isValidChessBoard(board):
    chessBoard = {'a1': ' ', 'a2': ' ', 'a3': ' ', 'a5': ' ', 'a6': ' ', 'a7': ' ', 'a8': ' ',
            'b1': ' ', 'b2': ' ', 'b3': ' ', 'b5': ' ', 'b6': ' ', 'b7': ' ', 'b8': ' ',
            'c1': ' ', 'c2': ' ', 'c3': ' ', 'c5': ' ', 'c6': ' ', 'c7': ' ', 'c8': ' ',
            'd1': ' ', 'd2': ' ', 'd3': ' ', 'd5': ' ', 'd6': ' ', 'd7': ' ', 'd8': ' ',
            'e1': ' ', 'e2': ' ', 'e3': ' ', 'e5': ' ', 'e6': ' ', 'e7': ' ', 'e8': ' ',
            'f1': ' ', 'f2': ' ', 'f3': ' ', 'f5': ' ', 'f6': ' ', 'f7': ' ', 'f8': ' ',
            'g1': ' ', 'g2': ' ', 'g3': ' ', 'g5': ' ', 'g6': ' ', 'g7': ' ', 'g8': ' ',
            'h1': ' ', 'h2': ' ', 'h3': ' ', 'h5': ' ', 'h6': ' ', 'h7': ' ', 'h8': ' ',}
    
    # This section checks to see if the spaces in the board would actually be spaces on a real chess board
    for spaces in list(board):
        if spaces not in chessBoard.keys():
            return False

    #This section will test to see if there are too many pieces of one type or another in the test board
    whiteTeam = 0    
    blackTeam = 0
    if 'wQueen' in board.values():
        values = list(board.values())
        wQueen = values.count('wQueen')
        if wQueen > 1:
            print('Invalid Board, too many white Queens')
            return False
        else:
            whiteTeam += wQueen
    if 'bQueen' in board.values():
        values = list(board.values())
        bQueen = values.count('bQueen')
        if bQueen > 1:
            print('Invalid Board, too many black Queens')
            return False
        else:
            blackTeam += wQueen

    if 'wBishop' in board.values():
        values = list(board.values())
        wBishop = values.count('wBishop')
        if wBishop > 2:
            print('Invalid Board, too many white Bishops')
            return False
        else:
            whiteTeam += wBishop
    if 'bBishop' in board.values():
        values = list(board.values())
        bBishop = values.count('bBishop')
        if bBishop > 2:
            print('Invalid Board, too many black Bishops')
            return False
        else:
            blackTeam += bBishop

    if 'wKnight' in board.values():
        values = list(board.values())
        wKnight = values.count('wKnight')
        if wKnight > 2:
            print('Invalid Board, too many white Knights')
            return False
        else:
            whiteTeam += wKnight
    if 'bKnight' in board.values():
        values = list(board.values())
        bKnight = values.count('bKnight')
        if bKnight > 2:
            print('Invalid Board, too many black Knights')
            return False
        else:
            blackTeam += bKnight

    if 'wRook' in board.values():
        values = list(board.values())
        wRook = values.count('wRook')
        if wRook > 2:
            print('Invalid Board, too many white Rooks')
            return False
        else:
            whiteTeam += wRook
    if 'bRook' in board.values():
        values = list(board.values())
        bRook = values.count('bRook')
        if bRook > 2:
            print('Invalid Board, too many black Rooks')
            return False
        else:
            blackTeam += bRook

    if 'wPawn' in board.values():
        values = list(board.values())
        wPawn = values.count('wPawn')
        if wPawn > 8:
            print('Invalid Board, too many white Pawns')
            return False
        else:
            whiteTeam += wPawn
    if 'bpawn' in board.values():
        values = list(board.values())
        bPawn = values.count('bPawn')
        if bPawn > 8:
            print('Invalid Board, too many black Pawns')
            return False
        else:
            blackTeam += bPawn

    if 'wKing' in board.values():
        if 'bKing' in board.values():
            return True
        else:
            whiteTeam += 1
            print('White Team Wins!')

    else:
        if 'bKing' in board.values():
            if False:
                return False
            else:
                blackTeam += 1
                print('Black Team Wins!')
    
    if whiteTeam > 16:
        return False
    if blackTeam > 16:
        return False
