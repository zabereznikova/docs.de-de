---
title: Durchführen kulturunabhängiger Zeichenfolgenvergleiche
ms.date: 08/22/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.CompareTo method
- String.Compare method
- string comparison [.NET], culture-insensitive
- strings [.NET], comparing
- culture-insensitive string operations, comparisons
- culture parameter
ms.assetid: abae50ef-32f7-4a50-a540-fd256fd1aed0
ms.openlocfilehash: 3f933121d3c878dd8eee4812fa6669a915c22356
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696491"
---
# <a name="performing-culture-insensitive-string-comparisons"></a>Durchführen kulturunabhängiger Zeichenfolgenvergleiche

In der Standardeinstellung führt die <xref:System.String.Compare%2A?displayProperty=nameWithType>-Methode kulturabhängige Vergleiche sowie Vergleiche unter Berücksichtigung der Groß-/Kleinschreibung aus. Diese Methode schließt auch mehrere Überladungen ein, die einen `culture`-Parameter zur Angabe der zu verwendenden Kultur und einen `comparisonType`-Parameter zur Angabe der zu verwendenden Vergleichsregeln bereitstellen. Durch den Aufruf dieser Methoden statt der Standardüberladung wird jede Mehrdeutigkeit hinsichtlich der in einem bestimmten Methodenaufruf verwendeten Regeln vermieden. Es wird verdeutlicht, ob ein bestimmter Vergleich kulturabhängig oder kulturunabhängig ist.  
  
> [!NOTE]
> Beide Überladungen der <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Methode führen kulturabhängige Vergleiche durch, bei denen die Groß- und Kleinschreibung berücksichtigt wird. Sie können kulturunabhängige Vergleiche nicht mithilfe dieser Methode ausführen. Aus Gründen der Übersichtlichkeit des Codes wird empfohlen, stattdessen die <xref:System.String.Compare%2A?displayProperty=nameWithType>-Methode zu verwenden.  
  
 Geben Sie für kulturabhängige Vorgänge den <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>-Enumerationswert oder den <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType>-Enumerationswert als `comparisonType`-Parameter an. Wenn Sie einen kulturabhängigen Vergleich mithilfe einer anderen festgelegten Kultur als der aktuellen Kultur ausführen möchten, geben Sie das <xref:System.Globalization.CultureInfo>-Objekt an, das diese Kultur als `culture`-Parameter darstellt.  
  
 Die kulturunabhängigen von der <xref:System.String.Compare%2A?displayProperty=nameWithType>-Methode unterstützten Zeichenfolgenvergleiche sind entweder linguistisch (auf Grundlage der Sortierkonventionen der invarianten Kultur) oder nicht linguistisch (auf Grundlage des Ordnungswerts der Zeichen in der Zeichenfolge). Die meisten kulturunabhängigen Zeichenfolgenvergleiche sind nicht linguistisch. Geben Sie den <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>-Enumerationswert oder den <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType>-Enumerationswert als `comparisonType`-Parameter für diese Vergleiche an. Wenn beispielsweise eine Sicherheitsentscheidung (z. B. ein Benutzername oder ein Kennwortvergleich) auf dem Ergebnis eines Zeichenfolgenvergleichs basiert, sollte der Vorgang kulturunabhängig und nicht linguistisch sein, um sicherzustellen, dass das Ergebnis nicht von den Konventionen einer bestimmten Kultur oder Sprache beeinflusst wird.  
  
 Verwenden Sie einen kulturunabhängigen linguistischen Zeichenfolgenvergleich, wenn Sie linguistisch relevante Zeichenfolgen mehrerer Kulturen auf eine konsistente Weise behandeln möchten. Wenn die Anwendung z. B. Wörter anzeigt, die mehrere Zeichensätze in einem Listenfeld verwenden, können Sie Wörter in der gleichen Reihenfolge unabhängig von der aktuellen Kultur anzeigen. Für kulturunabhängige linguistische Vergleiche definiert .NET eine invariante Kultur, die auf den linguistischen Konventionen der englischen Sprache basiert. Geben Sie <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> oder <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> als `comparisonType`-Parameter an, um einen kulturunabhängigen linguistischen Vergleich auszuführen.  
  
 Im folgenden Beispiel werden zwei kulturunabhängige, nicht linguistische Zeichenfolgenvergleiche ausgeführt. Beim ersten Beispiel wird die Groß-/Kleinschreibung beachtet, beim zweiten nicht.  
  
 [!code-csharp[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/cs/cultureinsensitive1.cs#1)]
 [!code-vb[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/vb/cultureinsensitive1.vb#1)]  

Sie können die aus mehreren Textdateien bestehenden [Sorting Weight Tables](https://www.microsoft.com/download/details.aspx?id=10921) herunterladen. Diese Textdateien enthalten Informationen zur Gewichtung der Zeichen, die bei Sortier- und Vergleichsvorgängen unter Windows-Betriebssystemen verwendet werden, sowie die [Default Unicode Collation Element Table](https://www.unicode.org/Public/UCA/latest/allkeys.txt), die Sortiergewichtungstabelle für Linux und macOS.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.String.Compare%2A?displayProperty=nameWithType>
- <xref:System.String.CompareTo%2A?displayProperty=nameWithType>
- [Durchführen kulturunabhängiger Zeichenfolgenoperationen](performing-culture-insensitive-string-operations.md)
- [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](../base-types/best-practices-strings.md)
