---
title: "Durchführen kulturunabhängiger Schreibungsänderungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.ToLower method
- culture, case sensitivity
- Char.ToLower method
- case, changing in culture-insensitive strings
- Char.ToUpper method
- culture-insensitive string operations, case changes
- String.ToUpper method
- culture parameter
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c500b882c335572b8b458ba515b282e9f5362b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-case-changes"></a>Durchführen kulturunabhängiger Schreibungsänderungen
Die Methoden <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType> und <xref:System.Char.ToLower%2A?displayProperty=nameWithType> stellen Überladungen bereit, die keine Parameter akzeptieren. Standardmäßig führen diese Überladungen ohne Parameter die Schreibungsänderungen auf Basis des <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>-Werts durch. Die unter Berücksichtigung der Groß-/Kleinschreibung erzielten Ergebnisse variieren je nach Kultur. Um klar anzugeben, ob die Schreibungsänderungen kulturabhängig oder kulturunabhängig erfolgen sollen, empfiehlt sich die Verwendung der Überladungen dieser Methoden, für die explizit ein `culture`-Parameter festgelegt werden muss. Um kulturabhängige Schreibungsänderungen zu aktivieren, geben Sie `CultureInfo.CurrentCulture` für den `culture`-Parameter an. Um kulturunabhängige Schreibungsänderungen zu aktivieren, geben Sie `CultureInfo.InvariantCulture` für den `culture`-Parameter an.  
  
 Häufig werden Zeichenfolgen in eine Standardschreibweise konvertiert, um spätere Suchvorgänge zu vereinfachen. Wenn Zeichenfolgen auf diese Weise verwendet werden, sollte `CultureInfo.InvariantCulture` für den `culture`-Parameter angegeben werden, da sich der Wert von <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> zwischen dem Zeitpunkt der Schreibungsänderung und dem Zeitpunkt des Suchvorgangs ändern kann.  
  
 Wenn darüber hinaus eine Sicherheitsentscheidung auf einer Änderung von Groß- und Kleinschreibung beruht, sollte die Operation kulturunabhängig sein, um sicherzustellen, dass das Ergebnis nicht durch den Wert von `CultureInfo.CurrentCulture` beeinflusst wird. Finden Sie im Abschnitt "Zeichenfolge vergleichen, verwenden die aktuelle Kultur" der [bewährte Methoden für die Verwendung von Zeichenfolgen](../../../docs/standard/base-types/best-practices-strings.md) Artikel für ein Beispiel, das veranschaulicht, wie kulturabhängige Zeichenfolgenoperationen stellen jedoch zu inkonsistenten Ergebnissen führen kann.  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a>Verwenden der String.ToUpper-Methode und der String.ToLower-Methode  
 Aus Gründen der Übersichtlichkeit des Codes wird empfohlen, immer die Überladungen der `String.ToUpper`-Methode und der `String.ToLower`-Methode zu verwenden, bei denen ein `culture`-Parameter explizit angegeben werden kann. Mit dem folgenden Code wird z. B. nach einem Bezeichner gesucht. In der Standardeinstellung ist die `key.ToLower`-Operation kulturabhängig, jedoch wird dieses Verhalten beim Lesen des Codes nicht deutlich.  
  
### <a name="example"></a>Beispiel  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 Wenn Sie eine kulturunabhängige `key.ToLower`-Operation ausführen möchten, muss das vorige Beispiel so geändert werden, dass beim Ändern der Schreibweise `CultureInfo.InvariantCulture` explizit verwendet wird:  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a>Verwenden der Char.ToUpper-Methode und der Char.ToLower-Methode  
 Obwohl die `Char.ToUpper` und `Char.ToLower` Methoden haben dieselben Merkmale wie die `String.ToUpper` und `String.ToLower` werden von Methoden, die betroffen sind nur die Kulturen Türkisch (Türkei) und Aserbaidschanisch (Lateinisch, Aserbaidschan). Hierbei handelt es sich um die beiden einzigen Kulturen mit Unterschieden in der Groß-/Kleinschreibung für ein einzelnes Zeichen. Weitere Informationen über diese Besonderheit bei der Groß-/Kleinschreibung finden Sie im Abschnitt "Groß-/Kleinschreibung" im Thema zur <xref:System.String>-Klasse. Aus Gründen der Übersichtlichkeit des Codes empfiehlt es sich, immer die Überladungen dieser Methoden zu verwenden, bei denen ein `culture`-Parameter explizit festgelegt werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.String.ToLower%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToLower%2A?displayProperty=nameWithType>  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
