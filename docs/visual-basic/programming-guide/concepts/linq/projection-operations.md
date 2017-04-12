---
title: "Projektionsvorgänge (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8876e65e752e0b18404ec32aecdcad7805533840
ms.lasthandoff: 03/13/2017

---
# <a name="projection-operations-visual-basic"></a>Projektionsvorgänge (Visual Basic)
Projektion bezeichnet das Transformieren eines Objekts in ein neues Format, das häufig nur aus den Eigenschaften besteht, die später verwendet wird. Mithilfe der Projektion können Sie einen neuen Typ erstellen, der aus den einzelnen Objekten erstellt wird. Sie können eine Eigenschaft projiziert und eine mathematische Funktion für sie ausführen. Sie können auch das ursprüngliche Objekt projizieren, ohne es zu konvertieren.  
  
 Die Standardabfrageoperator-Methoden, die Projektion ausführen, werden im folgenden Abschnitt aufgelistet.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Auswählen|Werte, die auf einer Transformationsfunktion basieren.|`Select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=fullName></xref:System.Linq.Queryable.Select%2A?displayProperty=fullName>|  
|SelectMany|Projiziert Sequenzen von Werten, die auf einer Transformationsfunktion basieren, und fasst diese dann in einer einzigen Sequenz.|Verwenden Sie mehrere `From` Klauseln|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName></xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax  
  
### <a name="select"></a>Auswählen  
 Im folgenden Beispiel wird die `Select` -Klausel, um den ersten Buchstaben der einzelnen Zeichenfolgen aus einer Liste von Zeichenfolgen projizieren.  
  
```vb  
Dim words = New List(Of String) From {"an", "apple", "a", "day"}  
  
Dim query = From word In words   
            Select word.Substring(0, 1)  
  
Dim sb As New System.Text.StringBuilder()  
For Each letter As String In query  
    sb.AppendLine(letter)  
Next  
  
' Display the output.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' a  
' a  
' a  
' d  
```  
  
### <a name="selectmany"></a>SelectMany  
 Im folgende Beispiel wird mithilfe mehrerer `From` -Klauseln, um jedes Wort der einzelnen Zeichenfolgen aus einer Liste von Zeichenfolgen projizieren.  
  
```vb  
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}  
  
Dim query = From phrase In phrases   
            From word In phrase.Split(" "c)   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the output.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' an  
' apple  
' a  
' day  
' the  
' quick  
' brown  
' fox  
```  
  
## <a name="select-versus-selectmany"></a>Wählen Sie im Vergleich zu SelectMany  
 Die Arbeit der beiden `Select()` und `SelectMany()` besteht darin, einen Ergebniswert (oder Werte) aus der Source-Werte. `Select()`generiert einen Ergebniswert für jeden Quellwert. Das Ergebnis ist daher eine Auflistung, die die gleiche von Elementen wie die quellauflistung Anzahl. Im Gegensatz dazu `SelectMany()` erzeugt ein einziges Gesamtergebnis, die verkettete untergeordnete Sammlungen aus jedem Quellwert enthält. Die Transformationsfunktion, die als Argument übergeben wird, `SelectMany()` muss eine aufzählbare Sequenz von Werten für jeden Quellwert zurückgeben. Diese aufzählbaren Sequenzen werden verkettet, von `SelectMany()` zu einer großen Sequenz.  
  
 Die folgenden zwei Abbildungen zeigen die konzeptionellen Unterschied zwischen den Aktionen der beiden Methoden. In jedem Fall wird davon ausgegangen Sie, dass die Auswahlfunktion (Transformation) das Array von Blumen aus jedem Quellwert auswählt.  
  
 Diese Abbildung zeigt, wie `Select()` gibt eine Auflistung, die die gleiche von Elementen als Auflistung Anzahl zurück.  
  
 ![Konzeptionelle Darstellung der Aktion Select()](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")  
  
 Diese Abbildung zeigt, wie `SelectMany()` verkettet die intermediate Sequenz von Arrays in einem Endergebnis-Wert, der jeden Wert aus jedem intermediate Array enthält.  
  
 ![Grafik, die der Aktion SelectMany(). ] (../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")  
  
### <a name="code-example"></a>Codebeispiel  
 Im folgenden Beispiel wird das Verhalten der `Select()` und `SelectMany()`. Der Code erstellt eine "Zukunft" Blumen dazu führt er die ersten beiden Elemente aus jeder Liste der Namen der Blume in der Auflistung. In diesem Beispiel "einzelner Wert", der Transformationsfunktion <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>verwendet wird, ist selbst eine Auflistung von Werten.</xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> Dies erfordert, dass die zusätzlichen `For Each` Schleife um jede Zeichenfolge in den einzelnen Untersequenzen aufgelistet.  
  
```vb  
Class Bouquet  
    Public Flowers As List(Of String)  
End Class  
  
Sub SelectVsSelectMany()  
    Dim bouquets = New List(Of Bouquet) From {   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}  
  
    Dim output As New System.Text.StringBuilder  
  
    ' Select()  
    Dim query1 = bouquets.Select(Function(b) b.Flowers)  
  
    output.AppendLine("Using Select():")  
    For Each flowerList In query1  
        For Each str As String In flowerList  
            output.AppendLine(str)  
        Next  
    Next  
  
    ' SelectMany()  
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)  
  
    output.AppendLine(vbCrLf & "Using SelectMany():")  
    For Each str As String In query2  
        output.AppendLine(str)  
    Next  
  
    ' Display the output  
    MsgBox(output.ToString())  
  
    ' This code produces the following output:  
    '  
    ' Using Select():  
    ' sunflower  
    ' daisy  
    ' daffodil  
    ' larkspur  
    ' tulip  
    ' rose  
    ' orchid  
    ' gladiolis  
    ' lily  
    ' snapdragon  
    ' aster  
    ' protea  
    ' larkspur  
    ' lilac  
    ' iris  
    ' dahlia  
  
    ' Using SelectMany()  
    ' sunflower  
    ' daisy  
    ' daffodil  
    ' larkspur  
    ' tulip  
    ' rose  
    ' orchid  
    ' gladiolis  
    ' lily  
    ' snapdragon  
    ' aster  
    ' protea  
    ' larkspur  
    ' lilac  
    ' iris  
    ' dahlia  
  
End Sub  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq></xref:System.Linq>   
 [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [SELECT-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md)   
 [Gewusst wie: Kombinieren von Daten mithilfe von Joins](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)   
 [Gewusst wie: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)   
 [Gewusst wie: zurückgeben ein LINQ-Abfrageergebnisses als einen bestimmten Typ](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md)   
 [Gewusst wie: Teilen eine Datei in mehrere Dateien mithilfe von Gruppen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
