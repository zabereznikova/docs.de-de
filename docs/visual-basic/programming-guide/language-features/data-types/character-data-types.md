---
title: Zeichendatentypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data types [Visual Basic], character
- String data type, character data types
- character data types [Visual Basic]
- Char data type, character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3407f614d5898f4fccf04e0363ec31669661b60a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="909b7-102">Zeichendatentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="909b7-102">Character Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="909b7-103">bietet *Zeichendatentypen* für den Umgang mit druckbaren und anzeigbaren Zeichen.</span><span class="sxs-lookup"><span data-stu-id="909b7-103"> provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="909b7-104">Während beide mit Unicode-Zeichen Umgang, `Char` ein einzelnes Zeichen enthält, wohingegen `String` eine unbestimmte Anzahl von Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="909b7-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="909b7-105">Für eine Tabelle mit einer Side-by-Side-Vergleich der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen finden Sie in [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="909b7-105">For a table that displays a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="909b7-106">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="909b7-106">Char Type</span></span>  
 <span data-ttu-id="909b7-107">Die `Char` -Datentyp ist ein einzelnes&2; Bytes (16-Bit) Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="909b7-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="909b7-108">Wenn eine Variable immer genau ein Zeichen speichert, deklarieren Sie es als `Char`.</span><span class="sxs-lookup"><span data-stu-id="909b7-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="909b7-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="909b7-109">For example:</span></span>  
  
 <span data-ttu-id="909b7-110">[!code-vb[VbVbalrCharTypes&#1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="909b7-110">[!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="909b7-111">Jeder mögliche Wert einer `Char` oder `String` Variable ist ein *Codepunkt*, Zeichencode im Unicode-Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="909b7-111">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="909b7-112">Unicode-Zeichensatz umfasst den grundlegenden ASCII-Zeichensatz, verschiedene andere Buchstaben, Akzente, Währungssymbole, Bruchzahlen, diakritische Zeichen und mathematische und technische Symbole.</span><span class="sxs-lookup"><span data-stu-id="909b7-112">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="909b7-113">Reserviert die Codepunkte D800 bis DFFF (55296 bis 55551 in Dezimalschreibweise) für den Unicode-Zeichensatz *Ersatzpaare*, die zwei 16-Bit-Werte, um eine Codepunkts erfordern.</span><span class="sxs-lookup"><span data-stu-id="909b7-113">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="909b7-114">Ein `Char` -Variable kann kein Ersatzzeichenpaar und ein `String` verwendet zwei Positionen für solch ein Paar.</span><span class="sxs-lookup"><span data-stu-id="909b7-114">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="909b7-115">Weitere Informationen finden Sie unter [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="909b7-115">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="909b7-116">String-Typ</span><span class="sxs-lookup"><span data-stu-id="909b7-116">String Type</span></span>  
 <span data-ttu-id="909b7-117">Die `String` -Datentyp ist eine Folge von NULL oder mehr&2; Bytes (16-Bit) Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="909b7-117">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="909b7-118">Wenn eine Variable eine unbestimmte Anzahl von Zeichen enthalten kann, deklarieren Sie es als `String`.</span><span class="sxs-lookup"><span data-stu-id="909b7-118">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="909b7-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="909b7-119">For example:</span></span>  
  
 <span data-ttu-id="909b7-120">[!code-vb[VbVbalrCharTypes&#2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="909b7-120">[!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="909b7-121">Weitere Informationen finden Sie unter [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="909b7-121">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909b7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="909b7-122">See Also</span></span>  
 <span data-ttu-id="909b7-123">[Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="909b7-123">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="909b7-124"> [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="909b7-124"> [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
<span data-ttu-id="909b7-125"> [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="909b7-125"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="909b7-126"> [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="909b7-126"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="909b7-127"> [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="909b7-127"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="909b7-128"> [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="909b7-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="909b7-129"> [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="909b7-129"> [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>
