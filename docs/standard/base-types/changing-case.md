---
title: Ändern der Groß-/Kleinschreibung in .NET
description: Erfahren Sie, wie Sie die Groß-/Kleinschreibung in Zeichenfolgen in .NET ändern können.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework], case
- case sensitivity
- ToUpper method
- ToLower method
- uppercase
- lowercase
ms.assetid: 6805f81b-e9ad-4387-9f4c-b9bdb21b87c0
ms.openlocfilehash: 135cfa815c10d1a9dd9056604a4601678da9d5c4
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159350"
---
# <a name="changing-case-in-net"></a>Ändern der Groß-/Kleinschreibung in .NET
Wenn Sie eine Anwendung schreiben, die Benutzereingaben akzeptiert, können Sie nicht sicher sein, ob die Daten in Groß- oder Kleinschreibung eingegeben werden. Häufig möchten Sie, dass Zeichenfolgen in einheitlicher Schreibung vorliegen, insbesondere, wenn sie in der Benutzeroberfläche angezeigt werden. In der folgenden Tabelle sind drei Methoden zur Änderung der Groß-/Kleinschreibung beschrieben. Die ersten beiden Methoden stellen eine Überladung bereit, die eine Kultur akzeptiert.  
  
|Methodenname|Verwendung|  
|-----------------|---------|  
|<xref:System.String.ToUpper%2A?displayProperty=nameWithType>|Konvertiert alle Zeichen in einer Zeichenfolge in Großbuchstaben.|  
|<xref:System.String.ToLower%2A?displayProperty=nameWithType>|Konvertiert alle Zeichen in einer Zeichenfolge in Kleinbuchstaben.|  
|<xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType>|Konvertiert eine Zeichenfolge in Titelschreibung.|  
  
> [!WARNING]
> Beachten Sie, dass die <xref:System.String.ToUpper%2A?displayProperty=nameWithType>- und die <xref:System.String.ToLower%2A?displayProperty=nameWithType>-Methode nicht dazu verwendet werden sollten, Zeichenfolgen zu konvertieren, um diese zu vergleichen oder auf Gleichheit zu testen. Weitere Informationen finden Sie im Abschnitt [Vergleichen von Zeichenfolgen in gemischter Schreibung](#Comparing).  
  
<a name="Comparing"></a>
## <a name="comparing-strings-of-mixed-case"></a>Vergleichen von Zeichenfolgen in gemischter Schreibung  
 Wenn Sie Zeichenfolgen in gemischter Schreibung vergleichen möchten, um deren Reihenfolge zu ermitteln, rufen Sie eine der Überladungen der <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Methode mit einem `comparisonType`-Parameter auf, und geben Sie entweder <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> oder <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> oder <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> als Wert für das `comparisonType`-Argument an. Soll für einen Vergleich eine bestimmte Kultur verwendet werden, die nicht die aktuelle Kultur ist, rufen Sie eine Überladung der <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Methode mit einem `culture`- und einem `options`-Parameter auf, und geben Sie <xref:System.Globalization.CompareOptions.IgnoreCase?displayProperty=nameWithType> als Wert für das `options`-Argument an.  
  
 Wenn Sie Zeichenfolgen in gemischter Schreibung vergleichen möchten, um zu ermitteln, ob sie gleich sind, rufen Sie eine der Überladungen der <xref:System.String.Equals%2A?displayProperty=nameWithType>-Methode mit einem `comparisonType`-Parameter auf, und geben Sie entweder <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> oder <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> oder <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> als Wert für das `comparisonType`-Argument an.  
  
 Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen in .NET Framework](../../../docs/standard/base-types/best-practices-strings.md).  
  
## <a name="toupper"></a>ToUpper  
 Die <xref:System.String.ToUpper%2A?displayProperty=nameWithType>-Methode ändert alle Zeichen in einer Zeichenfolge in Großbuchstaben. Im folgenden Beispiel wird die Zeichenfolge „Hello World!“ von gemischter Schreibung in Großbuchstaben konvertiert.  
  
 [!code-csharp[Strings.ChangingCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#1)]
 [!code-vb[Strings.ChangingCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#1)]  
  
 Das vorhergehende Beispiel ist standardmäßig kulturabhängig, d. h., in ihm werden hinsichtlich Groß- und Kleinschreibung die Konventionen der aktuellen Kultur verwendet. Wenn Sie eine kulturunabhängige Änderung der Groß-/Kleinschreibung ausführen oder die Schreibungskonventionen einer bestimmten Kultur anwenden möchten, verwenden Sie die <xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>-Methodenüberladung, und geben Sie den Wert <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> oder ein <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>-Objekt, das der angegebenen Kultur entspricht, für den *culture*-Parameter an. Ein Beispiel, in dem gezeigt wird, wie die <xref:System.String.ToUpper%2A>-Methode verwendet wird, um eine kulturunabhängige Änderung der Groß-/Kleinschreibung auszuführen, finden Sie unter [Durchführen kulturunabhängiger Schreibungsänderungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## <a name="tolower"></a>ToLower  
 Die <xref:System.String.ToLower%2A?displayProperty=nameWithType>-Methode entspricht der vorherigen Methode mit dem Unterschied, dass sie alle Zeichen in einer Zeichenfolge in Kleinbuchstaben konvertiert. Im folgenden Beispiel wird die Zeichenfolge „Hello World!“ in Kleinbuchstaben konvertiert.  
  
 [!code-csharp[Strings.ChangingCase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#2)]
 [!code-vb[Strings.ChangingCase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#2)]  
  
 Das vorhergehende Beispiel ist standardmäßig kulturabhängig, d. h., in ihm werden hinsichtlich Groß- und Kleinschreibung die Konventionen der aktuellen Kultur verwendet. Wenn Sie eine kulturunabhängige Änderung der Groß-/Kleinschreibung ausführen oder die Schreibungskonventionen einer bestimmten Kultur anwenden möchten, verwenden Sie die <xref:System.String.ToLower%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>-Methodenüberladung, und geben Sie den Wert <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> oder ein <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>-Objekt, das der angegebenen Kultur entspricht, für den *culture*-Parameter an. Ein Beispiel, in dem gezeigt wird, wie die <xref:System.String.ToLower%28System.Globalization.CultureInfo%29>-Methode verwendet wird, um eine kulturunabhängige Änderung der Groß-/Kleinschreibung auszuführen, finden Sie unter [Durchführen kulturunabhängiger Schreibungsänderungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## <a name="totitlecase"></a>ToTitleCase  
 Die <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType>-Methode konvertiert das erste Zeichen jedes Worts in einen Großbuchstaben und die übrigen Zeichen in Kleinbuchstaben. Wörter, die vollständig in Großbuchstaben vorliegen, werden als Akronyme angesehen und nicht konvertiert.  
  
 Die <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType>-Methode ist kulturabhängig, d. h., sie verwendet die Schreibungskonventionen einer bestimmten Kultur. Um die Methode aufzurufen, rufen Sie zuerst das <xref:System.Globalization.TextInfo>-Objekt, das die Schreibungskonventionen der bestimmten Kultur angibt, aus der <xref:System.Globalization.CultureInfo.TextInfo%2A?displayProperty=nameWithType>-Eigenschaft dieser Kultur ab.  
  
 Im folgenden Beispiel wird jede Zeichenfolge in einem Array an die <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType>-Methode übergeben.  Die Zeichenfolgen enthalten sowohl Titelzeichenfolgen als auch Akronyme. Die Zeichenfolgen werden in Titelschreibung konvertiert, indem die Schreibungskonventionen der Kultur Englisch (USA) verwendet werden.  
  
 [!code-csharp[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/cs/totitlecase2.cs#1)]
 [!code-vb[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/vb/totitlecase2.vb#1)]  
  
 Beachten Sie, dass die <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType>-Methode, obwohl sie kulturabhängig ist, keine linguistisch korrekten Regeln für Groß-/Kleinschreibung bereitstellt. Beispielsweise konvertiert die Methode die Zeichenfolge "a tale of two cities" im vorherigen Beispiel in "A Tale Of Two Cities". Die linguistisch korrekte Schreibung für die Kultur "en-US" ist aber "A Tale of Two Cities".  
  
## <a name="see-also"></a>Siehe auch

- [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)
- [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
