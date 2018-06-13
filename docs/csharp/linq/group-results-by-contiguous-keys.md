---
title: Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln
description: So gruppieren Sie Ergebnisse nach zusammenhängenden Schlüsseln
ms.date: 12/1/2016
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: a8d6ac133932a12154d5b23454065144c7652067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281436"
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
  
1.  Wir, finden, dass  
  
2.  LINQ  
  
3.  echt  
  
4.  cool  
  
5.  ist, !  
  
 Die Lösung wird als threadsichere Erweiterungsmethode implementiert, die die Ergebnisse streamend zurückgibt. Das bedeutet, dass die Methode während dem Durchlaufen der Quellsequenz die Gruppen erzeugt. Im Gegensatz zu den Operatoren `group` und `orderby` kann die Methode mit dem Zurückgeben der Gruppen an den Aufrufer beginnen, bevor die ganze Sequenz gelesen wurde.  
  
 Um Threadsicherheit zu gewährleisten, wird bei der Iteration der Gruppe eine Kopie der Gruppe oder des Abschnitts erstellt, wie in den Quellcodekommentaren erläutert. Wenn die Quellsequenz eine lange Sequenz von zusammenhängenden Elementen enthält, löst die Common Language Runtime möglicherweise eine <xref:System.OutOfMemoryException>-Ausnahme aus.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Erweiterungsmethode und der die Methode verwendende Clientcode gezeigt.  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 Um die Erweiterungsmethode in Ihrem Projekt zu verwenden, kopieren Sie die statische `MyExtensions`-Klasse in eine neue oder eine vorhandene Datenquelldatei, und fügen Sie, falls erforderlich, am Speicherort eine `using`-Direktive für den Namespace hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)  
 
