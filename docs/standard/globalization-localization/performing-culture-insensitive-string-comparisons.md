---
title: "Durchf&#252;hren kulturunabh&#228;ngiger Zeichenfolgenvergleiche | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "culture-Parameter"
  - "Kulturunabhängige Zeichenfolgenoperationen, Vergleiche"
  - "Vergleich von Zeichenfolgen [.NET Framework], Kulturunabhängig"
  - "String.Compare-Methode"
  - "String.CompareTo-Methode"
  - "Zeichenfolgen [.NET Framework], Vergleichen"
ms.assetid: abae50ef-32f7-4a50-a540-fd256fd1aed0
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Durchf&#252;hren kulturunabh&#228;ngiger Zeichenfolgenvergleiche
In der Standardeinstellung führt die <xref:System.String.Compare%2A?displayProperty=fullName>\-Methode kulturabhängige Vergleiche sowie Vergleiche unter Berücksichtigung der Groß\-\/Kleinschreibung aus.  Diese Methode schließt auch mehrere Überladungen ein, die einen `culture`\-Parameter zur Angabe der zu verwendenden Kultur und einen `comparisonType`\-Parameter zur Angabe der zu verwendenden Vergleichsregeln bereitstellen.  Durch den Aufruf dieser Methoden statt der Standardüberladung wird jede Mehrdeutigkeit hinsichtlich der in einem bestimmten Methodenaufruf verwendeten Regeln vermieden. Es wird verdeutlicht, ob ein bestimmter Vergleich kulturabhängig oder kulturunabhängig ist.  
  
> [!NOTE]
>  Beide Überladungen der <xref:System.String.CompareTo%2A?displayProperty=fullName>\-Methode führen kulturabhängige Vergleiche durch, bei denen die Groß\- und Kleinschreibung berücksichtigt wird. Sie können kulturunabhängige Vergleiche nicht mithilfe dieser Methode ausführen.  Aus Gründen der Übersichtlichkeit des Codes wird empfohlen, stattdessen die <xref:System.String.Compare%2A?displayProperty=fullName>\-Methode zu verwenden.  
  
 Geben Sie für kulturabhängige Vorgänge den <xref:System.StringComparison?displayProperty=fullName>\-Enumerationswert oder den <xref:System.StringComparison?displayProperty=fullName>\-Enumerationswert als `comparisonType`\-Parameter an.  Wenn Sie einen kulturabhängigen Vergleich mithilfe einer anderen festgelegte Kultur als der aktuellen Kultur ausführen möchten, geben Sie das <xref:System.Globalization.CultureInfo>\-Objekt an, das diese Kultur als `culture` \-Parameter darstellt.  
  
 Die kulturunabhängigen von der <xref:System.String.Compare%2A?displayProperty=fullName>\-Methode unterstützten Zeichenfolgenvergleiche sind entweder linguistisch \(auf Grundlage der Sortierkonventionen der invarianten Kultur\) oder nicht linguistisch \(auf Grundlage des Ordnungswerts der Zeichen in der Zeichenfolge\).  Die meisten kulturunabhängigen Zeichenfolgenvergleiche sind nicht linguistisch.  Geben Sie den <xref:System.StringComparison?displayProperty=fullName>\-Enumerationswert oder den <xref:System.StringComparison?displayProperty=fullName>\-Enumerationswert als `comparisonType`\-Parameter für diese Vergleiche an.  Wenn beispielsweise eine Sicherheitsentscheidung \(z. B. ein Benutzername oder ein Kennwortvergleich\) auf dem Ergebnis eines Zeichenfolgenvergleichs basiert, sollte der Vorgang kulturunabhängig und nicht linguistisch sein, um sicherzustellen, dass das Ergebnis nicht von den Konventionen einer bestimmten Kultur oder Sprache beeinflusst wird.  
  
 Verwenden Sie einen kulturunabhängigen linguistischen Zeichenfolgenvergleich, wenn Sie linguistisch relevante Zeichenfolgen mehrerer Kulturen auf eine konsistente Weise behandeln möchten.  Wenn die Anwendung z. B. Wörter anzeigt, die mehrere Zeichensätze in einem Listenfeld verwenden, können Sie Wörter in der gleichen Reihenfolge unabhängig von der aktuellen Kultur anzeigen.  Für kulturunabhängige linguistische Vergleiche definiert .NET Framework eine invariante Kultur, die auf den linguistischen Konventionen der englischen Sprache basiert.  Geben Sie <xref:System.StringComparison?displayProperty=fullName> oder <xref:System.StringComparison?displayProperty=fullName> als `comparisonType`\-Parameter an, um einen kulturunabhängigen linguistischen Vergleich auszuführen.  
  
 Im folgenden Beispiel werden zwei kulturunabhängige, nicht linguistische Zeichenfolgenvergleiche ausgeführt.  Beim ersten Beispiel wird die Groß\-\/Kleinschreibung beachtet, beim zweiten nicht.  
  
 [!code-csharp[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/cs/cultureinsensitive1.cs#1)]
 [!code-vb[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/vb/cultureinsensitive1.vb#1)]  
  
## Siehe auch  
 <xref:System.String.Compare%2A?displayProperty=fullName>   
 <xref:System.String.CompareTo%2A?displayProperty=fullName>   
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)   
 [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](../../../docs/standard/base-types/best-practices-strings.md)