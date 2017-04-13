---
title: "&#196;ndern der Gro&#223;-/Kleinschreibung in .NET Framework | Microsoft Docs"
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
  - "Berücksichtigung der Groß-/Kleinschreibung"
  - "Kleinbuchstaben"
  - "Zeichenfolgen [.NET Framework], Groß- und Kleinschreibung"
  - "ToLower-Methode"
  - "ToUpper-Methode"
  - "Großbuchstaben"
ms.assetid: 6805f81b-e9ad-4387-9f4c-b9bdb21b87c0
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# &#196;ndern der Gro&#223;-/Kleinschreibung in .NET Framework
Wenn Sie eine Anwendung schreiben, die Benutzereingaben akzeptiert, können Sie nicht sicher sein, ob die Daten in Groß\- oder Kleinschreibung eingegeben werden.  Häufig möchten Sie, dass Zeichenfolgen in einheitlicher Schreibung vorliegen, insbesondere, wenn sie in der Benutzeroberfläche angezeigt werden.  In der folgenden Tabelle sind drei Methoden zur Änderung der Groß\-\/Kleinschreibung beschrieben.  Die ersten beiden Methoden stellen eine Überladung bereit, die eine Kultur akzeptiert.  
  
|Methodenname|Verwendung|  
|------------------|----------------|  
|<xref:System.String.ToUpper%2A?displayProperty=fullName>|Konvertiert alle Zeichen in einer Zeichenfolge in Großbuchstaben.|  
|<xref:System.String.ToLower%2A?displayProperty=fullName>|Konvertiert alle Zeichen in einer Zeichenfolge in Kleinbuchstaben.|  
|<xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName>|Konvertiert eine Zeichenfolge in Titelschreibung.|  
  
> [!WARNING]
>  Beachten Sie, dass die <xref:System.String.ToUpper%2A?displayProperty=fullName>\- und die <xref:System.String.ToLower%2A?displayProperty=fullName>\-Methode nicht dazu verwendet werden sollten, Zeichenfolgen zu konvertieren, um diese zu vergleichen oder auf Gleichheit zu testen.  Weitere Informationen finden Sie im Abschnitt [Vergleichen von Zeichenfolgen in gemischter Schreibung](#Comparing).  
  
<a name="Comparing"></a>   
## Vergleichen von Zeichenfolgen in gemischter Schreibung  
 Wenn Sie Zeichenfolgen in gemischter Schreibung vergleichen möchten, um deren Reihenfolge zu ermitteln, rufen Sie eine der Überladungen der <xref:System.String.CompareTo%2A?displayProperty=fullName>\-Methode mit einem `comparisonType`\-Parameter auf, und geben Sie entweder <xref:System.StringComparison?displayProperty=fullName> oder <xref:System.StringComparison?displayProperty=fullName> oder <xref:System.StringComparison?displayProperty=fullName> als Wert für das `comparisonType`\-Argument an.  Soll für einen Vergleich eine bestimmte Kultur verwendet werden, die nicht die aktuelle Kultur ist, rufen Sie eine Überladung der <xref:System.String.CompareTo%2A?displayProperty=fullName>\-Methode mit einem `culture`\- und einem `options`\-Parameter auf, und geben Sie <xref:System.Globalization.CompareOptions?displayProperty=fullName> als Wert für das `options`\-Argument an.  
  
 Wenn Sie Zeichenfolgen in gemischter Schreibung vergleichen möchten, um zu ermitteln, ob sie gleich sind, rufen Sie eine der Überladungen der <xref:System.String.Equals%2A?displayProperty=fullName>\-Methode mit einem `comparisonType`\-Parameter auf, und geben Sie entweder <xref:System.StringComparison?displayProperty=fullName> oder <xref:System.StringComparison?displayProperty=fullName> oder <xref:System.StringComparison?displayProperty=fullName> als Wert für das `comparisonType`\-Argument an.  
  
 Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](../../../docs/standard/base-types/best-practices-strings.md).  
  
## ToUpper  
 Die <xref:System.String.ToUpper%2A?displayProperty=fullName>\-Methode ändert alle Zeichen in einer Zeichenfolge in Großbuchstaben.  Im folgenden Beispiel wird die Zeichenfolge "Hello World\!" aus der gemischten Schreibung in Großbuchstaben konvertiert.  
  
 [!code-csharp[Strings.ChangingCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#1)]
 [!code-vb[Strings.ChangingCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#1)]  
  
 Das vorhergehende Beispiel ist standardmäßig kulturabhängig, d. h., in ihm werden hinsichtlich Groß\- und Kleinschreibung die Konventionen der aktuellen Kultur verwendet.  Wenn Sie eine kulturunabhängige Änderung der Groß\-\/Kleinschreibung ausführen oder die Schreibungskonventionen einer bestimmten Kultur anwenden möchten, verwenden Sie die <xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=fullName>\-Methodenüberladung, und geben Sie den Wert <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> oder ein <xref:System.Globalization.CultureInfo?displayProperty=fullName>\-Objekt, das der angegebenen Kultur entspricht, für den *culture*\-Parameter an.  Ein Beispiel, in dem gezeigt wird, wie die <xref:System.String.ToUpper%2A>\-Methode verwendet wird, um eine kulturunabhängige Änderung der Groß\-\/Kleinschreibung auszuführen, finden Sie unter [Durchführen kulturunabhängiger Schreibungsänderungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## ToLower  
 Die <xref:System.String.ToLower%2A?displayProperty=fullName>\-Methode entspricht der vorherigen Methode mit dem Unterschied, dass sie alle Zeichen in einer Zeichenfolge in Kleinbuchstaben konvertiert.  Im folgenden Beispiel wird die Zeichenfolge "Hello World\!" in Kleinbuchstaben konvertiert.  
  
 [!code-csharp[Strings.ChangingCase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#2)]
 [!code-vb[Strings.ChangingCase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#2)]  
  
 Das vorhergehende Beispiel ist standardmäßig kulturabhängig, d. h., in ihm werden hinsichtlich Groß\- und Kleinschreibung die Konventionen der aktuellen Kultur verwendet.  Wenn Sie eine kulturunabhängige Änderung der Groß\-\/Kleinschreibung ausführen oder die Schreibungskonventionen einer bestimmten Kultur anwenden möchten, verwenden Sie die <xref:System.String.ToLower%28System.Globalization.CultureInfo%29?displayProperty=fullName>\-Methodenüberladung, und geben Sie den Wert <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> oder ein <xref:System.Globalization.CultureInfo?displayProperty=fullName>\-Objekt, das der angegebenen Kultur entspricht, für den *culture*\-Parameter an.  Ein Beispiel, in dem gezeigt wird, wie die <xref:System.String.ToLower%28System.Globalization.CultureInfo%29>\-Methode verwendet wird, um eine kulturunabhängige Änderung der Groß\-\/Kleinschreibung auszuführen, finden Sie unter [Durchführen kulturunabhängiger Schreibungsänderungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## ToTitleCase  
 Die <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName>\-Methode konvertiert das erste Zeichen jedes Worts in einen Großbuchstaben und die übrigen Zeichen in Kleinbuchstaben.  Wörter, die vollständig in Großbuchstaben vorliegen, werden als Akronyme angesehen und nicht konvertiert.  
  
 Die <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName>\-Methode ist kulturabhängig, d. h., sie verwendet die Schreibungskonventionen einer bestimmten Kultur.  Um die Methode aufzurufen, rufen Sie zuerst das <xref:System.Globalization.TextInfo>\-Objekt, das die Schreibungskonventionen der bestimmten Kultur angibt, aus der <xref:System.Globalization.CultureInfo.TextInfo%2A?displayProperty=fullName>\-Eigenschaft dieser Kultur ab.  
  
 Im folgenden Beispiel wird jede Zeichenfolge in einem Array an die <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName>\-Methode übergeben.  Die Zeichenfolgen enthalten sowohl Titelzeichenfolgen als auch Akronyme.  Die Zeichenfolgen werden in Titelschreibung konvertiert, indem die Schreibungskonventionen der Kultur Englisch \(USA\) verwendet werden.  
  
 [!code-csharp[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/cs/totitlecase2.cs#1)]
 [!code-vb[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/vb/totitlecase2.vb#1)]  
  
 Beachten Sie, dass die <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName>\-Methode, obwohl sie kulturabhängig ist, keine linguistisch korrekten Regeln für Groß\-\/Kleinschreibung bereitstellt.  Beispielsweise konvertiert die Methode die Zeichenfolge "a tale of two cities" im vorherigen Beispiel in "A Tale Of Two Cities".  Die linguistisch korrekte Schreibung für die Kultur "en\-US" ist aber "A Tale of Two Cities".  
  
## Siehe auch  
 [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)   
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)