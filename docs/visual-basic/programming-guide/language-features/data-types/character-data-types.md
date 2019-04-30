---
title: Zeichendatentypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 14085172a8f9f9d60af0495a36dd4ba7592213fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907230"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="3f41e-102">Zeichendatentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f41e-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="3f41e-103">Visual Basic bietet *Zeichendatentypen* für den Umgang mit druckbaren und anzeigbaren Zeichen.</span><span class="sxs-lookup"><span data-stu-id="3f41e-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="3f41e-104">Während beide Unicode-Zeichen verarbeiten `Char` ein einzelnes Zeichen enthält, wohingegen `String` eine unbestimmten Anzahl von Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="3f41e-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="3f41e-105">Eine Tabelle mit einer Seite-an-Seite-Vergleich der Visual Basic-Datentypen, finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="3f41e-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="3f41e-106">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3f41e-106">Char Type</span></span>  
 <span data-ttu-id="3f41e-107">Die `Char` -Datentyp ist ein einzelnes 2-Byte (16-Bit) Unicodezeichen.</span><span class="sxs-lookup"><span data-stu-id="3f41e-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="3f41e-108">Wenn eine Variable immer genau ein Zeichen gespeichert werden, deklarieren Sie sie als `Char`.</span><span class="sxs-lookup"><span data-stu-id="3f41e-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="3f41e-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f41e-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="3f41e-110">Jeden möglichen Wert in eine `Char` oder `String` Variable ist ein *Codepunkt*, oder Zeichencode in Unicode-Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="3f41e-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="3f41e-111">Unicode-Zeichen enthalten, die grundlegende ASCII-Zeichensatz, verschiedene andere Buchstaben, Akzente, Währungssymbole, Brüche, diakritische Zeichen und mathematischen und technischen Symbole.</span><span class="sxs-lookup"><span data-stu-id="3f41e-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f41e-112">Unicode-Zeichensatz reserviert, die die Codepunkte D800 bis DFFF (55296 bis 55551 decimal) für *Ersatzpaare*, müssen zwei 16-Bit-Werte, um einen einzelnen Codepunkt darzustellen.</span><span class="sxs-lookup"><span data-stu-id="3f41e-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="3f41e-113">Ein `Char` Variable kann kein Ersatzzeichenpaar enthalten und eine `String` verwendet zwei Positionen für solch ein Paar.</span><span class="sxs-lookup"><span data-stu-id="3f41e-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="3f41e-114">Weitere Informationen finden Sie unter [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="3f41e-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="3f41e-115">String-Typ</span><span class="sxs-lookup"><span data-stu-id="3f41e-115">String Type</span></span>  
 <span data-ttu-id="3f41e-116">Die `String` -Datentyp ist eine Sequenz von NULL oder mehr Unicode-Zeichen der 2-Byte-(16-Bit).</span><span class="sxs-lookup"><span data-stu-id="3f41e-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="3f41e-117">Wenn eine Variable mit eine unbestimmten Anzahl von Zeichen enthalten kann, deklarieren Sie sie als `String`.</span><span class="sxs-lookup"><span data-stu-id="3f41e-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="3f41e-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f41e-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="3f41e-119">Weitere Informationen finden Sie unter [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="3f41e-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f41e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f41e-120">See also</span></span>

- [<span data-ttu-id="3f41e-121">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="3f41e-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="3f41e-122">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="3f41e-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="3f41e-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f41e-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="3f41e-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="3f41e-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="3f41e-125">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f41e-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="3f41e-126">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="3f41e-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="3f41e-127">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="3f41e-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
