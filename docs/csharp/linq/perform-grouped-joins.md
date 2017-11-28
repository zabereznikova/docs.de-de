---
title: "Ausführen von Gruppenverknüpfungen"
description: "So führen Sie Gruppenverknüpfungen aus."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: 5e26473e19a5b6107d7aceea5e9829b48aa522b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="perform-grouped-joins"></a><span data-ttu-id="b34d5-104">Ausführen von Gruppenverknüpfungen</span><span class="sxs-lookup"><span data-stu-id="b34d5-104">Perform grouped joins</span></span>

<span data-ttu-id="b34d5-105">Die Gruppenverknüpfung ist nützlich für das Erstellen hierarchischer Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="b34d5-105">The group join is useful for producing hierarchical data structures.</span></span> <span data-ttu-id="b34d5-106">Sie verbindet jedes Element aus der ersten Auflistung mit einem Satz von entsprechenden Elementen aus der zweiten Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b34d5-106">It pairs each element from the first collection with a set of correlated elements from the second collection.</span></span>  
  
 <span data-ttu-id="b34d5-107">Eine Klasse oder relationale Datenbanktabelle namens `Student` kann z.B. zwei Felder enthalten: `Id` und `Name`.</span><span class="sxs-lookup"><span data-stu-id="b34d5-107">For example, a class or a relational database table named `Student` might contain two fields: `Id` and `Name`.</span></span> <span data-ttu-id="b34d5-108">Eine zweite Klasse oder relationale Datenbanktabelle namens `Course` kann zwei Felder enthalten: `StudentId` und `CourseTitle`.</span><span class="sxs-lookup"><span data-stu-id="b34d5-108">A second class or relational database table named `Course` might contain two fields: `StudentId` and `CourseTitle`.</span></span> <span data-ttu-id="b34d5-109">Eine Gruppenverknüpfung dieser beiden Datenquellen, die auf der übereinstimmenden `Student.Id` und `Course.StudentId` basiert, würde jeden `Student` mit einer Auflistung von `Course`-Objekten gruppieren (die vielleicht leer sind).</span><span class="sxs-lookup"><span data-stu-id="b34d5-109">A group join of these two data sources, based on matching `Student.Id` and `Course.StudentId`, would group each `Student` with a collection of `Course` objects (which might be empty).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b34d5-110">Jedes Element der ersten Auflistung erscheint im Ergebnissatz einer Gruppenverknüpfung, unabhängig davon, ob entsprechende Elemente in der zweiten Auflistung gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="b34d5-110">Each element of the first collection appears in the result set of a group join regardless of whether correlated elements are found in the second collection.</span></span> <span data-ttu-id="b34d5-111">Sollten keine entsprechenden Elemente gefunden werden, ist die Sequenz der entsprechenden Elemente für das Element leer.</span><span class="sxs-lookup"><span data-stu-id="b34d5-111">In the case where no correlated elements are found, the sequence of correlated elements for that element is empty.</span></span> <span data-ttu-id="b34d5-112">Die Ergebnisauswahl hat daher Zugriff auf jedes Element der ersten Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b34d5-112">The result selector therefore has access to every element of the first collection.</span></span> <span data-ttu-id="b34d5-113">Dies unterscheidet sich von der Ergebnisauswahl in einer Verknüpfung, bei der keine Gruppen verknüpft werden. Diese kann nicht auf Elemente aus der ersten Auflistung zugreifen, die keine Übereinstimmung in der zweiten Auflistung haben.</span><span class="sxs-lookup"><span data-stu-id="b34d5-113">This differs from the result selector in a non-group join, which cannot access elements from the first collection that have no match in the second collection.</span></span>  
  
 <span data-ttu-id="b34d5-114">Im ersten Beispiel in diesem Thema wird das Ausführen einer Gruppenverknüpfung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b34d5-114">The first example in this topic shows you how to perform a group join.</span></span> <span data-ttu-id="b34d5-115">Im zweiten Beispiel wird gezeigt, wie eine Gruppenverknüpfung zum Erstellen von XML-Elementen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b34d5-115">The second example shows you how to use a group join to create XML elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b34d5-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b34d5-116">Example</span></span>  
  
### <a name="group-join-example"></a><span data-ttu-id="b34d5-117">Beispiel für eine Gruppenverknüpfung</span><span class="sxs-lookup"><span data-stu-id="b34d5-117">Group join example</span></span>  
 <span data-ttu-id="b34d5-118">Das folgende Beispiel führt eine Gruppenverknüpfung von Objekten des Typs `Person` und `Pet` aus, die auf der `Person` basiert und mit der `Pet.Owner`-Eigenschaft übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b34d5-118">The following example performs a group join of objects of type `Person` and `Pet` based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="b34d5-119">Bei einer Verknüpfung, bei der keine Gruppen verknüpft werden, wird für jede Übereinstimmung ein Elementpaar erzeugt. Im Gegensatz dazu erzeugt eine Gruppenverknüpfung nur ein resultierendes Objekt für jedes Element der ersten Auflistung, was in diesem Beispiel ein `Person`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="b34d5-119">Unlike a non-group join, which would produce a pair of elements for each match, the group join produces only one resulting object for each element of the first collection, which in this example is a `Person` object.</span></span> <span data-ttu-id="b34d5-120">Die entsprechenden Elemente aus der zweiten Auflistung, die in diesem Beispiel `Pet`-Objekte sind, werden in einer Auflistung gruppiert.</span><span class="sxs-lookup"><span data-stu-id="b34d5-120">The corresponding elements from the second collection, which in this example are `Pet` objects, are grouped into a collection.</span></span> <span data-ttu-id="b34d5-121">Die Ergebnisauswahlfunktion erstellt schließlich einen anonymen Typ für jede Übereinstimmung, die aus `Person.FirstName` und einer Auflistung von `Pet`-Objekten besteht.</span><span class="sxs-lookup"><span data-stu-id="b34d5-121">Finally, the result selector function creates an anonymous type for each match that consists of `Person.FirstName` and a collection of `Pet` objects.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="b34d5-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b34d5-122">Example</span></span>  
  
### <a name="group-join-to-create-xml-example"></a><span data-ttu-id="b34d5-123">Gruppenverknüpfung zum Erstellen eines XML-Beispiels</span><span class="sxs-lookup"><span data-stu-id="b34d5-123">Group join to create XML example</span></span>  
 <span data-ttu-id="b34d5-124">Gruppenverknüpfungen lassen sich ideal für das Erstellen von XML mithilfe von LINQ to XML nutzen.</span><span class="sxs-lookup"><span data-stu-id="b34d5-124">Group joins are ideal for creating XML by using LINQ to XML.</span></span> <span data-ttu-id="b34d5-125">Das folgende Beispiel ähnelt dem vorherigen, nur dass die Ergebnisauswahlfunktion anstatt eines anonymen Typs XML-Elemente erstellt, die die verknüpften Objekte darstellen.</span><span class="sxs-lookup"><span data-stu-id="b34d5-125">The following example is similar to the previous example except that instead of creating anonymous types, the result selector function creates XML elements that represent the joined objects.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="b34d5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b34d5-126">See also</span></span>  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [<span data-ttu-id="b34d5-127">Ausführen innerer Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="b34d5-127">Perform inner joins</span></span>](perform-inner-joins.md)  
 [<span data-ttu-id="b34d5-128">Ausführen linker äußerer Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="b34d5-128">Perform left outer joins</span></span>](perform-left-outer-joins.md)  
 [<span data-ttu-id="b34d5-129">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="b34d5-129">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 
