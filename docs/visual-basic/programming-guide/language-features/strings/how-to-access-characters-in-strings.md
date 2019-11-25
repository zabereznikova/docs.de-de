---
title: 'Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352465"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="7b3b0-102">Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b3b0-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="7b3b0-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span><span class="sxs-lookup"><span data-stu-id="7b3b0-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b3b0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b3b0-104">Example</span></span>  
 <span data-ttu-id="7b3b0-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span><span class="sxs-lookup"><span data-stu-id="7b3b0-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="7b3b0-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span><span class="sxs-lookup"><span data-stu-id="7b3b0-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="7b3b0-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span><span class="sxs-lookup"><span data-stu-id="7b3b0-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7b3b0-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="7b3b0-108">Robust Programming</span></span>  
 <span data-ttu-id="7b3b0-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span><span class="sxs-lookup"><span data-stu-id="7b3b0-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="7b3b0-110">However, some Unicode characters can be represented by more than one character.</span><span class="sxs-lookup"><span data-stu-id="7b3b0-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="7b3b0-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="7b3b0-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="7b3b0-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span><span class="sxs-lookup"><span data-stu-id="7b3b0-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3b0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b3b0-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="7b3b0-114">Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="7b3b0-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="7b3b0-115">Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b3b0-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="7b3b0-116">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="7b3b0-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
