---
title: 'Gewusst wie: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie einen anonymen Typ in einem Abfrageausdruck in C# verwenden, um einige der Eigenschaften eines Quellelements zurückzugeben.
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 5784d6a288af374d357346e32535ebe9c1877bcc
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512794"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="6bf45-103">Gewusst wie: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6bf45-103">How to return subsets of element properties in a query (C# Programming Guide)</span></span>

<span data-ttu-id="6bf45-104">Verwenden Sie einen anonymen Typ in einem Abfrageausdruck, wenn die folgenden Bedingungen beide erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="6bf45-104">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
- <span data-ttu-id="6bf45-105">Sie möchte nur manche der Eigenschaften jedes Quellelements zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6bf45-105">You want to return only some of the properties of each source element.</span></span>  
  
- <span data-ttu-id="6bf45-106">Sie müssen die Abfrageergebnisse nicht außerhalb des Geltungsbereichs der Methode speichern, in der die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6bf45-106">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="6bf45-107">Wenn Sie nur eine Eigenschaft oder ein Feld jeder Quelldatei zurückgeben möchten, können Sie dazu den Punktoperator in der `select`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="6bf45-107">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="6bf45-108">Wenn Sie z.B. die `ID` jedes `student` zurückgeben möchten, schreiben Sie die `select`-Klausel wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6bf45-108">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="6bf45-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6bf45-109">Example</span></span>  

 <span data-ttu-id="6bf45-110">Im folgenden Beispiel erfahren Sie, wie Sie einen anonymen Typ verwenden können, um lediglich eine Teilmenge der Eigenschaften jedes Quellelements zurückzugeben, das die angegebenen Bedingungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="6bf45-110">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 <span data-ttu-id="6bf45-111">Beachten Sie, dass der anonyme Typ den Namen des Quellelements für dessen Eigenschaften verwendet, wenn keine Namen angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="6bf45-111">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="6bf45-112">Um die Eigenschaften im anonymen Typen zu benennen, schreiben Sie die `select`-Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6bf45-112">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="6bf45-113">Wenn Sie dies mit vorherigem Beispiel durchführen möchten, müssen Sie die `Console.WriteLine`-Anweisung anpassen:</span><span class="sxs-lookup"><span data-stu-id="6bf45-113">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6bf45-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6bf45-114">Compiling the Code</span></span>  
  
<span data-ttu-id="6bf45-115">Zum Ausführen dieses Codes müssen Sie die Klasse kopieren und in eine C#-Konsolenanwendung mit einer `using`-Anweisung für „System.Linq“ einfügen.</span><span class="sxs-lookup"><span data-stu-id="6bf45-115">To run this code, copy and paste the class into a C# console application  with a `using` directive for System.Linq.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6bf45-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bf45-116">See also</span></span>

- [<span data-ttu-id="6bf45-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6bf45-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6bf45-118">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="6bf45-118">Anonymous Types</span></span>](./anonymous-types.md)
- [<span data-ttu-id="6bf45-119">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="6bf45-119">LINQ in C#</span></span>](../../linq/index.md)
