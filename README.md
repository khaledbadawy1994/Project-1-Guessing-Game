# Project-1-Guessing-Game

def create_empty_board():
  board = [[1,2,3],
           [4,5,6],
           [7,8,9]]
  for row in board:
    for col in row:
     print(col, end='\t')
    print('\n')
    
create_empty_board()

board = [[1,2,3],
           [4,5,6],
           [7,8,9]]  # position  6  > board[1][2]
           
for row in board:
    for col in row:
        print(col, end='\t')
    print('\n')
    
def show_board(board):
  for row in board:
    for col in row:
    print(col, end='\t')
    print('\n')    
board = [[1,2,3],[4,'x',6],[7,8,9]]
show_board(board)

def set_players():
  from random import choice
  player1 = choice(['X','O'])
  if player1 == 'O':
    player2 = 'X'
  else:
    player2 ='O'
  return player1, player2
  
set_players()

def take_input(board, player):
  while True:
    player_input = input('Please Enter a number between 1,9 represents an empty position:     ')
    if player_input == '1' and board[0][0].isdigit() :
      board[0][0] = player
      break
    elif player_input == '2' and board[0][1].isdigit():
      board[0][1] = player
      break
    elif player_input == '3' and board[0][2].isdigit():
      board[0][2] = player
      break
    elif player_input == '4' and board[1][0].isdigit():
      board[1][0] = player
      break
    elif player_input == '5' and board[1][1].isdigit():
      board[1][1] = player
      break
    elif player_input == '6' and board[1][2].isdigit():
      board[1][2] = player
      break
    elif player_input == '7' and board[2][0].isdigit():
      board[2][0] = player
      break
    elif player_input == '8' and board[2][1].isdigit():
      board[2][1] = player
      break
    elif player_input == '9' and board[2][2].isdigit():
      board[2][2] = player
      break
    else:
      print('Invalid Choice')
      continue
      
  show_board(board)
  
board = [['1','2','3'],['4','X','6'],['7','8','9']]
player ='O'
take_input(board, player)

Please Enter a number between 1,9 represents an empty position:     

Please Enter a number between 1,9 represents an empty position:   

def check_full_board(board):
  for row in board:
   for col in row:
     if col.isdigit():
        return False
  return True
  
board =[['o','x','x'],['4','x','0'],['x','0','x']]

def check_win(board):
  return board[0][0] == board[0][1] == board[0][2] or \
         board[1][0] == board[1][1] == board[1][2] or \
         board[2][0] == board[2][1] == board[2][2] or \
         board[0][0] == board[1][0] == board[2][0] or \
         board[0][1] == board[1][1] == board[2][1] or \
         board[0][2] == board[1][2] == board[2][2] or \
         board[0][0] == board[1][1] == board[2][2] or \
         board[0][2] == board[1][1] == board[2][0]
board = [['o','x','x'],['o','o','x'],['x','o','9']]
show_board(board)
check_win(board)

def play():
  player1, player2 = set_players()
  print("Player1 :  ", player1)
  print("Player2 :  ", player2, '\n')
  board = [['1','2','3'],['4','5','6'],['7','8','9']]
  show_board(board)
  while True:
    for player in [player1, player2]:
      print(f"{player} turn")
      take_input(board, player)
      if check_win(board):
        print(f"{player} wins")
        break
      if check_full_board(board):
        print('Game Finished. Draw!')
        break
    if check_win(board):
        break
    if check_full_board(board):
    
play()
