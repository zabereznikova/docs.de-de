---
title: Vergleichen von Zeichenfolgen in .NET
description: In diesem Artikel werden Methoden zum Vergleichen von Zeichenfolgen in .NET behandelt. Erfahren Sie mehr über die Methoden Compare, CompareOrdinal, CompareTo, StartsWith, EndsWith, Equals, IndexOf und LastIndexOf.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- value comparisons of strings
- LastIndexOf method
- CompareTo method
- IndexOf method
- Compare method
- strings [.NET], comparing
- CompareOrdinal method
- EndsWith method
- Equals method
- StartsWith method
ms.assetid: 977dc094-fe19-4955-98ec-d2294d04a4ba
ms.openlocfilehash: 658f8b2cf7d7b2431654df1caebdac8118b3674b
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889490"
---
# <a name="comparing-strings-in-net"></a>Vergleichen von Zeichenfolgen in .NET
.NET stellt mehrere Methoden bereit, um Werte von Zeichenfolgen zu vergleichen. In der folgenden Tabelle werden die Methoden zum Vergleichen von Werten aufgeführt und beschrieben.  
  
|Methodenname|Verwendung|  
|-----------------|---------|  
|<xref:System.String.Compare%2A?displayProperty=nameWithType>|Vergleicht die Werte zweier Zeichenfolgen. Gibt einen Ganzzahlwert zurück.|  
|<xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType>|Vergleicht zwei Zeichenfolgen, ohne die Einstellungen der lokalen Kultur zu berücksichtigen. Gibt einen Ganzzahlwert zurück.|  
|<xref:System.String.CompareTo%2A?displayProperty=nameWithType>|Vergleicht das aktuelle Zeichenfolgenobjekt mit einer anderen Zeichenfolge. Gibt einen Ganzzahlwert zurück.|  
|<xref:System.String.StartsWith%2A?displayProperty=nameWithType>|Stellt fest, ob eine Zeichenfolge mit der übergebenen Zeichenfolge beginnt. Gibt einen booleschen Wert zurück.|  
|<xref:System.String.EndsWith%2A?displayProperty=nameWithType>|Stellt fest, ob eine Zeichenfolge mit der übergebenen Zeichenfolge endet. Gibt einen booleschen Wert zurück.|  
|<xref:System.String.Equals%2A?displayProperty=nameWithType>|Stellt fest, ob zwei Zeichenfolgen identisch sind. Gibt einen booleschen Wert zurück.|  
|<xref:System.String.IndexOf%2A?displayProperty=nameWithType>|Gibt ausgehend vom Anfang der zu überprüfenden Zeichenfolge die Indexposition eines Zeichens oder einer Zeichenfolge zurück. Gibt einen Ganzzahlwert zurück.|  
|<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>|Gibt ausgehend vom Ende der zu überprüfenden Zeichenfolge die Indexposition eines Zeichens oder einer Zeichenfolge zurück. Gibt einen Ganzzahlwert zurück.|  
  
## <a name="compare"></a>Vergleichen  
 Die statische <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode bietet umfassende Möglichkeiten zum Vergleichen von zwei Zeichenfolgen. Bei dieser Methode werden unterschiedliche Kulturen berücksichtigt. Sie können diese Funktion verwenden, um zwei Zeichenfolgen oder zwei untergeordnete Zeichenfolgen zweier Zeichenfolgen miteinander zu vergleichen. Zusätzlich sind Überladungen verfügbar, mit denen die Groß-/Kleinschreibung sowie abweichende Kulturen berücksichtigt bzw. ignoriert werden können. In der folgenden Tabelle sind die drei ganzzahligen Werte aufgeführt, die von dieser Methode zurückgegeben werden können.  
  
|Rückgabewert|Bedingung|  
|------------------|---------------|  
|Eine negative ganze Zahl|Die erste Zeichenfolge steht in der Sortierreihenfolge vor der zweiten Zeichenfolge.<br /><br /> - oder -<br /><br /> Die erste Zeichenfolge ist `null`.|  
|0|Die erste Zeichenfolge und die zweite Zeichenfolge sind gleich.<br /><br /> - oder -<br /><br /> Beide Zeichenfolgen sind `null`.|  
|Eine positive ganze Zahl<br /><br /> - oder -<br /><br /> 1|Die erste Zeichenfolge steht in der Sortierreihenfolge hinter der zweiten Zeichenfolge.<br /><br /> - oder -<br /><br /> Die zweite Zeichenfolge ist `null`.|  
  
> [!IMPORTANT]
> Die <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode ist hauptsächlich für die Anordnung oder Sortierung von Zeichenfolgen bestimmt. Sie sollten die <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode nicht verwenden, um einen Übereinstimmungstest auszuführen (also um explizit nach dem Rückgabewert 0 zu suchen, ohne dass dabei berücksichtigt wird, ob eine Zeichenfolge kleiner oder größer als die andere ist). Um festzustellen, ob zwei Zeichenfolgen gleich sind, verwenden Sie stattdessen die <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> -Methode.  
  
 Im folgenden Beispiel wird die <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode verwendet, um die relativen Werte von zwei Zeichenfolgen zu bestimmen.  
  
 [!code-cpp[Conceptual.String.BasicOps#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#6)]
 [!code-csharp[Conceptual.String.BasicOps#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#6)]
 [!code-vb[Conceptual.String.BasicOps#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#6)]  
  
 In diesem Beispiel wird `-1` auf der Konsole angezeigt.  
  
 Das vorhergehende Beispiel ist in der Standardeinstellung kulturabhängig. Zum Durchführen eines kulturunabhängigen Zeichenfolgenvergleichs verwenden Sie eine Überladung der <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode, bei der Sie die zu verwendende Kultur festlegen können, indem Sie einen *culture* -Parameter angeben. Ein Beispiel für die Verwendung der <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode zur Durchführung eines kulturunabhängigen Vergleichs finden Sie unter [Durchführen kulturunabhängiger Zeichenfolgenvergleiche](../globalization-localization/performing-culture-insensitive-string-comparisons.md).  
  
## <a name="compareordinal"></a>CompareOrdinal  
 Mit der <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> -Methode werden zwei Zeichenfolgenobjekte ohne Berücksichtigung der lokalen Kultur verglichen. Die Rückgabewerte dieser Methode stimmen mit den Werten überein, die von der in der vorherigen Tabelle beschriebenen **Compare** -Methode zurückgegeben werden.  
  
> [!IMPORTANT]
> Die <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> -Methode ist hauptsächlich für die Anordnung oder Sortierung von Zeichenfolgen bestimmt. Sie sollten die <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> -Methode nicht verwenden, um einen Übereinstimmungstest auszuführen (also um explizit nach dem Rückgabewert 0 zu suchen, ohne dass dabei berücksichtigt wird, ob eine Zeichenfolge kleiner oder größer als die andere ist). Um festzustellen, ob zwei Zeichenfolgen gleich sind, verwenden Sie stattdessen die <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> -Methode.  
  
 Im folgenden Beispiel wird die **CompareOrdinal** -Methode verwendet, um die Werte von zwei Zeichenfolgen zu vergleichen.  
  
 [!code-cpp[Conceptual.String.BasicOps#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#7)]
 [!code-csharp[Conceptual.String.BasicOps#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#7)]
 [!code-vb[Conceptual.String.BasicOps#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#7)]  
  
 In diesem Beispiel wird `-32` auf der Konsole angezeigt.  
  
## <a name="compareto"></a>CompareTo  
 Mit der <xref:System.String.CompareTo%2A?displayProperty=nameWithType> -Methode wird die im aktuellen Zeichenfolgenobjekt gekapselte Zeichenfolge mit einer anderen Zeichenfolge oder einem anderen Objekt verglichen. Die Rückgabewerte dieser Methode stimmen mit den Werten überein, die von der in der vorherigen Tabelle beschriebenen <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode zurückgegeben werden.  
  
> [!IMPORTANT]
> Die <xref:System.String.CompareTo%2A?displayProperty=nameWithType> -Methode ist hauptsächlich für die Anordnung oder Sortierung von Zeichenfolgen bestimmt. Sie sollten die <xref:System.String.CompareTo%2A?displayProperty=nameWithType> -Methode nicht verwenden, um einen Übereinstimmungstest auszuführen (also um explizit nach dem Rückgabewert 0 zu suchen, ohne dass dabei berücksichtigt wird, ob eine Zeichenfolge kleiner oder größer als die andere ist). Um festzustellen, ob zwei Zeichenfolgen gleich sind, verwenden Sie stattdessen die <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> -Methode.  
  
 Im folgenden Beispiel wird die <xref:System.String.CompareTo%2A?displayProperty=nameWithType> -Methode verwendet, um das `string1` -Objekt mit dem `string2` -Objekt zu vergleichen.  
  
 [!code-cpp[Conceptual.String.BasicOps#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#8)]
 [!code-csharp[Conceptual.String.BasicOps#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#8)]
 [!code-vb[Conceptual.String.BasicOps#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#8)]  
  
 In diesem Beispiel wird `-1` auf der Konsole angezeigt.  
  
 Alle Überladungen der <xref:System.String.CompareTo%2A?displayProperty=nameWithType> -Methode führen in der Standardeinstellung kulturabhängige Vergleiche durch, bei denen die Groß- und Kleinschreibung berücksichtigt wird. Es werden keine Überladungen dieser Methode bereitgestellt, mit denen Sie einen kulturunabhängigen Vergleich durchführen können. Aus Gründen der Übersichtlichkeit des Codes wird empfohlen, stattdessen die **String.Compare** -Methode zu verwenden und für kulturabhängige Operationen <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> sowie für kulturunabhängige Operationen <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> festzulegen. Beispiele für die Verwendung der **String.Compare** -Methode zur Durchführung von kulturabhängigen und kulturunabhängigen Vergleichen finden Sie unter [Durchführen kulturunabhängiger Zeichenfolgenvergleiche](../globalization-localization/performing-culture-insensitive-string-comparisons.md).  
  
## <a name="equals"></a>gleich  
 Mit der **String.Equals** -Methode lässt sich auf einfache Weise feststellen, ob zwei Zeichenfolgen identisch sind. Diese Methode, bei der die Groß-/Kleinschreibung beachtet wird, gibt den booleschen Wert **true** oder **false** zurück. Wie das nächste Beispiel zeigt, kann die Methode einer bestehenden Klasse verwendet werden. Im folgenden Beispiel wird mithilfe der **Equals** -Methode festgestellt, ob ein Zeichenfolgenobjekt den Ausdruck "Hello World" enthält.  
  
 [!code-cpp[Conceptual.String.BasicOps#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#9)]
 [!code-csharp[Conceptual.String.BasicOps#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#9)]
 [!code-vb[Conceptual.String.BasicOps#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#9)]  
  
 In diesem Beispiel wird `True` auf der Konsole angezeigt.  
  
 Diese Methode kann auch als statische Methode verwendet werden. Im folgenden Beispiel werden zwei Zeichenfolgenobjekte mithilfe einer statischen Methode verglichen.  
  
 [!code-cpp[Conceptual.String.BasicOps#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#10)]
 [!code-csharp[Conceptual.String.BasicOps#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#10)]
 [!code-vb[Conceptual.String.BasicOps#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#10)]  
  
 In diesem Beispiel wird `True` auf der Konsole angezeigt.  
  
## <a name="startswith-and-endswith"></a>"StartsWith" und "EndsWith"  
 Mit der **String.StartsWith** -Methode können Sie feststellen, ob ein Zeichenfolgenobjekt mit denselben Zeichen beginnt, die eine andere Zeichenfolge enthält. Diese Methode, bei der die Groß-/Kleinschreibung beachtet wird, gibt **true** zurück, wenn das aktuelle Zeichenfolgenobjekt mit der übergebenen Zeichenfolge beginnt, und sie gibt **false** zurück, wenn dies nicht der Fall ist. Im folgenden Beispiel wird mithilfe dieser Methode festgestellt, ob ein Zeichenfolgenobjekt mit "Hello" beginnt.  
  
 [!code-cpp[Conceptual.String.BasicOps#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#11)]
 [!code-csharp[Conceptual.String.BasicOps#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#11)]
 [!code-vb[Conceptual.String.BasicOps#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#11)]  
  
 In diesem Beispiel wird `True` auf der Konsole angezeigt.  
  
 Bei der **String.EndsWith** -Methode wird eine übergebene Zeichenfolge mit den Zeichen am Ende des aktuellen Zeichenfolgenobjekts verglichen. Auch sie gibt einen booleschen Wert zurück. Im folgenden Beispiel wird das Ende einer Zeichenfolge mithilfe der **EndsWith** -Methode überprüft.  
  
 [!code-cpp[Conceptual.String.BasicOps#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#12)]
 [!code-csharp[Conceptual.String.BasicOps#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#12)]
 [!code-vb[Conceptual.String.BasicOps#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#12)]  
  
 In diesem Beispiel wird `False` auf der Konsole angezeigt.  
  
## <a name="indexof-and-lastindexof"></a>"IndexOf" und "LastIndexOf"  
 Mit der **String.IndexOf** -Methode können Sie die Position feststellen, an der ein bestimmtes Zeichen in einer Zeichenfolge erstmalig vorkommt. Bei dieser Methode, die die Groß-/Kleinschreibung beachtet, beginnt die Zählung am Anfang einer Zeichenfolge; sie gibt die Position eines übergebenen Zeichens auf der Grundlage eines nullbasierten Indizes zurück. Wenn das Zeichen nicht gefunden wird, wird der Wert –1 zurückgegeben.  
  
 Im folgenden Beispiel wird die **IndexOf** -Methode verwendet, um in einer Zeichenfolge nach dem ersten Vorkommnis des Zeichens '`l`' zu suchen.  
  
 [!code-cpp[Conceptual.String.BasicOps#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#13)]
 [!code-csharp[Conceptual.String.BasicOps#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#13)]
 [!code-vb[Conceptual.String.BasicOps#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#13)]  
  
 In diesem Beispiel wird `2` auf der Konsole angezeigt.  
  
 Die **String.LastIndexOf** -Methode ist vergleichbar mit der **String.IndexOf** -Methode, außer dass sie die Position zurückgibt, an der ein bestimmtes Zeichen innerhalb einer Zeichenfolge letztmalig vorkommt. Sie beachtet die Groß-/Kleinschreibung und verwendet einen nullbasierten Index.  
  
 Im folgenden Beispiel wird die **LastIndexOf** -Methode verwendet, um in einer Zeichenfolge nach dem letzten Vorkommnis des Zeichens '`l`' zu suchen.  
  
 [!code-cpp[Conceptual.String.BasicOps#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#14)]
 [!code-csharp[Conceptual.String.BasicOps#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#14)]
 [!code-vb[Conceptual.String.BasicOps#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#14)]  
  
 In diesem Beispiel wird `9` auf der Konsole angezeigt.  
  
 Beide Methoden sind hilfreich, wenn sie in Verbindung mit der **String.Remove** -Methode verwendet werden. Sie können die **IndexOf** -Methode oder die **LastIndexOf** -Methode verwenden, um die Position eines Zeichens abzurufen, und diese Position dann an die **Remove** -Methode übergeben, um ein Zeichen oder ein Wort zu entfernen, das mit diesem Zeichen beginnt.  
  
## <a name="see-also"></a>Siehe auch

- [Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)
- [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../globalization-localization/performing-culture-insensitive-string-operations.md)
- [Sortiergewichtungstabellen (für .NET unter Windows)](https://www.microsoft.com/download/details.aspx?id=10921)
- [Default Unicode Collation Element Table (für .NET Core unter Linux und macOS)](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
