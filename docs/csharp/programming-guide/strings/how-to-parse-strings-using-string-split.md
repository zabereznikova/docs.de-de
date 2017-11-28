---
title: 'Gewusst wie: Analysieren von Zeichenfolgen mithilfe von String.Split (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7b97d1d89a4c74a4c759d1ed41a0bc2476b3b07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a><span data-ttu-id="2f8d3-102">Gewusst wie: Analysieren von Zeichenfolgen mithilfe von String.Split (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2f8d3-102">How to: Parse Strings Using String.Split (C# Programming Guide)</span></span>
<span data-ttu-id="2f8d3-103">Im folgenden Codebeispiel wird veranschaulicht, wie eine Zeichenfolge mithilfe der <xref:System.String.Split%2A?displayProperty=nameWithType> -Methode analysiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f8d3-103">The following code example demonstrates how a string can be parsed using the <xref:System.String.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2f8d3-104">Als Eingabe akzeptiert <xref:System.String.Split%2A> ein Array von Zeichen, die angeben, durch welche Zeichen relevante Unterzeichenfolgen der Zielzeichenfolge getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="2f8d3-104">As input, <xref:System.String.Split%2A> takes an array of characters that indicate which characters separate interesting sub strings of the target string.</span></span>  <span data-ttu-id="2f8d3-105">Die Funktion gibt ein Array von Unterzeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="2f8d3-105">The function returns an array of the sub strings.</span></span>  
  
 <span data-ttu-id="2f8d3-106">In diesem Beispiel werden Leerzeichen, Kommas, Punkte, Doppelpunkte und Tabstopps verwendet, die alle in einem Array, das diese Trennzeichen enthält, an <xref:System.String.Split%2A>übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="2f8d3-106">This example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters to <xref:System.String.Split%2A>.</span></span>  <span data-ttu-id="2f8d3-107">Jedes Wort im Satz der Zielzeichenfolge wird getrennt vom resultierenden Zeichenfolgenarray angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f8d3-107">Each word in the target string's sentence displays separately from the resulting array of strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f8d3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f8d3-108">Example</span></span>  
 [!code-csharp[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="2f8d3-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f8d3-109">Example</span></span>  
 <span data-ttu-id="2f8d3-110">Standardmäßig gibt String.Split leere Zeichenfolgen zurück, wenn zwei Trennzeichen in der Zielzeichenfolge nacheinander angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2f8d3-110">By default, String.Split returns empty strings when two separating characters appear contiguously in the target string.</span></span>  <span data-ttu-id="2f8d3-111">Sie können einen optionalen StringSplitOptions.RemoveEmptyEntries-Parameter übergeben, um alle leeren Zeichenfolgen in der Ausgabe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="2f8d3-111">You can pass an optional StringSplitOptions.RemoveEmptyEntries parameter to exclude any empty strings in the output.</span></span>  
  
 <span data-ttu-id="2f8d3-112">String.Split kann ein Array von Zeichenfolgen aufnehmen (Zeichenfolgen, die als Trennzeichen für die Analyse der Zielzeichenfolge fungieren, statt einzelne Zeichen).</span><span class="sxs-lookup"><span data-stu-id="2f8d3-112">String.Split can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        string[] separatingChars = { "<<", "..." };  
  
        string text = "one<<two......three<four";  
        System.Console.WriteLine("Original text: '{0}'", text);  
  
        string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries );  
        System.Console.WriteLine("{0} substrings in text:", words.Length);  
  
        foreach (string s in words)  
        {  
            System.Console.WriteLine(s);  
        }  
  
        // Keep the console window open in debug mode.  
        System.Console.WriteLine("Press any key to exit.");  
        System.Console.ReadKey();  
    }  
}  
/* Output:  
    Original text: 'one<<two......three<four'  
    3 words in text:  
    one  
    two  
    three<four  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f8d3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f8d3-113">See Also</span></span>  
 [<span data-ttu-id="2f8d3-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2f8d3-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2f8d3-115">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="2f8d3-115">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="2f8d3-116">Reguläre Ausdrücke von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2f8d3-116">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)
