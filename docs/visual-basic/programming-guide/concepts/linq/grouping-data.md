---
title: Gruppieren von Daten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ce4e8f924f91eed451d3b1a02cd0bcff75589537
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="b657f-102">Gruppieren von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b657f-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="b657f-103">Gruppierung bezieht sich auf den Betrieb von Daten in Gruppen angeordnet werden, so dass die Elemente in jeder Gruppe ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="b657f-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="b657f-104">Die folgende Abbildung zeigt die Ergebnisse eine Folge von Zeichen zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="b657f-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="b657f-105">Der Schlüssel für jede Gruppe ist das Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b657f-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="b657f-106">![LINQ-Gruppierungsvorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="b657f-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="b657f-107">Die Standardabfrageoperator-Methoden, die Datenelemente gruppieren, werden im folgenden Abschnitt aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b657f-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b657f-108">Methoden</span><span class="sxs-lookup"><span data-stu-id="b657f-108">Methods</span></span>  
  
|<span data-ttu-id="b657f-109">Methodenname</span><span class="sxs-lookup"><span data-stu-id="b657f-109">Method Name</span></span>|<span data-ttu-id="b657f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b657f-110">Description</span></span>|<span data-ttu-id="b657f-111">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="b657f-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="b657f-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b657f-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="b657f-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="b657f-113">GroupBy</span></span>|<span data-ttu-id="b657f-114">Gruppen-Elemente, die ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="b657f-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="b657f-115">Jede Gruppe wird durch dargestellt ein <xref:System.Linq.IGrouping%602>Objekt.</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="b657f-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<span data-ttu-id="b657f-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b657f-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="b657f-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b657f-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="b657f-118">ToLookup</span><span class="sxs-lookup"><span data-stu-id="b657f-118">ToLookup</span></span>|<span data-ttu-id="b657f-119">Fügt Elemente in einer <xref:System.Linq.Lookup%602>(ein&1;: n-Wörterbuch) basierend auf einer Schlüsselauswahlfunktion.</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="b657f-119">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="b657f-120">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="b657f-120">Not applicable.</span></span>|<span data-ttu-id="b657f-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b657f-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="b657f-122">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="b657f-122">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="b657f-123">Im folgenden Codebeispiel wird die `Group By` -Klausel, um die Gruppe von Ganzzahlen in einer Liste nach, ob sie gerade oder ungerade sind.</span><span class="sxs-lookup"><span data-stu-id="b657f-123">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a><span data-ttu-id="b657f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b657f-124">See Also</span></span>  
 <span data-ttu-id="b657f-125"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="b657f-125"><xref:System.Linq></span></span>   
<span data-ttu-id="b657f-126"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b657f-126"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="b657f-127"> [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="b657f-127"> [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span></span>  
<span data-ttu-id="b657f-128"> [Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span><span class="sxs-lookup"><span data-stu-id="b657f-128"> [How to: Group Files by Extension (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span></span>  
<span data-ttu-id="b657f-129"> [Gewusst wie: Teilen eine Datei in mehrere Dateien mithilfe von Gruppen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span><span class="sxs-lookup"><span data-stu-id="b657f-129"> [How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span></span>
