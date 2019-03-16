---
title: x:Uid-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 6e946c63227a06b2032ce27e61899c1b8f05ec9f
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58042971"
---
# <a name="xuid-directive"></a>x:Uid-Anweisung
Stellt einen eindeutigen Bezeichner für die Markupelemente bereit. In vielen Fällen wird dieser eindeutige Bezeichner von XAML Lokalisierungsprozesse und Tools verwendet.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`identifier`|Eine manuell erstellte oder automatisch generierte Zeichenfolge, die in einer Datei eindeutig sein sollte, wenn es vom interpretiert wird ein `x:Uid` Consumer.|  
  
## <a name="remarks"></a>Hinweise  
 In [MS-XAML] `x:Uid` als eine Direktive definiert ist. Weitere Informationen finden Sie unter [ \[MS-XAML-\] Abschnitt 5.3.6](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid` diskret aus `x:Name` sowohl aufgrund der angegebenen XAML-Lokalisierung-Szenario, Bezeichner, die für die Lokalisierung verwendet werden keine Abhängigkeiten auf die programming Model Auswirkungen haben und `x:Name`. Darüber hinaus `x:Name` unterliegt der XAML-Namescope; allerdings `x:Uid` unterliegt keine XAML-Sprache definiert-Konzept der Eindeutigkeit erzwingen. XAML-Prozessoren im weitesten Sinne (Prozessoren, die nicht Teil des Lokalisierungsprozesses sind) wird nicht erwartet Erzwingen der Eindeutigkeit von `x:Uid` Werte. Diese Verantwortung ist vom Konzept her der Ersteller der Werte. Eindeutigkeit des erwarten, dass `x:Uid` Werte innerhalb einer einzelnen XAML-Quelle ist sinnvoll für Consumer der Werte, z. B. dedizierten Globalisierungsprozessen oder Tools. Die typische Eindeutigkeit-Modell ist `x:Uid` Werte sind eindeutig in einer XML-codierte Datei, die XAML darstellt.  
  
 Tools, die erhebliche ausreichende praktische Kenntnisse in einem bestimmten XAML-Schema können anzuwendende `x:Uid` nur für "true" lokalisierbare Zeichenfolgen anstelle von für alle Fälle, in denen ein Textzeichenfolgenwert in Markup gefunden wird.  
  
 Frameworks können eine bestimmte Eigenschaft angeben, in ihrem Objektmodell als Alias für `x:Uid` durch Anwenden des Attributs <xref:System.Windows.Markup.UidPropertyAttribute> zu definierenden Typs. Wenn ein Framework eine bestimmte Eigenschaft angegeben ist, es ist nicht zulässig, beide anzugeben `x:Uid` und das Element mit einem Alias versehen, auf das gleiche Objekt. Wenn beide `x:Uid` und die Alias-Element angegeben werden, die .NET Framework XAML Services-API in der Regel löst eine <xref:System.Xaml.XamlDuplicateMemberException> für diesen Fall.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Weitere Informationen über die Rolle des `x:Uid` in der WPF-Lokalisierung-Prozess und die BAML-Form von XAML, finden Sie unter [Globalisierung für WPF](../wpf/advanced/globalization-for-wpf.md) oder <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalisierung für WPF](../wpf/advanced/globalization-for-wpf.md)
