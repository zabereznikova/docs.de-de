---
title: 'Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: acff804d87d67bf8758b97ad04805359bb3f2e32
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586069"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="008b1-102">Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="008b1-102">How to: Return Subsets of Element Properties in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="008b1-103">Verwenden Sie einen anonymen Typ in einem Abfrageausdruck, wenn die folgenden Bedingungen beide erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="008b1-103">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
- <span data-ttu-id="008b1-104">Sie möchte nur manche der Eigenschaften jedes Quellelements zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="008b1-104">You want to return only some of the properties of each source element.</span></span>  
  
- <span data-ttu-id="008b1-105">Sie müssen die Abfrageergebnisse nicht außerhalb des Geltungsbereichs der Methode speichern, in der die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="008b1-105">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="008b1-106">Wenn Sie nur eine Eigenschaft oder ein Feld jeder Quelldatei zurückgeben möchten, können Sie dazu den Punktoperator in der `select`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="008b1-106">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="008b1-107">Wenn Sie z.B. die `ID` jedes `student` zurückgeben möchten, schreiben Sie die `select`-Klausel wie folgt:</span><span class="sxs-lookup"><span data-stu-id="008b1-107">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="008b1-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="008b1-108">Example</span></span>  
 <span data-ttu-id="008b1-109">Im folgenden Beispiel erfahren Sie, wie Sie einen anonymen Typ verwenden können, um lediglich eine Teilmenge der Eigenschaften jedes Quellelements zurückzugeben, das die angegebenen Bedingungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="008b1-109">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 <span data-ttu-id="008b1-110">Beachten Sie, dass der anonyme Typ den Namen des Quellelements für dessen Eigenschaften verwendet, wenn keine Namen angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="008b1-110">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="008b1-111">Um die Eigenschaften im anonymen Typen zu benennen, schreiben Sie die `select`-Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="008b1-111">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="008b1-112">Wenn Sie dies mit vorherigem Beispiel durchführen möchten, müssen Sie die `Console.WriteLine`-Anweisung anpassen:</span><span class="sxs-lookup"><span data-stu-id="008b1-112">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="008b1-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="008b1-113">Compiling the Code</span></span>  
  
<span data-ttu-id="008b1-114">Zum Ausführen dieses Codes müssen Sie die Klasse kopieren und in eine C#-Konsolenanwendung mit einer `using`-Anweisung für „System.Linq“ einfügen.</span><span class="sxs-lookup"><span data-stu-id="008b1-114">To run this code, copy and paste the class into a C# console application  with a `using` directive for System.Linq.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="008b1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="008b1-115">See also</span></span>

- [<span data-ttu-id="008b1-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="008b1-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="008b1-117">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="008b1-117">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="008b1-118">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="008b1-118">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
