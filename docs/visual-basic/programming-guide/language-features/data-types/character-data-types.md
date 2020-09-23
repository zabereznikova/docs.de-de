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
ms.openlocfilehash: 5fde5eff40d83bdd7d90cd611bd6749106db6e16
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077175"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="8fa7c-102">Zeichendatentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fa7c-102">Character Data Types (Visual Basic)</span></span>

<span data-ttu-id="8fa7c-103">Visual Basic stellt *Zeichen Datentypen* für das Behandeln von druckbaren und darstellbaren Zeichen bereit.</span><span class="sxs-lookup"><span data-stu-id="8fa7c-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="8fa7c-104">Obwohl beide Unicode-Zeichen `Char` enthalten, enthält ein einzelnes Zeichen, wohingegen `String` eine unbegrenzte Anzahl von Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="8fa7c-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="8fa7c-105">Eine Tabelle, in der ein paralleler Vergleich der Visual Basic-Datentypen angezeigt wird, finden Sie unter [Datentypen](../../../language-reference/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="8fa7c-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="8fa7c-106">Char-Typ</span><span class="sxs-lookup"><span data-stu-id="8fa7c-106">Char Type</span></span>  

 <span data-ttu-id="8fa7c-107">Der- `Char` Datentyp ist ein einzelnes 2-Byte-Unicode-Zeichen (16 Bit).</span><span class="sxs-lookup"><span data-stu-id="8fa7c-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="8fa7c-108">Wenn eine Variable immer genau ein Zeichen speichert, deklarieren Sie Sie als `Char` .</span><span class="sxs-lookup"><span data-stu-id="8fa7c-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="8fa7c-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8fa7c-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="8fa7c-110">Jeder mögliche Wert in einer- `Char` oder- `String` Variablen ist ein *Codepunkt*oder Zeichencode im Unicode-Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="8fa7c-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="8fa7c-111">Unicode-Zeichen umfassen den grundlegenden ASCII-Zeichensatz, verschiedene andere alphabetische Buchstaben, Akzente, Währungssymbole, Bruchzeichen, Diakritik und mathematische und technische Symbole.</span><span class="sxs-lookup"><span data-stu-id="8fa7c-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8fa7c-112">Der Unicode-Zeichensatz reserviert die Code Punkte D800 und durch DFFF (55296 bis 55551 Decimal) für *Ersatz Zeichenpaare*, bei denen 2 16-Bit-Werte erforderlich sind, um einen einzelnen Codepunkt darzustellen.</span><span class="sxs-lookup"><span data-stu-id="8fa7c-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="8fa7c-113">Eine `Char` Variable kann kein Ersatz Zeichenpaar enthalten, und eine `String` verwendet zwei Positionen, um ein solches Paar zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8fa7c-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="8fa7c-114">Weitere Informationen finden Sie unter [Char-Datentyp](../../../language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="8fa7c-114">For more information, see [Char Data Type](../../../language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="8fa7c-115">Zeichenfolgentyp</span><span class="sxs-lookup"><span data-stu-id="8fa7c-115">String Type</span></span>  

 <span data-ttu-id="8fa7c-116">Der- `String` Datentyp ist eine Sequenz von NULL oder mehr 2-Byte-Unicode-Zeichen (16 Bit).</span><span class="sxs-lookup"><span data-stu-id="8fa7c-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="8fa7c-117">Wenn eine Variable eine unbestimmte Anzahl von Zeichen enthalten kann, deklarieren Sie Sie als `String` .</span><span class="sxs-lookup"><span data-stu-id="8fa7c-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="8fa7c-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8fa7c-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="8fa7c-119">Weitere Informationen finden Sie unter [String Data Type](../../../language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="8fa7c-119">For more information, see [String Data Type](../../../language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa7c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fa7c-120">See also</span></span>

- [<span data-ttu-id="8fa7c-121">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="8fa7c-121">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="8fa7c-122">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="8fa7c-122">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="8fa7c-123">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fa7c-123">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="8fa7c-124">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="8fa7c-124">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="8fa7c-125">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8fa7c-125">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="8fa7c-126">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="8fa7c-126">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="8fa7c-127">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="8fa7c-127">Type Characters</span></span>](type-characters.md)
