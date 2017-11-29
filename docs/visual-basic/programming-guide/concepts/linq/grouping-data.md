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
# <a name="grouping-data-visual-basic"></a>Gruppieren von Daten (Visual Basic)
Als „Gruppieren“ wird das Anordnen von Daten in Gruppen bezeichnet, sodass die Elemente in jeder Gruppe über ein gemeinsames Attribut verfügen.  
  
 Die folgende Abbildung zeigt die Ergebnisse der Gruppierung einer Zeichenfolge. Der Schlüssel für jede Gruppe ist das Zeichen.  
  
 ![LINQ-Gruppierungsvorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")  
  
 Die Methoden des Standardabfrageoperators, die Datenelemente gruppieren, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|GroupBy|Gruppenelemente, die über ein gemeinsames Attribut verfügen. Jede Gruppe wird durch ein <xref:System.Linq.IGrouping%602>-Objekt dargestellt.|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|ToLookup|Fügt Elemente basierend auf einer Schlüsselauswahlfunktion in eine <xref:System.Linq.Lookup%602>-Klasse (one-to-many-Wörterbuch) ein.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Beispiel für die Abfrageausdruckssyntax  
 Im folgenden Codebeispiel wird die `Group By`-Klausel angewandt, um die Gruppe ganzer Zahlen in Listen mit geraden und ungeraden Zahlen zu aufzuteilen.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq>  
 [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md)  
 [Vorgehensweise: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 [Vorgehensweise: Teilen einer Datei in mehrere Dateien mithilfe von Gruppen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
