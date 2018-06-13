---
title: 'Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: c109143601e304b1ec15a60c71d65fe6bd15aae8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648618"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="3f246-102">Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f246-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="3f246-103">Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der diese Zeichen innerhalb der Zeichenfolge, z. B. beim Analysieren einer Zeichenfolge zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f246-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="3f246-104">In diesem Beispiel wird gezeigt, wie Sie ein Array von Zeichen in einer Zeichenfolge abrufen können, durch Aufrufen der Zeichenfolge <xref:System.String.ToCharArray%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="3f246-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f246-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f246-105">Example</span></span>  
 <span data-ttu-id="3f246-106">In diesem Beispiel wird veranschaulicht, wie zum Aufteilen einer Zeichenfolge in eine `Char` Array sowie zum Aufteilen einer Zeichenfolge in eine `String` Array von Unicode-Textzeichen.</span><span class="sxs-lookup"><span data-stu-id="3f246-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="3f246-107">Der Grund für diese Unterscheidung ist, dass von zwei oder mehr Unicode-Textzeichen zusammengesetzt werden können `Char` Zeichen (z. B. ein Ersatzzeichenpaar oder eine Kombination von Zeichen der Sequenz).</span><span class="sxs-lookup"><span data-stu-id="3f246-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="3f246-108">Weitere Informationen finden Sie unter <xref:System.Globalization.TextElementEnumerator> und "Im Unicode-Standard" auf http://www.unicode.org.</span><span class="sxs-lookup"><span data-stu-id="3f246-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and "The Unicode Standard" at http://www.unicode.org.</span></span>  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3f246-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f246-109">Example</span></span>  
 <span data-ttu-id="3f246-110">Es ist schwieriger, eine Zeichenfolge in Unicode-Textzeichen aufgeteilt, aber dies ist erforderlich, wenn Sie Informationen über die visuelle Darstellung einer Zeichenfolge benötigen.</span><span class="sxs-lookup"><span data-stu-id="3f246-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="3f246-111">Dieses Beispiel verwendet die <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> Methode zum Abrufen von Informationen über die Unicode-Zeichen, die eine Zeichenfolge zu bilden.</span><span class="sxs-lookup"><span data-stu-id="3f246-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3f246-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f246-112">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [<span data-ttu-id="3f246-113">Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="3f246-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [<span data-ttu-id="3f246-114">Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f246-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="3f246-115">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="3f246-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
