---
title: 'Vorgehensweise: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 840a769b0bb322ef7b878a312437c5ec200ab074
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834490"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="4c666-102">Vorgehensweise: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c666-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="4c666-103">In diesem Beispiel wird veranschaulicht, wie die <xref:System.String.Chars%2A> Eigenschaft, um das Zeichen an der angegebenen Position in einer Zeichenfolge zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4c666-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c666-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c666-104">Example</span></span>  
 <span data-ttu-id="4c666-105">Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der diese Zeichen in der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4c666-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="4c666-106">Sie können als ein Array von Zeichen einer Zeichenfolge vorstellen (`Char` Instanzen); Sie können ein bestimmtes Zeichen abrufen, indem Sie auf den Index des Zeichens durch Verweisen der <xref:System.String.Chars%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4c666-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="4c666-107">Die `index` Parameter, der die <xref:System.String.Chars%2A> Eigenschaft ist nullbasiert.</span><span class="sxs-lookup"><span data-stu-id="4c666-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4c666-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="4c666-108">Robust Programming</span></span>  
 <span data-ttu-id="4c666-109">Die <xref:System.String.Chars%2A> Eigenschaft gibt das Zeichen an der angegebenen Position zurück.</span><span class="sxs-lookup"><span data-stu-id="4c666-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="4c666-110">Allerdings können einige Unicode-Zeichen durch mehr als ein Zeichen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4c666-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="4c666-111">Weitere Informationen zum Arbeiten mit Unicode-Zeichen finden Sie unter [Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="4c666-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="4c666-112">Die <xref:System.String.Chars%2A> Eigenschaft löst eine <xref:System.IndexOutOfRangeException> Ausnahme wenn die `index` -Parameter ist größer als oder gleich der Länge der Zeichenfolge ist, oder wenn es kleiner als 0 (null)</span><span class="sxs-lookup"><span data-stu-id="4c666-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c666-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c666-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="4c666-114">Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen</span><span class="sxs-lookup"><span data-stu-id="4c666-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="4c666-115">Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c666-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="4c666-116">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="4c666-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
