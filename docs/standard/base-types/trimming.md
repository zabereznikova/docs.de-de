---
title: Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen in .NET
description: Erfahren Sie, wie Sie Leerzeichen am Anfang oder Ende einer Zeichenfolge kürzen, oder wie Sie eine beliebige Anzahl von Leerzeichen oder Zeichen ab einer angegebenen Position in der Zeichenfolge in .NET entfernen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
ms.openlocfilehash: 8bc2980aa887dc652485e135058b9f6f718e7b45
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831272"
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a>Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen in .NET
Wenn Sie einen Satz in einzelne Wörter auflösen, erhalten Sie möglicherweise Wörter mit Leerzeichen (auch als Leerräume bezeichnet) auf beiden Seiten des jeweiligen Wortes. In diesem Fall können Sie eine der Entfernungsmethoden aus der **System.String**-Klasse verwenden, um an einer bestimmten Position der Zeichenfolge eine beliebige Anzahl von Leerzeichen oder anderen Zeichen zu entfernen. In der folgenden Tabelle sind die verfügbaren Entfernungsmethoden aufgeführt.  
  
|Methodenname|Verwendung|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|Entfernt in einem Zeichenarray angegebene Leerzeichen am Anfang und Ende einer Zeichenfolge.|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|Entfernt in einem Zeichenarray angegebene Zeichen am Ende einer Zeichenfolge.|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|Entfernt in einem Zeichenarray angegebene Zeichen am Anfang einer Zeichenfolge.|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|Entfernt eine festgelegte Anzahl von Zeichen an der angegebenen Indexposition in einer Zeichenfolge.|  
  
## <a name="trim"></a>Trim

 Wie das folgende Beispiel zeigt, lassen sich mit der <xref:System.String.Trim%2A?displayProperty=nameWithType>-Methode Leerzeichen an beiden Enden einer Zeichenfolge auf einfache Weise entfernen.  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 Sie können auch Zeichen am Anfang und am Ende einer Zeichenfolge entfernen, die Sie in einem Zeichenarray angeben. Im folgenden Beispiel werden Leerzeichen, Punkte und Sternchen entfernt.  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a>TrimEnd

 Mit der **String.TrimEnd**-Methode werden Zeichen am Ende einer Zeichenfolge entfernt, wodurch ein neues Zeichenfolgenobjekt entsteht. An diese Methode wird ein Zeichenarray übergeben, das die zu entfernenden Zeichen enthält. Die Reihenfolge der Elemente im Zeichenarray hat keine Auswirkungen auf den Entfernungsvorgang. Der Vorgang wird beendet, sobald ein nicht im Array angegebenes Zeichen gefunden wird.  
  
 Im folgenden Beispiel werden die letzten Buchstaben einer Zeichenfolge mit der **TrimEnd**-Methode entfernt. In diesem Beispiel werden die Positionen der Zeichen `'r'` und `'W'` vertauscht, um zu veranschaulichen, dass die Reihenfolge der Zeichen im Array keine Rolle spielt. Beachten Sie, dass durch diesen Code das letzte Wort von `MyString` sowie ein Teil des ersten Wortes entfernt wird.  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 Durch diesen Code wird `He` auf der Konsole angezeigt.  
  
 Im folgenden Beispiel wird das letzte Wort einer Zeichenfolge mit der **TrimEnd**-Methode entfernt. Im Code folgt auf das Wort `Hello` ein Komma. Da das Komma im Zeichenarray nicht als zu entfernendes Zeichen angegeben ist, wird der Vorgang beim Komma beendet.  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 Durch diesen Code wird `Hello,` auf der Konsole angezeigt.  
  
## <a name="trimstart"></a>TrimStart

 Die **String.TrimStart**-Methode ist mit der **String.TrimEnd**-Methode vergleichbar, außer dass eine neue Zeichenfolge erstellt wird, indem Zeichen am Anfang eines bestehenden Zeichenfolgenobjekts entfernt werden. An die **TrimStart**-Methode wird ein Zeichenarray übergeben, das die zu entfernenden Zeichen enthält. Wie bei der **TrimEnd**-Methode hat die Reihenfolge der Elemente im Zeichenarray keine Auswirkungen auf den Entfernungsvorgang. Der Vorgang wird beendet, sobald ein nicht im Array angegebenes Zeichen gefunden wird.  
  
 Im folgenden Beispiel wird das erste Wort einer Zeichenfolge entfernt. In diesem Beispiel werden die Positionen der Zeichen `'l'` und `'H'` vertauscht, um zu veranschaulichen, dass die Reihenfolge der Zeichen im Array keine Rolle spielt.  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 Durch diesen Code wird `World!` auf der Konsole angezeigt.  
  
## <a name="remove"></a>Remove

 Mit der <xref:System.String.Remove%2A?displayProperty=nameWithType>-Methode wird an einer festgelegten Position innerhalb einer bestehenden Zeichenfolge eine festgelegte Anzahl von Zeichen entfernt. Diese Methode setzt einen nullbasierten Index voraus.  
  
 Im folgenden Beispiel werden ausgehend von der fünften Position des nullbasierten Zeichenfolgenindizes zehn Zeichen aus einer Zeichenfolge entfernt.  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
## <a name="replace"></a>Ersetzen von

 Sie können auch ein bestimmtes Zeichen oder eine Teilzeichenfolge aus einer Zeichenfolge entfernen, indem Sie die <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType>-Methode aufrufen und eine leere Zeichenfolge (<xref:System.String.Empty?displayProperty=nameWithType>) zum Ersetzen angeben. Im folgenden Beispiel werden alle Kommas in einer Zeichenfolge entfernt.  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a>Siehe auch

- [Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)
