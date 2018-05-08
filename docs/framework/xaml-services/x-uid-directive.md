---
title: x:Uid-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 667b722097d091902cb65f2e6f0485a039f8a2ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xuid-directive"></a>x:Uid-Anweisung
Stellt einen eindeutigen Bezeichner für Markupelemente bereit. In vielen Szenarien wird dieser eindeutige Bezeichner von XAML-Lokalisierungsprozesse und Tools verwendet.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`identifier`|Eine manuell erstellte oder automatisch generierte Zeichenfolge, die in einer Datei eindeutig sein sollte, wenn er vom interpretiert wird ein `x:Uid` Consumer.|  
  
## <a name="remarks"></a>Hinweise  
 In [MS-XAML] `x:Uid` wird als Direktive definiert. Weitere Informationen finden Sie unter [ \[MS-XAML-\] Abschnitt 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid` diskret aus `x:Name` sowohl aufgrund der angegebenen XAML-Lokalisierung Szenario, für die Lokalisierung verwendeten, Bezeichner auf programming Model Auswirkungen auf die keine Abhängigkeiten haben und `x:Name`. Darüber hinaus `x:Name` werden, unterliegt die Verwendung von XAML-Namensbereich; allerdings `x:Uid` unterliegt keine XAML-Sprache definiert Konzept der Eindeutigkeit erzwungen. XAML-Prozessoren im weitesten Sinne (Prozessoren, die nicht Teil des Lokalisierungsprozesses sind) werden nicht dazu gedacht, die die Eindeutigkeit der `x:Uid` Werte. Diese Aufgabe ist im Grunde auf dem Absender der Werte. Der Erwartungswert der Eindeutigkeit der `x:Uid` Werte innerhalb einer einzelnen XAML-Quelle ist sinnvoll für Consumer der Werte an, z. B. dedizierte Globalisierungsprozesse oder Tools. Das typische Eindeutigkeit-Modell ist, die `x:Uid` Werte sind eindeutig innerhalb einer XML-codierte Datei, die XAML darstellt.  
  
 Tools, mit denen wichtige Kenntnisse in einem bestimmten XAML-Schema können wahlweise für `x:Uid` nur für "true" lokalisierbare Zeichenfolgen, sondern für alle Fälle, in denen ein Textzeichenfolgenwert in Markup gefunden wird.  
  
 Frameworks können in ihrem Objektmodell als Alias für eine bestimmte Eigenschaft angeben `x:Uid` durch Anwenden des Attributs <xref:System.Windows.Markup.UidPropertyAttribute> zu definierenden Typ. Wenn ein Framework eine bestimmte Eigenschaft angibt, ist es nicht zulässig, beide geben `x:Uid` mit dem Alias-Element für das gleiche Objekt. Wenn beide `x:Uid` und der Alias-Element angegeben werden, die .NET Framework-XAML-Dienste-API in der Regel löst <xref:System.Xaml.XamlDuplicateMemberException> für diesen Fall.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Weitere Informationen über die Rolle des `x:Uid` in WPF-Lokalisierungsprozess und die BAML-Form von XAML, finden Sie unter [Globalisierung für WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md) oder <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
 <xref:Microsoft.Build.Tasks.Windows.UidManager>  
 [Globalisierung für WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
