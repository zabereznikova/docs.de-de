---
title: Zeichendatentypen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1066444ba3a98f26fc2a35135a50b2954c6b992
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="320cc-102">Zeichendatentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="320cc-102">Character Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="320cc-103">bietet *Zeichendatentypen* für den Umgang mit druckbaren und anzeigbaren Zeichen.</span><span class="sxs-lookup"><span data-stu-id="320cc-103"> provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="320cc-104">Während beide mit Unicode-Zeichen verarbeiten `Char` ein einzelnes Zeichen enthält, wohingegen `String` eine unbegrenzte Anzahl von Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="320cc-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="320cc-105">Für eine Tabelle mit einer Seite-an-Seite-Vergleich, der die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Datentypen finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="320cc-105">For a table that displays a side-by-side comparison of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="320cc-106">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="320cc-106">Char Type</span></span>  
 <span data-ttu-id="320cc-107">Die `Char` -Datentyp ist ein einzelnes aus zwei Bytes (16-Bit) Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="320cc-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="320cc-108">Wenn eine Variable immer genau ein Zeichen speichert, deklarieren Sie es als `Char`.</span><span class="sxs-lookup"><span data-stu-id="320cc-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="320cc-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="320cc-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 <span data-ttu-id="320cc-110">Jeder mögliche Wert in einer `Char` oder `String` Variable ist eine *Codepunkt*, oder Zeichencode im Unicode-Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="320cc-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="320cc-111">Unicode-Zeichen umfassen den grundlegenden ASCII-Zeichensatz, verschiedene andere Buchstaben, Akzente, Währungssymbole, Brüche, diakritische Zeichen und mathematische und technische Symbole.</span><span class="sxs-lookup"><span data-stu-id="320cc-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="320cc-112">Reserviert die Codepunkte D800 bis DFFF (55296 über Dezimalstellen 55551) für die Unicode-Zeichensatz *Ersatzpaare*, was erfordern zwei 16-Bit-Werten, die einen einzelnen Codepunkt darstellen.</span><span class="sxs-lookup"><span data-stu-id="320cc-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="320cc-113">Ein `Char` -Variable kann kein Ersatzzeichenpaar, und ein `String` verwendet zwei Positionen für solch ein Paar.</span><span class="sxs-lookup"><span data-stu-id="320cc-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="320cc-114">Weitere Informationen finden Sie unter [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="320cc-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="320cc-115">String-Typ</span><span class="sxs-lookup"><span data-stu-id="320cc-115">String Type</span></span>  
 <span data-ttu-id="320cc-116">Die `String` -Datentyp ist eine Sequenz von NULL oder mehr Unicode-Zeichen für 2-Byte-(16-Bit).</span><span class="sxs-lookup"><span data-stu-id="320cc-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="320cc-117">Wenn eine Variable eine unbestimmten Anzahl von Zeichen enthalten kann, deklarieren Sie es als `String`.</span><span class="sxs-lookup"><span data-stu-id="320cc-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="320cc-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="320cc-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 <span data-ttu-id="320cc-119">Weitere Informationen finden Sie unter [Zeichenfolgendatentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="320cc-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="320cc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="320cc-120">See Also</span></span>  
 [<span data-ttu-id="320cc-121">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="320cc-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="320cc-122">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="320cc-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="320cc-123">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="320cc-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="320cc-124">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="320cc-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="320cc-125">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="320cc-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="320cc-126">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="320cc-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="320cc-127">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="320cc-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
