---
title: 'Vorgehensweise: Entfernen von ungültigen Zeichen aus einer Zeichenfolge'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- cleaning input
- user input, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
ms.openlocfilehash: cc90e6609f9335b7e2f08271e5540b182901e8c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127650"
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a><span data-ttu-id="b07d2-102">Vorgehensweise: Entfernen von ungültigen Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b07d2-102">How to: Strip Invalid Characters from a String</span></span>
<span data-ttu-id="b07d2-103">Im folgenden Beispiel wird die statische <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>-Methode verwendet, um ungültige Zeichen aus einer Zeichenfolge zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b07d2-103">The following example uses the static <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to strip invalid characters from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b07d2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b07d2-104">Example</span></span>  
 <span data-ttu-id="b07d2-105">Mit der in diesem Beispiel definierten `CleanInput`-Methode können Sie potenziell schädliche Zeichen entfernen, die in ein Textfeld eingegeben wurden, das Benutzereingaben akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b07d2-105">You can use the `CleanInput` method defined in this example to strip potentially harmful characters that have been entered into a text field that accepts user input.</span></span> <span data-ttu-id="b07d2-106">In diesem Fall entfernt `CleanInput` alle nicht alphanumerischen Zeichen außer Punkten (.), at-Symbolen (@) und Bindestrichen (-) und gibt die verbleibende Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="b07d2-106">In this case, `CleanInput` strips out all nonalphanumeric characters except periods (.), at symbols (@), and hyphens (-), and returns the remaining string.</span></span> <span data-ttu-id="b07d2-107">Allerdings können Sie Muster für reguläre Ausdrücke ändern, sodass alle Zeichen entfernt werden, die in einer Eingabezeichenfolge nicht enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="b07d2-107">However, you can modify the regular expression pattern so that it strips out any characters that should not be included in an input string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 <span data-ttu-id="b07d2-108">Das Muster für reguläre Ausdrücke `[^\w\.@-]` gleicht alle Zeichen ab, bei denen es sich nicht um Wortzeichen, Punkte, @-Zeichen oder Bindestriche handelt.</span><span class="sxs-lookup"><span data-stu-id="b07d2-108">The regular expression pattern `[^\w\.@-]` matches any character that is not a word character, a period, an @ symbol, or a hyphen.</span></span> <span data-ttu-id="b07d2-109">Wortzeichen sind alle Buchstaben, Dezimalziffern oder verbindende Satzzeichen wie Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="b07d2-109">A word character is any letter, decimal digit, or punctuation connector such as an underscore.</span></span> <span data-ttu-id="b07d2-110">Alle Zeichen, die diesem Muster entsprechen, werden durch <xref:System.String.Empty?displayProperty=nameWithType> ersetzt. Dies ist die durch das Ersatzmuster definierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b07d2-110">Any character that matches this pattern is replaced by <xref:System.String.Empty?displayProperty=nameWithType>, which is the string defined by the replacement pattern.</span></span> <span data-ttu-id="b07d2-111">Um zusätzliche Zeichen in der Benutzereingabe zu ermöglichen, fügen Sie diese Zeichen der Zeichenklasse im Muster für reguläre Ausdrücke hinzu.</span><span class="sxs-lookup"><span data-stu-id="b07d2-111">To allow additional characters in user input, add those characters to the character class in the regular expression pattern.</span></span> <span data-ttu-id="b07d2-112">Beispiel: Das Muster für reguläre Ausdrücke `[^\w\.@-\\%]` lässt auch ein Prozentsymbol und einen umgekehrten Schrägstrich in einer Eingabezeichenfolge zu.</span><span class="sxs-lookup"><span data-stu-id="b07d2-112">For example, the regular expression pattern `[^\w\.@-\\%]` also allows a percentage symbol and a backslash in an input string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b07d2-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b07d2-113">See also</span></span>

- [<span data-ttu-id="b07d2-114">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="b07d2-114">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
