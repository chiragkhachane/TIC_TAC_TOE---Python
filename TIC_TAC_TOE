import random


def disp_board(board):
    print(board[7] + '  | ' + board[8] + '  | ' + board[9])
    print('-----------')
    print(board[4] + '  | ' + board[5] + '  | ' + board[6])
    print('-----------')
    print(board[1] + '  | ' + board[2] + '  | ' + board[3])


def player_input():
    '''
    OUTPUT : (PLAYER1_MARKER , PLAYER2_MARKER)
    :return:
    '''

    # Marker is X or O
    marker = ''

    while marker != 'X' and marker != 'O':
        marker = input('Player1 choose "X" or "O" :').upper()

        if marker == 'X':
            return ('X', 'O')
        else:
            return ('O', 'X')


def place_marker(board, marker, pos):
    board[pos] = marker


def win_check(board, mark):
    return (
            (board[1] == board[2] == board[3] == mark) or
            (board[4] == board[5] == board[6] == mark) or
            (board[7] == board[8] == board[9] == mark) or
            (board[7] == board[4] == board[1] == mark) or
            (board[8] == board[5] == board[2] == mark) or
            (board[9] == board[6] == board[3] == mark) or
            (board[7] == board[5] == board[3] == mark) or
            (board[9] == board[1] == board[5] == mark))


def space_check(board, pos):
    return board[pos] == ' '


def full_space_check(board):
    for i in range(1, 10):
        if board[i] == ' ':
            return False

    return True


def place_choice(board):
    pos = int(input('Choose position (1-9) :'))
    return pos


def replay():
    choice = input('DO you want to replay (YES/NO)? :').upper()

    if choice == 'YES':
        return True
    else:
        return False


def choose_first():
    flip = random.randint(0, 1)

    if flip == '1':
        return 'Player 1'
    else:
        return 'Player 2'


# def TIC_TAC_TOE():

while True:
    # Play the Game
    board1 = [' '] * 10
    player1_marker, player2_marker = player_input()
    turn = choose_first()
    print(turn + 'will go first ')

    ready = input('Ready to play( y/n) :').upper()
    if ready == 'Y':
        game_on = True
    else:
        game_on = False

    while game_on:
        if turn == 'Player 1':
            disp_board(board1)  # Display board
            position = place_choice(board1)  # Take input Position
            place_marker(board1, player1_marker, position)  # Place marker at Position

            if win_check(board1, player1_marker):
                disp_board(board1)
                print('Player 1 has Won!')
                game_on = False
            else:
                if full_space_check(board1):
                    disp_board(board1)
                    print('It is a Draw')
                    game_on = False
                else:
                    turn = 'Player 2'


        else:

            disp_board(board1)  # Display board
            position = place_choice(board1)  # Take input Position
            place_marker(board1, player2_marker, position)  # Place marker at Position

            if win_check(board1, player2_marker):
                disp_board(board1)
                print('Player 2 has Won!')
                game_on = False
            else:
                if full_space_check(board1):
                    disp_board(board1)
                    print('It is a Draw')
                    game_on = False
                else:
                    turn = 'Player 1'

    if not replay():
        break

print(' ')

