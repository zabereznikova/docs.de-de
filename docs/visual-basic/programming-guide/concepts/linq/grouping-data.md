---
title: Gruppieren von Daten (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5f2e5c4c4713f1056f1eb2243f27e5acf0494542
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="e3c53-102">Gruppieren von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3c53-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="e3c53-103">Als „Gruppieren“ wird das Anordnen von Daten in Gruppen bezeichnet, sodass die Elemente in jeder Gruppe über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="e3c53-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="e3c53-104">Die folgende Abbildung zeigt die Ergebnisse der Gruppierung einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e3c53-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="e3c53-105">Der Schlüssel für jede Gruppe ist das Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e3c53-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="e3c53-106">![LINQ-Gruppierungsvorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="e3c53-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="e3c53-107">Die Methoden des Standardabfrageoperators, die Datenelemente gruppieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e3c53-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3c53-108">Methoden</span><span class="sxs-lookup"><span data-stu-id="e3c53-108">Methods</span></span>  
  
|<span data-ttu-id="e3c53-109">Methodenname</span><span class="sxs-lookup"><span data-stu-id="e3c53-109">Method Name</span></span>|<span data-ttu-id="e3c53-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3c53-110">Description</span></span>|<span data-ttu-id="e3c53-111">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="e3c53-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="e3c53-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3c53-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="e3c53-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="e3c53-113">GroupBy</span></span>|<span data-ttu-id="e3c53-114">Gruppenelemente, die über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="e3c53-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="e3c53-115">Jede Gruppe wird durch ein <xref:System.Linq.IGrouping%602>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e3c53-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e3c53-116">ToLookup</span><span class="sxs-lookup"><span data-stu-id="e3c53-116">ToLookup</span></span>|<span data-ttu-id="e3c53-117">Fügt Elemente basierend auf einer Schlüsselauswahlfunktion in eine <xref:System.Linq.Lookup%602>-Klasse (one-to-many-Wörterbuch) ein.</span><span class="sxs-lookup"><span data-stu-id="e3c53-117">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="e3c53-118">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="e3c53-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="e3c53-119">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="e3c53-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="e3c53-120">Im folgenden Codebeispiel wird die `Group By`-Klausel angewandt, um die Gruppe ganzer Zahlen in Listen mit geraden und ungeraden Zahlen zu aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="e3c53-120">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3c53-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3c53-121">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="e3c53-122">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="e3c53-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="e3c53-123">Group By-Klausel</span><span class="sxs-lookup"><span data-stu-id="e3c53-123">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)  
 [<span data-ttu-id="e3c53-124">Vorgehensweise: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3c53-124">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 [<span data-ttu-id="e3c53-125">Vorgehensweise: Teilen einer Datei in mehrere Dateien mithilfe von Gruppen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3c53-125">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
