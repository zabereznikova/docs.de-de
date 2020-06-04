---
title: 'Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: eca8cd7be8da1f6149dadf1e9edeab5e5225ab9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360669"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="65b63-102">Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65b63-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="65b63-103">Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der Zeichen in der Zeichenfolge zu erhalten, z. b. Wenn Sie eine Zeichenfolge in eine Zeichenfolge schreiben.</span><span class="sxs-lookup"><span data-stu-id="65b63-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="65b63-104">Dieses Beispiel zeigt, wie Sie ein Array von Zeichen in einer Zeichenfolge abrufen können, indem Sie die-Methode der Zeichenfolge aufrufen <xref:System.String.ToCharArray%2A> .</span><span class="sxs-lookup"><span data-stu-id="65b63-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65b63-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65b63-105">Example</span></span>  
 <span data-ttu-id="65b63-106">Dieses Beispiel zeigt, wie Sie eine Zeichenfolge in ein `Char` -Array aufteilen und eine Zeichenfolge in ein `String` Array von Unicode-Textzeichen aufteilen können.</span><span class="sxs-lookup"><span data-stu-id="65b63-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="65b63-107">Der Grund für diesen Unterschied besteht darin, dass Unicode-Textzeichen aus mindestens zwei `Char` Zeichen bestehen können (z. b. ein Ersatz Zeichenpaar oder eine kombinierte Zeichen Sequenz).</span><span class="sxs-lookup"><span data-stu-id="65b63-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="65b63-108">Weitere Informationen finden Sie unter <xref:System.Globalization.TextElementEnumerator> und [im Unicode-Standard](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="65b63-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="65b63-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65b63-109">Example</span></span>  
 <span data-ttu-id="65b63-110">Es ist schwieriger, eine Zeichenfolge in die Unicode-Textzeichen aufzuteilen, aber dies ist erforderlich, wenn Sie Informationen zur visuellen Darstellung einer Zeichenfolge benötigen.</span><span class="sxs-lookup"><span data-stu-id="65b63-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="65b63-111">In diesem Beispiel wird die- <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> Methode verwendet, um Informationen über die Unicode-Textzeichen, die eine Zeichenfolge bilden, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="65b63-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="65b63-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65b63-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="65b63-113">Vorgehensweise: Zugreifen auf Zeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="65b63-113">How to: Access Characters in Strings</span></span>](how-to-access-characters-in-strings.md)
- [<span data-ttu-id="65b63-114">Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65b63-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="65b63-115">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="65b63-115">Strings</span></span>](index.md)
