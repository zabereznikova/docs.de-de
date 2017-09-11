---
title: into (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- into_CSharpKeyword
- into
dev_langs:
- CSharp
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ef85caf02387432761e5ccbb7e0478b46d32f795
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="into-c-reference"></a><span data-ttu-id="1a501-102">into (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1a501-102">into (C# Reference)</span></span>
<span data-ttu-id="1a501-103">Das Kontextschlüsselwort `into` kann zum Erstellen eines temporären Bezeichners verwendet werden, der die Ergebnisse einer [group](../../../csharp/language-reference/keywords/group-clause.md)-, [join](../../../csharp/language-reference/keywords/join-clause.md)- oder [select](../../../csharp/language-reference/keywords/select-clause.md)-Klausel in einem neuen Bezeichner speichert.</span><span class="sxs-lookup"><span data-stu-id="1a501-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) or [select](../../../csharp/language-reference/keywords/select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="1a501-104">Dieser Bezeichner kann wiederum ein Generator für zusätzliche Abfragebefehle sein.</span><span class="sxs-lookup"><span data-stu-id="1a501-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="1a501-105">In einer `group`- oder `select`-Klausel wird die Verwendung des neuen Bezeichners auch als *Fortsetzung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1a501-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a501-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a501-106">Example</span></span>  
 <span data-ttu-id="1a501-107">Das folgende Beispiel zeigt die Verwendung des Schlüsselworts `into` zur Aktivierung eines temporären Bezeichners `fruitGroup`, der über einen abgeleiteten Typ `IGrouping` verfügt.</span><span class="sxs-lookup"><span data-stu-id="1a501-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="1a501-108">Mit diesem Bezeichner können Sie die <xref:System.Linq.Enumerable.Count%2A>-Methode für jede Gruppe aufrufen und nur die Gruppen auswählen, die mindestens zwei Wörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a501-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>  
  
 <span data-ttu-id="1a501-109">[!code-cs[cscsrefAbfrageSchlüsselwörter#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a501-109">[!code-cs[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]</span></span>  
  
 <span data-ttu-id="1a501-110">Die Verwendung von `into` in einer `group`-Klausel ist nur erforderlich, wenn Sie zusätzliche Abfragevorgänge für jede Gruppe ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1a501-110">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="1a501-111">Weitere Informationen finden Sie unter [group-Klausel](../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="1a501-111">For more information, see [group clause](../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="1a501-112">Ein Beispiel für die Verwendung von `into` in einer `join`-Klausel finden Sie unter [join-Klausel](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="1a501-112">For an example of the use of `into` in a `join` clause, see [join clause](../../../csharp/language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a501-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a501-113">See Also</span></span>  
 <span data-ttu-id="1a501-114">[Abfrageschlüsselwörter (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="1a501-114">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="1a501-115">[LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a501-115">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="1a501-116">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="1a501-116">group clause</span></span>](../../../csharp/language-reference/keywords/group-clause.md)

