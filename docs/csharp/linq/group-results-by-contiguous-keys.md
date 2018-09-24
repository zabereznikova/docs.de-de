---
title: Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie mit LINQ in C# Ergebnisse nach zusammenhängenden Schlüsseln gruppieren.
ms.date: 08/14/2018
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: b5753c85bb07be4fc84b78a299eece961969ff9d
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46696954"
---
# <a name="group-results-by-contiguous-keys"></a>Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln

Im folgende Beispiel wird veranschaulicht, wie Elemente in Segmenten gruppiert werden, die Untersequenzen von zusammenhängenden Schlüsseln darstellen. Gehen wir beispielsweise von der folgenden Sequenz von Schlüssel-Wert-Paaren aus:

|Key|Wert|
|---------|-----------|
|A|Wir|
|A|finden|
|A|dass|
|B|LINQ|
|C|echt|
|A|cool|
|B|ist|
|B|!|

Die folgenden Gruppen werden in dieser Reihenfolge erstellt:

1. Wir, finden, dass

2. LINQ

3. echt

4. cool

5. ist, !

Die Lösung wird als threadsichere Erweiterungsmethode implementiert, die die Ergebnisse streamend zurückgibt. Das bedeutet, dass die Methode während dem Durchlaufen der Quellsequenz die Gruppen erzeugt. Im Gegensatz zu den Operatoren `group` und `orderby` kann die Methode mit dem Zurückgeben der Gruppen an den Aufrufer beginnen, bevor die ganze Sequenz gelesen wurde.

Um Threadsicherheit zu gewährleisten, wird bei der Iteration der Gruppe eine Kopie der Gruppe oder des Abschnitts erstellt, wie in den Quellcodekommentaren erläutert. Wenn die Quellsequenz eine lange Sequenz von zusammenhängenden Elementen enthält, löst die Common Language Runtime möglicherweise eine <xref:System.OutOfMemoryException>-Ausnahme aus.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden die Erweiterungsmethode und der Clientcode gezeigt, der sie verwendet:

[!code-csharp[cscsrefContiguousGroups#1](~/samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]

Um die Erweiterungsmethode in Ihrem Projekt zu verwenden, kopieren Sie die statische `MyExtensions`-Klasse in eine neue oder eine vorhandene Datenquelldatei, und fügen Sie, falls erforderlich, am Speicherort eine `using`-Direktive für den Namespace hinzu.

## <a name="see-also"></a>Siehe auch

- [Language-Integrated Query (LINQ)](index.md)
