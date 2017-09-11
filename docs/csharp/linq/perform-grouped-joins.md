---
title: "Ausführen von Gruppenverknüpfungen"
description: "So führen Sie Gruppenverknüpfungen aus."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0410c5f673e61f91c00a69cb1659e0d72852f128
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="perform-grouped-joins"></a><span data-ttu-id="dac13-104">Ausführen von Gruppenverknüpfungen</span><span class="sxs-lookup"><span data-stu-id="dac13-104">Perform grouped joins</span></span>

<span data-ttu-id="dac13-105">Die Gruppenverknüpfung ist nützlich für das Erstellen hierarchischer Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="dac13-105">The group join is useful for producing hierarchical data structures.</span></span> <span data-ttu-id="dac13-106">Sie verbindet jedes Element aus der ersten Auflistung mit einem Satz von entsprechenden Elementen aus der zweiten Auflistung.</span><span class="sxs-lookup"><span data-stu-id="dac13-106">It pairs each element from the first collection with a set of correlated elements from the second collection.</span></span>  
  
 <span data-ttu-id="dac13-107">Eine Klasse oder relationale Datenbanktabelle namens `Student` kann z.B. zwei Felder enthalten: `Id` und `Name`.</span><span class="sxs-lookup"><span data-stu-id="dac13-107">For example, a class or a relational database table named `Student` might contain two fields: `Id` and `Name`.</span></span> <span data-ttu-id="dac13-108">Eine zweite Klasse oder relationale Datenbanktabelle namens `Course` kann zwei Felder enthalten: `StudentId` und `CourseTitle`.</span><span class="sxs-lookup"><span data-stu-id="dac13-108">A second class or relational database table named `Course` might contain two fields: `StudentId` and `CourseTitle`.</span></span> <span data-ttu-id="dac13-109">Eine Gruppenverknüpfung dieser beiden Datenquellen, die auf der übereinstimmenden `Student.Id` und `Course.StudentId` basiert, würde jeden `Student` mit einer Auflistung von `Course`-Objekten gruppieren (die vielleicht leer sind).</span><span class="sxs-lookup"><span data-stu-id="dac13-109">A group join of these two data sources, based on matching `Student.Id` and `Course.StudentId`, would group each `Student` with a collection of `Course` objects (which might be empty).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dac13-110">Jedes Element der ersten Auflistung erscheint im Ergebnissatz einer Gruppenverknüpfung, unabhängig davon, ob entsprechende Elemente in der zweiten Auflistung gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="dac13-110">Each element of the first collection appears in the result set of a group join regardless of whether correlated elements are found in the second collection.</span></span> <span data-ttu-id="dac13-111">Sollten keine entsprechenden Elemente gefunden werden, ist die Sequenz der entsprechenden Elemente für das Element leer.</span><span class="sxs-lookup"><span data-stu-id="dac13-111">In the case where no correlated elements are found, the sequence of correlated elements for that element is empty.</span></span> <span data-ttu-id="dac13-112">Die Ergebnisauswahl hat daher Zugriff auf jedes Element der ersten Auflistung.</span><span class="sxs-lookup"><span data-stu-id="dac13-112">The result selector therefore has access to every element of the first collection.</span></span> <span data-ttu-id="dac13-113">Dies unterscheidet sich von der Ergebnisauswahl in einer Verknüpfung, bei der keine Gruppen verknüpft werden. Diese kann nicht auf Elemente aus der ersten Auflistung zugreifen, die keine Übereinstimmung in der zweiten Auflistung haben.</span><span class="sxs-lookup"><span data-stu-id="dac13-113">This differs from the result selector in a non-group join, which cannot access elements from the first collection that have no match in the second collection.</span></span>  
  
 <span data-ttu-id="dac13-114">Im ersten Beispiel in diesem Thema wird das Ausführen einer Gruppenverknüpfung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dac13-114">The first example in this topic shows you how to perform a group join.</span></span> <span data-ttu-id="dac13-115">Im zweiten Beispiel wird gezeigt, wie eine Gruppenverknüpfung zum Erstellen von XML-Elementen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dac13-115">The second example shows you how to use a group join to create XML elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dac13-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dac13-116">Example</span></span>  
  
### <a name="group-join-example"></a><span data-ttu-id="dac13-117">Beispiel für eine Gruppenverknüpfung</span><span class="sxs-lookup"><span data-stu-id="dac13-117">Group join example</span></span>  
 <span data-ttu-id="dac13-118">Das folgende Beispiel führt eine Gruppenverknüpfung von Objekten des Typs `Person` und `Pet` aus, die auf der `Person` basiert und mit der `Pet.Owner`-Eigenschaft übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="dac13-118">The following example performs a group join of objects of type `Person` and `Pet` based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="dac13-119">Bei einer Verknüpfung, bei der keine Gruppen verknüpft werden, wird für jede Übereinstimmung ein Elementpaar erzeugt. Im Gegensatz dazu erzeugt eine Gruppenverknüpfung nur ein resultierendes Objekt für jedes Element der ersten Auflistung, was in diesem Beispiel ein `Person`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="dac13-119">Unlike a non-group join, which would produce a pair of elements for each match, the group join produces only one resulting object for each element of the first collection, which in this example is a `Person` object.</span></span> <span data-ttu-id="dac13-120">Die entsprechenden Elemente aus der zweiten Auflistung, die in diesem Beispiel `Pet`-Objekte sind, werden in einer Auflistung gruppiert.</span><span class="sxs-lookup"><span data-stu-id="dac13-120">The corresponding elements from the second collection, which in this example are `Pet` objects, are grouped into a collection.</span></span> <span data-ttu-id="dac13-121">Die Ergebnisauswahlfunktion erstellt schließlich einen anonymen Typ für jede Übereinstimmung, die aus `Person.FirstName` und einer Auflistung von `Pet`-Objekten besteht.</span><span class="sxs-lookup"><span data-stu-id="dac13-121">Finally, the result selector function creates an anonymous type for each match that consists of `Person.FirstName` and a collection of `Pet` objects.</span></span>  
  
 <span data-ttu-id="dac13-122">[!code-cs[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dac13-122">[!code-cs[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="dac13-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dac13-123">Example</span></span>  
  
### <a name="group-join-to-create-xml-example"></a><span data-ttu-id="dac13-124">Gruppenverknüpfung zum Erstellen eines XML-Beispiels</span><span class="sxs-lookup"><span data-stu-id="dac13-124">Group join to create XML example</span></span>  
 <span data-ttu-id="dac13-125">Gruppenverknüpfungen lassen sich ideal für das Erstellen von XML mithilfe von LINQ to XML nutzen.</span><span class="sxs-lookup"><span data-stu-id="dac13-125">Group joins are ideal for creating XML by using LINQ to XML.</span></span> <span data-ttu-id="dac13-126">Das folgende Beispiel ähnelt dem vorherigen, nur dass die Ergebnisauswahlfunktion anstatt eines anonymen Typs XML-Elemente erstellt, die die verknüpften Objekte darstellen.</span><span class="sxs-lookup"><span data-stu-id="dac13-126">The following example is similar to the previous example except that instead of creating anonymous types, the result selector function creates XML elements that represent the joined objects.</span></span>  
  
 <span data-ttu-id="dac13-127">[!code-cs[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="dac13-127">[!code-cs[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="dac13-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dac13-128">See also</span></span>  
 <span data-ttu-id="dac13-129"><xref:System.Linq.Enumerable.Join%2A></span><span class="sxs-lookup"><span data-stu-id="dac13-129"><xref:System.Linq.Enumerable.Join%2A></span></span>   
 <span data-ttu-id="dac13-130"><xref:System.Linq.Enumerable.GroupJoin%2A></span><span class="sxs-lookup"><span data-stu-id="dac13-130"><xref:System.Linq.Enumerable.GroupJoin%2A></span></span>   
 <span data-ttu-id="dac13-131">[Ausführen innerer Verknüpfungen](perform-inner-joins.md) </span><span class="sxs-lookup"><span data-stu-id="dac13-131">[Perform inner joins](perform-inner-joins.md) </span></span>  
 <span data-ttu-id="dac13-132">[Perform left outer joins (Ausführen von Left Outer Joins)](perform-left-outer-joins.md) </span><span class="sxs-lookup"><span data-stu-id="dac13-132">[Perform left outer joins](perform-left-outer-joins.md) </span></span>  
 [<span data-ttu-id="dac13-133">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="dac13-133">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)   
 

