---
title: Arraydimensionen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 5ba92e113faf9d68bad97968937cc736132b2065
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708531"
---
# <a name="array-dimensions-in-visual-basic"></a>Arraydimensionen in Visual Basic
Ein *Dimension* ist eine Richtung, in dem Sie die Spezifikation der Elemente eines Arrays können variieren. Ein Array, das den Umsatz für jeden Tag des Monats insgesamt enthält hat es sich um eine Dimension (Tag des Monats). Ein Array, das den Umsatz nach Abteilung für jeden Tag des Monats insgesamt enthält verfügt über zwei Dimensionen (die Abteilung-Anzahl und den Tag des Monats). Wird aufgerufen, die Anzahl der Dimensionen, die ein Array hat seine *Rang*.  
  
> [!NOTE]
>  Sie können die <xref:System.Array.Rank%2A> Eigenschaft, um zu bestimmen, wie viele Dimensionen ein Array enthält.  
  
## <a name="working-with-dimensions"></a>Arbeiten mit Dimensionen  
 Sie geben Sie ein Element eines Arrays durch Angabe einer *Index* oder *Feldindex* für jeden seiner Dimensionen. Die Elemente sind über die einzelnen Dimensionen von Index 0 bis zum höchsten Indexwert für diese Dimension zusammenhängenden.  
  
 Die folgenden Abbildungen zeigen die grundlegende Struktur von Arrays mit unterschiedlichem Rang. Jedes Element in den Abbildungen zeigt die Werte des Indexes, die darauf zugreifen. Sie können z. B. das erste Element der zweiten Zeile des zweidimensionalen Arrays zugreifen, durch Angabe von Indizes `(1, 0)`.  
  
 ![Grafisches Diagramm eines&#45;-dimensionales Array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")  
Eindimensionale Arrays  
  
 ![Grafisches Diagramm der beiden&#45;-dimensionales Array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")  
zweidimensionales array  
  
 ![Grafisches Diagramm der drei&#45;-dimensionales Array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")  
dreidimensionale array  
  
### <a name="one-dimension"></a>Eine Dimension  
 Viele Arrays haben nur eine Dimension, wie z. B. die Anzahl der einzelnen Altersgruppen. Die einzige Voraussetzung für ein Element angeben, ist das Alter, das die Anzahl die dieses Element enthält. Aus diesem Grund wird ein entsprechendes Array nur ein Index verwendet. Das folgende Beispiel deklariert eine Variable für eine *eindimensionales Array* ALT Anzahl der Zugriffe von 0 bis 120.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a>Zwei Dimensionen  
 Einige Arrays haben zwei Dimensionen, z. B. die Anzahl der Niederlassungen auf jede Boden der jedes Gebäude an einem Campus. Die Spezifikation eines Elements erfordert, Erstellen von Anzahl und der Boden und jedes Element enthält die Anzahl der für diese Kombination von Gebäude und Etage. Aus diesem Grund wird ein entsprechendes Array zwei Indizes verwendet. Das folgende Beispiel deklariert eine Variable für eine *zweidimensionales Array* der Anzahl der Büros, Gebäuden 0 bis 40 und Stockwerken 0 bis 5.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 Ein zweidimensionales Array wird auch bezeichnet ein *rechteckiges Array*.  
  
### <a name="three-dimensions"></a>Drei Dimensionen  
 Einige Arrays haben drei Dimensionen, z. B. Werte im dreidimensionalen Raum. Ein solches Array verwendet drei Indizes, die in diesem Fall die x-, y- und Z-Koordinaten des physischen Speicherplatzes darstellen. Das folgende Beispiel deklariert eine Variable für eine *dreidimensionale Array* Air temperaturspalte an verschiedenen Punkten in einem dreidimensionalen Volume.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a>Mehr als drei Dimensionen  
 Obwohl ein Array mit bis zu 32 Dimensionen aufweisen kann, ist es selten um mehr als drei zu erhalten.  
  
> [!NOTE]
>  Wenn Sie die Dimensionen in ein Array hinzufügen, erhöht der gesamte Speicher erforderlich, die vom Array sind beträchtlich, also verwenden mehrdimensionale Arrays mit Vorsicht.  
  
## <a name="using-different-dimensions"></a>Verwenden von verschiedenen Dimensionen  
 Angenommen Sie, Sie Umsätze für jeden Tag des aktuellen Monats nachverfolgen möchten. Sie können ein eindimensionales Array mit 31 Elementen deklarieren, eine für jeden Tag des Monats, wie im folgenden Beispiel wird gezeigt.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 Jetzt nehmen Sie die gleiche Informationen nicht nur für jeden Tag eines Monats, sondern auch für jeden Monat des Jahres nachverfolgen möchten. Sie können ein zweidimensionales Array mit 12 Zeilen (für die Monate) und 31 Spalten (für die Tage), wie im folgenden Beispiel gezeigt deklarieren.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 Angenommen, Sie entscheiden, damit Ihr Array enthalten jetzt Informationen für mehr als ein Jahr. Wenn Sie die Umsatzbeträge für fünf Jahre nachverfolgen möchten, können Sie ein dreidimensionales Array mit 5 Ebenen, 12 Zeilen und 31 Spalten, wie im folgenden Beispiel gezeigt deklarieren.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 Beachten Sie Folgendes: Da jeder Index von 0 abweicht, die auf seinen Maximalwert, jede Dimension des `salesAmounts` als eins kleiner ist als die erforderliche Länge für diese Dimension deklariert wird. Beachten Sie, dass die Größe des Arrays mit jeder neuen Dimension zunimmt. Die drei Größen in den vorherigen Beispielen werden 31 372 und 1.860 Elementen.  
  
> [!NOTE]
>  Sie können ein Array erstellen, ohne die `Dim` Anweisung oder der `New` Klausel. Sie können z. B. Aufrufen der <xref:System.Array.CreateInstance%2A> Methode oder eine andere Komponente kann Ihren Code auf diese Weise erstellte Array übergeben. Ein Array dieser Art lassen sich auf eine unteren Grenze ungleich 0. Sie können immer auf die untere Grenze einer Dimension testen, mit der <xref:System.Array.GetLowerBound%2A> Methode oder der `LBound` Funktion.  
  
## <a name="see-also"></a>Siehe auch
- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Problembehandlung bei Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
