---
title: Gruppieren von Daten
ms.date: 07/20/2015
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
ms.openlocfilehash: 8996eee748489c596bc5adc32f53b6b39dbfc6ac
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398382"
---
# <a name="grouping-data-visual-basic"></a>Gruppieren von Daten (Visual Basic)
Als „Gruppieren“ wird das Anordnen von Daten in Gruppen bezeichnet, sodass die Elemente in jeder Gruppe über ein gemeinsames Attribut verfügen.  
  
 Die folgende Abbildung zeigt die Ergebnisse der Gruppierung einer Zeichenfolge. Der Schlüssel für jede Gruppe ist das Zeichen.  
  
 ![Diagramm, das eine LINQ-Gruppierung zeigt.](./media/grouping-data/linq-group-operation.png)  
  
 Die Methoden des Standardabfrageoperators, die Datenelemente gruppieren, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|Syntax von Visual Basic-Abfrage Ausdrücken|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|GroupBy|Gruppenelemente, die über ein gemeinsames Attribut verfügen. Jede Gruppe wird durch ein <xref:System.Linq.IGrouping%602>-Objekt dargestellt.|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|ToLookup|Fügt Elemente basierend auf einer Schlüsselauswahlfunktion in eine <xref:System.Linq.Lookup%602>-Klasse (one-to-many-Wörterbuch) ein.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Beispiele für die Abfrageausdruckssyntax  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](standard-query-operators-overview.md)
- [Group By-Klausel](../../../language-reference/queries/group-by-clause.md)
- [Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic)](how-to-group-files-by-extension-linq.md)
- [Vorgehensweise: Aufteilen einer Datei in viele Dateien mithilfe von Gruppen (LINQ) (Visual Basic)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
