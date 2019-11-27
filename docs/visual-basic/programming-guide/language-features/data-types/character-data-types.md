---
title: Zeichendatentypen
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: edd1d3a41dd878649aa422256b7858d7bce366e1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346394"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="b61b1-102">Zeichendatentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b61b1-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="b61b1-103">Visual Basic stellt *Zeichen Datentypen* für das Behandeln von druckbaren und darstellbaren Zeichen bereit.</span><span class="sxs-lookup"><span data-stu-id="b61b1-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="b61b1-104">Obwohl beide Unicode-Zeichen enthalten, enthält `Char` ein einzelnes Zeichen, während `String` eine unbestimmte Anzahl von Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="b61b1-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="b61b1-105">Eine Tabelle, in der ein paralleler Vergleich der Visual Basic-Datentypen angezeigt wird, finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="b61b1-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="b61b1-106">Char-Typ</span><span class="sxs-lookup"><span data-stu-id="b61b1-106">Char Type</span></span>  
 <span data-ttu-id="b61b1-107">Der `Char`-Datentyp ist ein einzelnes 2-Byte-Unicode-Zeichen (16 Bit).</span><span class="sxs-lookup"><span data-stu-id="b61b1-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="b61b1-108">Wenn eine Variable immer genau ein Zeichen speichert, deklarieren Sie Sie als `Char`.</span><span class="sxs-lookup"><span data-stu-id="b61b1-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="b61b1-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b61b1-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="b61b1-110">Jeder mögliche Wert in einer `Char`-oder `String` Variablen ist ein *Codepunkt*oder Zeichencode im Unicode-Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="b61b1-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="b61b1-111">Unicode-Zeichen umfassen den grundlegenden ASCII-Zeichensatz, verschiedene andere alphabetische Buchstaben, Akzente, Währungssymbole, Bruchzeichen, Diakritik und mathematische und technische Symbole.</span><span class="sxs-lookup"><span data-stu-id="b61b1-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b61b1-112">Der Unicode-Zeichensatz reserviert die Code Punkte D800 und durch DFFF (55296 bis 55551 Decimal) für *Ersatz Zeichenpaare*, bei denen 2 16-Bit-Werte erforderlich sind, um einen einzelnen Codepunkt darzustellen.</span><span class="sxs-lookup"><span data-stu-id="b61b1-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="b61b1-113">Eine `Char` Variable darf kein Ersatz Zeichenpaar enthalten, und ein `String` verwendet zwei Positionen, um ein solches Paar zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b61b1-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="b61b1-114">Weitere Informationen finden Sie unter [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="b61b1-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="b61b1-115">Zeichen Folgentyp</span><span class="sxs-lookup"><span data-stu-id="b61b1-115">String Type</span></span>  
 <span data-ttu-id="b61b1-116">Der `String`-Datentyp ist eine Sequenz von NULL oder mehr Unicode-Zeichen (16 Bit), die aus zwei Bytes bestehen.</span><span class="sxs-lookup"><span data-stu-id="b61b1-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="b61b1-117">Wenn eine Variable eine unbestimmte Anzahl von Zeichen enthalten kann, deklarieren Sie Sie als `String`.</span><span class="sxs-lookup"><span data-stu-id="b61b1-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="b61b1-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b61b1-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="b61b1-119">Weitere Informationen finden Sie unter [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="b61b1-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61b1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b61b1-120">See also</span></span>

- [<span data-ttu-id="b61b1-121">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="b61b1-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="b61b1-122">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="b61b1-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="b61b1-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b61b1-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="b61b1-124">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="b61b1-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="b61b1-125">Typkonvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b61b1-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="b61b1-126">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="b61b1-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="b61b1-127">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="b61b1-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
