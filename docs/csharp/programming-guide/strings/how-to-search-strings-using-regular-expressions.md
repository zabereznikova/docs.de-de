---
title: "Gewusst wie: Suchen von Zeichenfolgen mithilfe von regulären Ausdrücken (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c851c57b44f1343816b905db002e530121fb6c0a
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a><span data-ttu-id="8ee0c-102">Gewusst wie: Suchen von Zeichenfolgen mithilfe von regulären Ausdrücken (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8ee0c-102">How to: Search Strings Using Regular Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="8ee0c-103">Die <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>-Klasse kann zum durchsuchen von Zeichenfolgen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-103">The <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class can be used to search strings.</span></span> <span data-ttu-id="8ee0c-104">Diese Suchvorgänge können sehr simpel sein oder voll von regulären Ausdrücken profitieren.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-104">These searches can range in complexity from very simple to making full use of regular expressions.</span></span> <span data-ttu-id="8ee0c-105">Im Folgenden finden Sie zwei Beispiele für das Durchsuchen von Zeichenfolgen mit der <xref:System.Text.RegularExpressions.Regex>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-105">The following are two examples of string searching by using the <xref:System.Text.RegularExpressions.Regex> class.</span></span> <span data-ttu-id="8ee0c-106">Weitere Informationen hierzu finden Sie unter [Reguläre Ausdrücke von .NET Framework](https://msdn.microsoft.com/library/hs600312).</span><span class="sxs-lookup"><span data-stu-id="8ee0c-106">For more information, see [.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ee0c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ee0c-107">Example</span></span>  
 <span data-ttu-id="8ee0c-108">Der folgende Code ist eine Konsolenanwendung, die eine einfache Suche von Zeichenfolgen in einem Array durchführt, die nicht auf die Groß- und Kleinschreibung achtet.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-108">The following code is a console application that performs a simple case-insensitive search of the strings in an array.</span></span> <span data-ttu-id="8ee0c-109">Die statische Methode <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> führt die Suche mit der zu durchsuchenden Zeichenfolge und einer Zeichenfolge, die das Suchmuster enthält, durch.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-109">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> performs the search given the string to search and a string that contains the search pattern.</span></span> <span data-ttu-id="8ee0c-110">In diesem Fall wird ein drittes Argument verwendet, um anzugeben, dass die Groß- und Kleinschreibung nicht beachtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-110">In this case, a third argument is used to indicate that case should be ignored.</span></span> <span data-ttu-id="8ee0c-111">Weitere Informationen finden Sie unter <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-111">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="8ee0c-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ee0c-112">Example</span></span>  
 <span data-ttu-id="8ee0c-113">Der folgende Code ist eine Konsolenanwendung, die reguläre Ausdrücke verwendet, um das Format jeder Zeichenfolge in einem Array zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-113">The following code is a console application that uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="8ee0c-114">Für die Überprüfung ist erforderlich, dass jede Zeichenfolge die Form einer Telefonnummer hat, in der drei Gruppen von Zahlen durch Gedankenstriche getrennt sind, wobei die erste Gruppe drei Zeichen enthält und die dritte vier.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-114">The validation requires that each string take the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="8ee0c-115">Dies erreichen Sie mit dem regulären Ausdruck `^\\d{3}-\\d{3}-\\d{4}$`.</span><span class="sxs-lookup"><span data-stu-id="8ee0c-115">This is done by using the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="8ee0c-116">Weitere Informationen finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span><span class="sxs-lookup"><span data-stu-id="8ee0c-116">For more information, see [Regular Expression Language - Quick Reference](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span></span>  
  
 [!code-csharp[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8ee0c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ee0c-117">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [<span data-ttu-id="8ee0c-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8ee0c-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8ee0c-119">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="8ee0c-119">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="8ee0c-120">Reguläre Ausdrücke von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8ee0c-120">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)  
 [<span data-ttu-id="8ee0c-121">Sprachelemente für reguläre Ausdrücke – Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="8ee0c-121">Regular Expression Language - Quick Reference</span></span>](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)
