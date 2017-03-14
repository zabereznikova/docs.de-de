---
title: "Array Dimensions in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "dimensions, arrays"
  - "arrays [Visual Basic], dimensions"
  - "arrays [Visual Basic], rectangular"
  - "arrays [Visual Basic], rank"
  - "rectangular arrays"
  - "ranking, arrays"
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Array Dimensions in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine *Dimension* ist eine Richtung, in der sich die Spezifikation von Arrayelementen variieren lässt.  Ein Array, in dem die Tagesverkaufsumsätze eines Monats abgelegt sind, hat eine Dimension \(Tag des Monats\).  Ein Array, in dem die Tagesverkaufsumsätze einzelner Abteilungen abgelegt sind, hat zwei Dimensionen \(Abteilungsnummer und Tag des Monats\).  Die Anzahl der Dimensionen eines Arrays wird als *Rang* bezeichnet.  
  
> [!NOTE]
>  Mit der <xref:System.Array.Rank%2A>\-Eigenschaft können Sie bestimmen, wie viele Dimensionen ein Array aufweist.  
  
## Arbeiten mit Dimensionen  
 Ein Arrayelement wird durch die Angabe eines *Index*\- oder *Subscript*\-Werts seiner Dimensionen identifiziert.  Die Elemente einer Dimension sind vom Index 0 bis zum höchsten Indexwert der Dimension zusammenhängend angeordnet.  
  
 In den folgenden Abbildungen wird das Strukturkonzept von Arrays mit unterschiedlichen Rängen dargestellt.  Für jedes abgebildete Element wird der Indexwert angegeben, über den darauf zugegriffen werden kann.  Beispielsweise kann durch die Angabe der Indizes `(1, 0)` auf das erste Element der zweiten Zeile des zweidimensionalen Arrays zugegriffen werden.  
  
 ![Grafisches Diagramm eines eindimensionalen Arrays](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.png "ArrayExDimOne")  
Eindimensionales Array  
  
 ![Grafisches Diagramm eines zweidimensionalen Arrays](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")  
Zweidimensionales Array  
  
 ![Grafisches Diagramm eines dreidimensionalen Arrays](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.png "ArrayExDimThree")  
Dreidimensionales Array  
  
### Eine Dimension  
 Viele Arrays haben nur eine Dimension, etwa die Anzahl von Personen verschiedener Altersgruppen.  Zur Festlegung eines Elements ist lediglich die Angabe der Altersgruppe erforderlich, deren Anzahl im Element abgelegt ist.  Deshalb wird für ein solches Array nur ein Index verwendet.  Im folgenden Beispiel wird eine Variable deklariert, die ein *eindimensionales Array* enthalten soll, in dem die Anzahl der Personen mit einem Alter von 0 bis 120 Jahren aufgeführt sind.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### Zwei Dimensionen  
 Einige Arrays haben zwei Dimensionen, beispielsweise die Anzahl der Büros in den einzelnen Stockwerken der verschiedenen Gebäude auf einem Universitäts\- oder Firmengelände.  Zur Festlegung eines Elements müssen sowohl die Gebäudenummer als auch das Stockwerk angegeben werden. Außerdem ist in jedem Element die Anzahl der Büros für die betreffende Kombination von Gebäude und Stockwerk abgelegt.  Deshalb werden für ein solches Array zwei Indizes verwendet.  Im folgenden Beispiel wird eine Variable deklariert, die ein *zweidimensionales Array* mit der Anzahl der Büros in den Gebäuden 0 bis 40 und den Stockwerken 0 bis 5 enthalten soll.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 Ein zweidimensionales Array wird auch als *rechteckiges Array* bezeichnet.  
  
### Drei Dimensionen  
 Einige Arrays haben drei Dimensionen, z. B. Werte des dreidimensionalen Raums.  Für ein solches Array werden drei Indizes verwendet, die in diesem Fall die Koordinaten x, y und z des physikalischen Raums darstellen.  Im folgenden Beispiel wird eine Variable deklariert, die ein *dreidimensionales Array* mit den Lufttemperaturen verschiedener Punkte eines dreidimensionalen Raums enthalten soll.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### Mehr als drei Dimensionen  
 Obwohl ein Array 32 Dimensionen haben kann, werden selten Arrays mit mehr als drei Dimensionen verwendet.  
  
> [!NOTE]
>  Wenn Sie einem Array Dimensionen hinzufügen, erfordert dieses Array insgesamt erheblich mehr Speicher. Sie sollten daher mehrdimensionale Arrays mit Bedacht verwenden.  
  
## Verwenden von verschiedenen Dimensionen  
 Angenommen, Sie möchten die Tagesverkaufsumsätze des aktuellen Monats verfolgen.  Sie können hierzu, wie im folgenden Beispiel gezeigt, ein eindimensionales Array mit 31 Elementen deklarieren, die jeweils einen Tag des Monats darstellen.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 Nehmen wir weiter an, Sie möchten nicht nur die Daten für die einzelnen Tage eines Monats verfolgen, sondern auch die Daten für die einzelnen Monate eines Jahres.  Sie können hierzu, wie im folgenden Beispiel gezeigt, ein zweidimensionales Array mit 12 Zeilen \(für die Monate\) und 31 Spalten \(für die Tage\) deklarieren.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 Nehmen wir nun an, Sie möchten in diesem Array Daten über mehrere Jahre ablegen.  Wenn Sie die Umsatzzahlen über 5 Jahre hinweg verfolgen möchten, können Sie, wie im folgenden Beispiel gezeigt, ein dreidimensionales Array mit 5 Schichten, 12 Zeilen und 31 Spalten deklarieren.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 Beachten Sie, dass jede Dimension von `salesAmounts` als Wert deklariert wird, der um eins geringer als die erforderliche Länge der Dimension ist, weil der Index mit 0 beginnend bis zum Höchstwert gezählt wird.  Beachten Sie auch, dass die Größe des Arrays mit jeder neuen Dimension zunimmt.  Die drei Arrays in den vorherigen Beispielen haben eine Größe von 31, 372 bzw. 1.860 Elementen.  
  
> [!NOTE]
>  Arrays können auch ohne die `Dim`\-Anweisung oder die `New`\-Klausel erstellt werden.  Beispielsweise können Sie die <xref:System.Array.CreateInstance%2A>\-Methode aufrufen, oder eine andere Komponente kann Ihrem Code ein auf diese Weise erstelltes Array übergeben.  Ein solches Array kann eine untere Grenze besitzen, die ungleich 0 ist.  Mit der <xref:System.Array.GetLowerBound%2A>\-Methode bzw. der `LBound`\-Funktion können Sie die untere Grenze einer Dimension überprüfen.  
  
## Siehe auch  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Troubleshooting Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)