Number of Characters and Additional Sounds at radicals of Qunji Yupian (群籍玉篇/新修絫音引證群籍玉篇)
=======================================================================================================


このデータについて
-------------------

nchars.json は、群籍玉篇における部首冒頭に書かれている収録字数や
添重音 (韻書などから追加された追加音) の数について、
機械読み取りが可能なように加工したファイルです。


About this Data
----------------

nchars.json is machine-readable file based on number of characters and
添重音 (additional sounds based on rime dictionaries etc.) noted at the
head of the radical of Qunji Yupian (群籍玉篇).


ルートオブジェクト
-------------------

ルートオブジェクトは、下に記述する部首情報オブジェクトの配列です。


The Root Object
----------------

The root object is an array of radical information object
(described later).


部首情報オブジェクト
---------------------

次の情報を含む連想配列です。

*	`vol`  
	巻次
*	`radical`  
	部首コード (Q001-Q545 もしくは q001-q036)  
	注: 部首注記の無い q037 は、nchars-raw.txt とは異なり当データに含めていない。
*	`original`  
	注記 (文字列)。  
	ただし、"original" の名称とは裏腹に、最小限の修正を加えている。
	欠損している場合には `null`。
*	`original_raw`  
	注記 (文字列)。  
	上記修正を加えないもの。欠損している場合には `null`。
	次の追加マークアップを行う。
	*	"■": 欠損部分
	*	"x?": おそらく "x" だが、異なる解釈も考えられる。
*	`total`  
	合計字数。  
	"notes" に合計字数を示す "t" キーが含まれる場合、その字数。
	そうでなければ字数に関する注記を合計したもの。
*	`total_old`  
	底本における合計字数 (推定)。  
	"notes" に底本の字数を示す "o" キーが含まれた場合、その字数。
	そうでなければ合計字数から字数に関する合計でない注記を差し引いたもの。
*	`notes`  
	下に示す注記オブジェクトの連想配列。配列のキーは、
	原文の解釈が困難な場合には原文のものを、
	そうでない場合には、次の英文キーを用いる:
	*	`t`: 合計収録字数
	*	`o`: 旧収録字数
	*	`n`: 新収録字数 (出典表記がない場合)
	*	`GJ`: 広集韻 (広集)
	*	`SJ`: 省韻 (省集, 省集韻)
	*	`QY`: 切韻
	*	`JY`: 集韻 (丁公集韻)
	*	`GY`: 広韻
	*	`s`  : 添重音 (字数としては数えない)
	*	`SJs`: 省韻における追加音の数 (字数としては数えない)
	*	`N` : 群籍玉篇の新部首であることを示す表記 (字数は常に 0)


Radical Information Object
---------------------------

This is an associative array including following keys:

*	`vol`  
	Volume number
*	`radical`  
	Radical code (Q001-Q545 or q001-q036)  
	Note: q037 without notes is not included here (unlike nchars-raw.txt).
*	`original`  
	Notes (string).
	Despite its name, minimum amount of modification is made here.
	If this is missing, the value is `null`.
*	`original_raw`  
	Notes (string).
	The original notes without modification.
	If this is missing, the value is `null`.
	This string has following markups:
	*	"■": Missing
	*	"x?": Probably "x" but different interpretation is possible
*	`total`  
	Total number of characters  
	If "notes" has a key of "t" (indicating total number of characters),
	corresponding number of that object. If not, total number of
	characters indicated by "notes" entries.
*	`total_old`  
	Total number of characters in the original text of QJYP (estimated).
	If "notes" has a key of "o" (indicating old number of characters),
	corresponding number of that object. If not, total number of
	characters minus non-total numbers of characters.
*	`notes`  
	An associative array of note object (described below).
	The key is the original caption if exact meaning/source of the note is
	uncertain. If the meaning/source of the note is certain, following
	generic names are used:
	*	`t`: Total number of characters
	*	`o`: Original number of characters (without addition)
	*	`n`: Additional number of characters (without source attribution)
	*	`GJ`: Guang Ji Yun (廣集韻; 廣集)
	*	`SJ`: Sheng Yun or Sheng Ji Yun (省韻; 省集, 省集韻)
	*	`QY`: Qieyun (切韻)
	*	`JY`: Jiyun (丁公集韻)
	*	`GY`: Guangyun (廣韻)
	*	`s`:   Additional sounds (添重音; not number of characters)
	*	`SJs`: Additional sounds in Sheng Yun (省韻; not number of characters)
	*	`N`: Note about additional radical in Qunji Yupian (群籍玉篇) (number is always zero)


注記オブジェクト
-----------------

次の情報を含む連想配列です。

*	`o`  
	順序 (最初の注記が 0、次の注記が 1...)
*	`c`  
	注記のキャプション
*	`n`  
	注記の示す数字


Note Object
------------

This is an associative array including following keys:

*	`o`  
	The order of this note in specific radical (first note: 0, second note: 1...)
*	`c`  
	The caption (or prefix) of the note
*	`n`  
	Number indicated by the note
