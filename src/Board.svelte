<script>
  import { onMount } from "svelte";

  /////////////////////////////////
  /*
 64SQ "STANDARD" BOARD CONVERTED TO 120SQ BOARD WITH OFFBOARD SQUARES DEFINED AS 100

100 100 100 100 100 100 100 100 100 100   
100 100 100 100 100 100 100 100 100 100 
100 21  22  23  24  25  26  27  28  100 
100 31  32  33  34  35  36  37  38  100 
100 41  42  43  44  45  46  47  48  100 
100 51  52  53  54  55  56  57  58  100 
100 61  62  63  64  65  66  67  68  100 
100 71  72  73  74  75  76  77  78  100
100 81  82  83  84  85  86  87  88  100 
100 91  92  93  94  95  96  97  98  100
100 100 100 100 100 100 100 100 100 100 
100 100 100 100 100 100 100 100 100 100 

NOTE: BOARD IS "UPSIDE DOWN" WITH A1 = 21 AND B8 = 92 AND SO ON.

*/
  ////////////////////////////////////

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

  const SQUARES = {
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
    wP: 1,
    wNg: 2,
    wB: 3,
    wR: 4,
    wQ: 5,
    wK: 6,
    bP: 7,
    bNg: 8,
    bB: 9,
    bR: 10,
    bQ: 11,
    bK: 12,
    NO_PCE: 0,
  };

  //initialize the gameboard with all squares being off board
  let FILES_BOARD = Array(COMPLETE_BOARD_SIZE).fill(SQUARES.OFFBOARD);
  let RANKS_BOARD = Array(COMPLETE_BOARD_SIZE).fill(SQUARES.OFFBOARD);
  let currentFile = FILES.A;
  let currentRank = RANKS.RANK_1;

  onMount(async () => {
    console.log("mounting");
    initBoard();
  });
  function initBoard() {
    console.log("initialising board");
    let sq = SQUARES.A1;

    for (let rank = RANKS.RANK_1; rank <= RANKS.RANK_8; rank++) {
      for (let file = FILES.A; file <= FILES.H; file++) {
        sq = fileRankToSqr(file, rank);
        FILES_BOARD[sq] = file;
        RANKS_BOARD[sq] = rank;
      }
    }
  }
  function fileRankToSqr(file, rank) {
    console.log(21 + file + rank * 10);
    return 21 + file + rank * 10;
  }
</script>

<div class="board_wrapper" />
