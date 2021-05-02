<script>
  const COMPLETE_BOARD_SIZE = 120;
  const STANDARD_BOARD_SIZE = 64;
  const FILES = {
    A: 0,
    B: 1,
    C: 2,
    D: 3,
    E: 4,
    F: 5,
    G: 6,
    H: 7,
    NO_FILE: 8,
  };
  const RANKS = {
    RANK_1: 0,
    RANK_2: 1,
    RANK_3: 2,
    RANK_4: 3,
    RANK_5: 4,
    RANK_6: 5,
    RANK_7: 6,
    RANK_8: 7,
    NO_RANK: 8,
  };

  const KEY_SQRS = {
    A1: 21,
    B1: 22,
    C1: 23,
    D1: 24,
    E1: 25,
    F1: 26,
    G1: 27,
    H1: 28,
    A8: 91,
    B8: 92,
    C8: 93,
    D8: 94,
    E8: 95,
    F8: 96,
    G8: 97,
    H8: 98,
    NO_SQR: 99,
    OFFBOARD: 100,
  }; //To make it easier for ourselves with edge checking and placement and move validation.

  const COLORS = { WHITE: 0, BLACK: 1, BOTH: 2 };

  const PIECE_TYPES = {
    wP: 0,
    wNg: 1,
    wB: 2,
    wR: 3,
    wQ: 4,
    wK: 5,
    bP: 6,
    bNg: 7,
    bB: 8,
    bR: 9,
    bQ: 10,
    bK: 11,
    NO_PCE: 12,
  };
  //initialize the gameboard with all squares being off board
  export let Board = Array(COMPLETE_BOARD_SIZE).fill(KEY_SQRS.OFFBOARD);

  function rankFileToSqr(file, rank) {
    return 21 + file + rank * 10;
  }
</script>

<div class="board_wrapper" />
