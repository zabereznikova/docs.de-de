---
title: 'Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 48507cade639660e6ce36697975d09fb29206c20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649151"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="f7976-102">Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7976-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="f7976-103">In diesem Beispiel wird veranschaulicht, wie die <xref:System.String.Chars%2A> -Eigenschaft auf das Zeichen an der angegebenen Position in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f7976-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7976-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7976-104">Example</span></span>  
 <span data-ttu-id="f7976-105">Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der diese Zeichen innerhalb der Zeichenfolge zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7976-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="f7976-106">Sie können eine Zeichenfolge vorstellen, als ein Array von Zeichen (`Char` Instanzen); Sie können ein bestimmtes Zeichen abrufen, indem Sie auf den Index des Zeichens durch Verweisen der <xref:System.String.Chars%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f7976-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 <span data-ttu-id="f7976-107">Die `index` Parameter von der <xref:System.String.Chars%2A> Eigenschaft ist nullbasiert.</span><span class="sxs-lookup"><span data-stu-id="f7976-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f7976-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="f7976-108">Robust Programming</span></span>  
 <span data-ttu-id="f7976-109">Die <xref:System.String.Chars%2A> Eigenschaft gibt das Zeichen an der angegebenen Position zurück.</span><span class="sxs-lookup"><span data-stu-id="f7976-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="f7976-110">Allerdings können einige Unicode-Zeichen durch mehr als ein Zeichen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f7976-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="f7976-111">Weitere Informationen zum Arbeiten mit Unicode-Zeichen, finden Sie unter [wie: Konvertieren einer Zeichenfolge in ein Array von Zeichen](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="f7976-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="f7976-112">Die <xref:System.String.Chars%2A> -Eigenschaft löst eine <xref:System.IndexOutOfRangeException> Ausnahme wenn die `index` Parameter ist größer als oder gleich der Länge der Zeichenfolge ist, oder wenn er kleiner als 0 (null)</span><span class="sxs-lookup"><span data-stu-id="f7976-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7976-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7976-113">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 [<span data-ttu-id="f7976-114">Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="f7976-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [<span data-ttu-id="f7976-115">Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7976-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="f7976-116">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f7976-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
