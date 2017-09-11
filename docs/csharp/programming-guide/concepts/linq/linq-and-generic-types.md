---
title: LINQ und generische Typen (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 177db64491d58b31ca50cef0bb2eda8c2cb65078
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="linq-and-generic-types-c"></a><span data-ttu-id="f2cf4-102">LINQ und generische Typen (C#)</span><span class="sxs-lookup"><span data-stu-id="f2cf4-102">LINQ and Generic Types (C#)</span></span>
[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]<span data-ttu-id="f2cf4-103">-Abfragen basieren auf generischen Typen, die mit Version 2.0 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-103"> queries are based on generic types, which were introduced in version 2.0 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="f2cf4-104">Sie benötigen kein ausführliches Wissen über Generika, um Abfragen schreiben zu können.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-104">You do not need an in-depth knowledge of generics before you can start writing queries.</span></span> <span data-ttu-id="f2cf4-105">Dennoch sollten Sie zwei grundlegende Konzepte verstehen:</span><span class="sxs-lookup"><span data-stu-id="f2cf4-105">However, you may want to understand two basic concepts:</span></span>  
  
1.  <span data-ttu-id="f2cf4-106">Wenn Sie eine Instanz einer generischen Auflistungsklasse wie etwa <xref:System.Collections.Generic.List%601> erstellen, ersetzen Sie das „T“ durch den Objekttyp, den die Liste enthalten wird.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-106">When you create an instance of a generic collection class such as <xref:System.Collections.Generic.List%601>, you replace the "T" with the type of objects that the list will hold.</span></span> <span data-ttu-id="f2cf4-107">Eine Liste von Zeichenfolgen wird z.B. als `List<string>` und eine Liste von `Customer`-Objekten als `List<Customer>` ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-107">For example, a list of strings is expressed as `List<string>`, and a list of `Customer` objects is expressed as `List<Customer>`.</span></span> <span data-ttu-id="f2cf4-108">Eine generische Liste ist stark typisiert und hat gegenüber Auflistungen, die ihre Elemente als <xref:System.Object> speichern, viele Vorzüge.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-108">A generic list is strongly typed and provides many benefits over collections that store their elements as <xref:System.Object>.</span></span> <span data-ttu-id="f2cf4-109">Wenn Sie versuchen einen `Customer` in eine `List<string>` einzufügen, erhalten Sie zur Laufzeit eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-109">If you try to add a `Customer` to a `List<string>`, you will get an error at compile time.</span></span> <span data-ttu-id="f2cf4-110">Es ist sehr leicht, generische Auflistungen zu verwenden, da Sie keine Laufzeitumwandlung von Typen durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-110">It is easy to use generic collections because you do not have to perform run-time type-casting.</span></span>  
  
2.  <span data-ttu-id="f2cf4-111"><xref:System.Collections.Generic.IEnumerable%601> ist die Schnittstelle, die es ermöglicht, dass generische Auflistungsklassen mithilfe der Anweisung `foreach` aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-111"><xref:System.Collections.Generic.IEnumerable%601> is the interface that enables generic collection classes to be enumerated by using the `foreach` statement.</span></span> <span data-ttu-id="f2cf4-112">Generische Auflistungsklassen unterstützen <xref:System.Collections.Generic.IEnumerable%601>, während nicht generische Auflistungsklassen, wie etwa <xref:System.Collections.ArrayList>, <xref:System.Collections.IEnumerable> unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-112">Generic collection classes support <xref:System.Collections.Generic.IEnumerable%601> just as non-generic collection classes such as <xref:System.Collections.ArrayList> support <xref:System.Collections.IEnumerable>.</span></span>  
  
 <span data-ttu-id="f2cf4-113">Weitere Informationen zu Generika finden Sie unter [Generika](../../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="f2cf4-113">For more information about generics, see [Generics](../../../../csharp/programming-guide/generics/index.md).</span></span>  
  
## <a name="ienumerablet-variables-in-linq-queries"></a><span data-ttu-id="f2cf4-114">IEnumerable<T\>-Variablen in LINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="f2cf4-114">IEnumerable<T\> variables in LINQ Queries</span></span>  
 <span data-ttu-id="f2cf4-115">Die Abfragevariablen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] werden als <xref:System.Collections.Generic.IEnumerable%601> typisiert oder als ein abgeleiteter Typ, wie z.B. <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-115">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query variables are typed as <xref:System.Collections.Generic.IEnumerable%601> or a derived type such as <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="f2cf4-116">Wenn Sie eine Abfragevariable des Typs `IEnumerable<Customer>` sehen, bedeutet dies nur, dass die Abfrage bei der Ausführung eine Folge von null oder mehr `Customer`-Objekten produziert.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-116">When you see a query variable that is typed as `IEnumerable<Customer>`, it just means that the query, when it is executed, will produce a sequence of zero or more `Customer` objects.</span></span>  
  
 <span data-ttu-id="f2cf4-117">[!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2cf4-117">[!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]</span></span>  
  
 <span data-ttu-id="f2cf4-118">Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="f2cf4-118">For more information, see [Type Relationships in LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a><span data-ttu-id="f2cf4-119">Verarbeiten von generischen Typdeklaration durch den Compiler</span><span class="sxs-lookup"><span data-stu-id="f2cf4-119">Letting the Compiler Handle Generic Type Declarations</span></span>  
 <span data-ttu-id="f2cf4-120">Falls Sie dies möchten, können Sie generische Syntax umgehen, indem Sie das Schlüsselwort [var](../../../../csharp/language-reference/keywords/var.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-120">If you prefer, you can avoid generic syntax by using the [var](../../../../csharp/language-reference/keywords/var.md) keyword.</span></span> <span data-ttu-id="f2cf4-121">Das Schlüsselwort `var` weist den Compiler an, den Typ der Abfragevariablen abzuleiten, indem er sich an der in der `from`-Klausel angegebenen Datenquelle orientiert.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-121">The `var` keyword instructs the compiler to infer the type of a query variable by looking at the data source specified in the `from` clause.</span></span> <span data-ttu-id="f2cf4-122">Das folgende Beispiel erstellt den gleichen kompilierten Code wie das vorherige Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f2cf4-122">The following example produces the same compiled code as the previous example:</span></span>  
  
 <span data-ttu-id="f2cf4-123">[!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2cf4-123">[!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]</span></span>  
  
 <span data-ttu-id="f2cf4-124">Das Schlüsselwort `var` ist nützlich, wenn der Typ der Variablen offensichtlich ist, oder wenn es nicht so wichtig ist, die geschachtelten generischen Typen explizit festzulegen, wie z.B. diejenigen, die in Gruppenabfragen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-124">The `var` keyword is useful when the type of the variable is obvious or when it is not that important to explicitly specify nested generic types such as those that are produced by group queries.</span></span> <span data-ttu-id="f2cf4-125">Allgemein wird darauf hingewiesen, dass das Verwenden von `var` das Lesen Ihres Codes durch andere erschwert.</span><span class="sxs-lookup"><span data-stu-id="f2cf4-125">In general, we recommend that if you use `var`, realize that it can make your code more difficult for others to read.</span></span> <span data-ttu-id="f2cf4-126">Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f2cf4-126">For more information, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cf4-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2cf4-127">See Also</span></span>  
 <span data-ttu-id="f2cf4-128">[Erste Schritte mit LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f2cf4-128">[Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
 [<span data-ttu-id="f2cf4-129">Generika</span><span class="sxs-lookup"><span data-stu-id="f2cf4-129">Generics</span></span>](../../../../csharp/programming-guide/generics/index.md)

