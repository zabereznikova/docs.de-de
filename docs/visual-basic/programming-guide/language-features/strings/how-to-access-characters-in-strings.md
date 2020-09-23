---
title: 'Vorgehensweise: Zugreifen auf Zeichen in Zeichenfolgen'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 4ea37c4393a8ece5513327b22c6c0ba4b027c781
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059183"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="60af4-102">Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60af4-102">How to: Access Characters in Strings in Visual Basic</span></span>

<span data-ttu-id="60af4-103">In diesem Beispiel wird veranschaulicht, wie die-Eigenschaft verwendet wird <xref:System.String.Chars%2A> , um auf das Zeichen an der angegebenen Position in einer Zeichenfolge zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="60af4-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60af4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60af4-104">Example</span></span>  

 <span data-ttu-id="60af4-105">Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen dieser Zeichen in der Zeichenfolge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="60af4-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="60af4-106">Sie können sich eine Zeichenfolge als Zeichen Array vorstellen `Char` . Sie können ein bestimmtes Zeichen abrufen, indem Sie über die-Eigenschaft auf den Index dieses Zeichens verweisen <xref:System.String.Chars%2A> .</span><span class="sxs-lookup"><span data-stu-id="60af4-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="60af4-107">Der `index` -Parameter der- <xref:System.String.Chars%2A> Eigenschaft ist NULL basiert.</span><span class="sxs-lookup"><span data-stu-id="60af4-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="60af4-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="60af4-108">Robust Programming</span></span>  

 <span data-ttu-id="60af4-109">Die- <xref:System.String.Chars%2A> Eigenschaft gibt das Zeichen an der angegebenen Position zurück.</span><span class="sxs-lookup"><span data-stu-id="60af4-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="60af4-110">Einige Unicode-Zeichen können jedoch durch mehr als ein Zeichen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="60af4-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="60af4-111">Weitere Informationen zum Arbeiten mit Unicode-Zeichen finden Sie unter Gewusst [wie: Konvertieren einer Zeichenfolge in ein Zeichen Array](how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="60af4-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="60af4-112">Die- <xref:System.String.Chars%2A> Eigenschaft löst eine <xref:System.IndexOutOfRangeException> Ausnahme aus, wenn der- `index` Parameter größer oder gleich der Länge der Zeichenfolge ist, oder wenn er kleiner als 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="60af4-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60af4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60af4-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="60af4-114">Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen</span><span class="sxs-lookup"><span data-stu-id="60af4-114">How to: Convert a String to an Array of Characters</span></span>](how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="60af4-115">Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60af4-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="60af4-116">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="60af4-116">Strings</span></span>](index.md)
