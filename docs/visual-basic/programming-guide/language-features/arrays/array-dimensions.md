---
title: Arraydimensionen
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 12e983ae62fa9f9ea762d434ffe5b73873a4a2e8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351905"
---
# <a name="array-dimensions-in-visual-basic"></a>Arraydimensionen in Visual Basic

Eine *Dimension* ist eine Richtung, in der Sie die Spezifikation der Elemente eines Arrays variieren können. Ein Array, das die Gesamtumsätze für jeden Tag des Monats enthält, verfügt über eine Dimension (den Tag des Monats). Ein Array, das die Gesamtumsätze pro Abteilung für jeden Tag des Monats enthält, hat zwei Dimensionen (die Abteilungs Nummer und den Tag des Monats). Die Anzahl der Dimensionen, die ein Array hat, wird als *Rang*bezeichnet.

> [!NOTE]
> Sie können die <xref:System.Array.Rank%2A>-Eigenschaft verwenden, um die Anzahl der Dimensionen eines Arrays zu bestimmen.

## <a name="working-with-dimensions"></a>Arbeiten mit Dimensionen

Sie geben ein Element eines Arrays an, indem Sie einen Index bereit *stellen oder für* jede seiner Dimensionen einen *Index* festlegen. Die Elemente sind zusammenhängend entlang jeder Dimension von Index 0 bis zum höchsten Index für diese Dimension.

Die folgenden Abbildungen zeigen die konzeptionelle Struktur von Arrays mit unterschiedlichen Rang folgen. Jedes Element in den Abbildungen zeigt die Indexwerte, die darauf zugreifen. Sie können z. b. auf das erste Element der zweiten Zeile des zweidimensionalen Arrays zugreifen, indem Sie die Indizes `(1, 0)`angeben.

![Diagramm, das ein eindimensionales Array anzeigt.](./media/array-dimensions/one-dimensional-array.gif)

![Diagramm, das ein zweidimensionales Array anzeigt.](./media/array-dimensions/two-dimensional-array.gif)

![Diagramm, das ein dreidimensionales Array anzeigt.](./media/array-dimensions/three-dimensional-array.gif)

### <a name="one-dimension"></a>Eine Dimension

Viele Arrays verfügen nur über eine Dimension, z. b. die Anzahl der Personen jedes Alters. Die einzige Anforderung, ein Element anzugeben, ist das Alter, für das dieses Element die Anzahl enthält. Daher verwendet ein solches Array nur einen Index. Im folgenden Beispiel wird eine Variable deklariert, die ein *eindimensionales Array* von Alters Zählungen für die Alters Zahlen 0 bis 120 enthält.

```vb
Dim ageCounts(120) As UInteger
```

### <a name="two-dimensions"></a>Zwei Dimensionen

Einige Arrays verfügen über zwei Dimensionen, z. b. die Anzahl der Niederlassungen in jeder Etage der einzelnen Gebäude auf einem Campus. Die Angabe eines Elements erfordert sowohl die Gebäude Nummer als auch die Etage, und jedes Element enthält die Anzahl für diese Kombination aus Gebäude und Etage. Daher verwendet ein solches Array zwei Indizes. Im folgenden Beispiel wird eine Variable deklariert, die ein *zweidimensionales Array* von Office-Zählungen enthält, für Gebäude 0 bis 40 und die Stock-Werte 0 bis 5.

```vb
Dim officeCounts(40, 5) As Byte
```

Ein zweidimensionales Array wird auch als *rechteckiges Array*bezeichnet.

### <a name="three-dimensions"></a>Drei Dimensionen

Einige Arrays verfügen über drei Dimensionen, z. b. Werte im dreidimensionalen Raum. Ein solches Array verwendet drei Indizes, die in diesem Fall die x-, y-und z-Koordinaten von physischem Raum darstellen. Im folgenden Beispiel wird eine Variable deklariert, die ein *dreidimensionales Array* von Lufttemperaturen an verschiedenen Punkten in einem dreidimensionalen Volume enthält.

```vb
Dim airTemperatures(99, 99, 24) As Single
```

### <a name="more-than-three-dimensions"></a>Mehr als drei Dimensionen

Obwohl ein Array bis zu 32 Dimensionen aufweisen kann, ist es selten, dass mehr als drei Dimensionen vorhanden sind.

> [!NOTE]
> Wenn Sie einem Array Dimensionen hinzufügen, erhöht sich der für das Array benötigte Gesamtspeicher erheblich. verwenden Sie daher mehrdimensionale Arrays mit Sorgfalt.

## <a name="using-different-dimensions"></a>Verwenden verschiedener Dimensionen

Angenommen, Sie möchten die Umsatz Beträge für jeden Tag des aktuellen Monats nachverfolgen. Sie können ein eindimensionales Array mit 31 Elementen deklarieren, eine für jeden Tag des Monats, wie im folgenden Beispiel gezeigt.

```vb
Dim salesAmounts(30) As Double
```

Nehmen Sie nun an, Sie möchten die gleichen Informationen nicht nur für jeden Tag eines Monats, sondern auch für jeden Monat des Jahres nachverfolgen. Sie können ein zweidimensionales Array mit 12 Zeilen (für die Monate) und 31 Spalten (für die Tage) deklarieren, wie im folgenden Beispiel gezeigt.

```vb
Dim salesAmounts(11, 30) As Double
```

Angenommen, Sie entscheiden sich dafür, dass Ihr Array Informationen für mehr als ein Jahr enthalten soll. Wenn Sie Umsatz Beträge für 5 Jahre nachverfolgen möchten, können Sie ein dreidimensionales Array mit 5 Ebenen, 12 Zeilen und 31 Spalten deklarieren, wie im folgenden Beispiel gezeigt.

```vb
Dim salesAmounts(4, 11, 30) As Double
```

Beachten Sie, dass jede Dimension von `salesAmounts` als die für diese Dimension erforderliche Länge deklariert wird, da jeder Index von 0 bis zum Maximum abweicht. Beachten Sie auch, dass sich die Größe des Arrays mit jeder neuen Dimension vergrößert. Die drei Größen in den vorangehenden Beispielen sind die Elemente 31, 372 und 1.860.

> [!NOTE]
> Sie können ein Array erstellen, ohne die `Dim`-Anweisung oder die `New`-Klausel zu verwenden. Beispielsweise können Sie die <xref:System.Array.CreateInstance%2A>-Methode oder eine andere Komponente den Code an ein auf diese Weise erstelltes Array übergeben. Ein solches Array kann eine untere Grenze aufweisen, die nicht 0 (null) ist. Mit der <xref:System.Array.GetLowerBound%2A>-Methode oder der `LBound`-Funktion können Sie immer die untere Grenze einer Dimension testen.

## <a name="see-also"></a>Siehe auch

- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Problembehandlung bei Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
