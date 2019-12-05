---
title: x:Uid-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 32cfd9ab0cf6037c731b619e81a7504ac92d5fb9
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837180"
---
# <a name="xuid-directive"></a>x:Uid-Anweisung
Stellt einen eindeutigen Bezeichner für Markupelemente bereit. In vielen Szenarien wird dieser eindeutige Bezeichner von XAML-Lokalisierungsprozessen und-Tools verwendet.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`identifier`|Eine manuell erstellte oder automatisch generierte Zeichenfolge, die in einer Datei eindeutig sein sollte, wenn Sie von einem `x:Uid` Consumer interpretiert wird.|  
  
## <a name="remarks"></a>Hinweise  
 In [MS-XAML] wird `x:Uid` als-Direktive definiert. Weitere Informationen finden Sie unter [\[MS-XAML\] Abschnitt 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
 `x:Uid` ist aufgrund des angegebenen XAML-Lokalisierungs Szenarios diskret `x:Name`, sodass Bezeichner, die für die Lokalisierung verwendet werden, keine Abhängigkeiten von den Auswirkungen von `x:Name`des-Programmiermodells haben. Außerdem wird `x:Name` vom XAML-Namescope gesteuert. `x:Uid` wird jedoch nicht durch ein XAML-sprach definiertes Konzept der Eindeutigkeits Erzwingung geregelt. Bei XAML-Prozessoren (Prozessoren, die nicht Teil des Lokalisierungsprozesses sind) wird davon ausgegangen, dass Sie keine Eindeutigkeit von `x:Uid` Werten erzwingen. Diese Verantwortung ist konzeptionell für den Absender der Werte. Die Annahme der Eindeutigkeit von `x:Uid` Werten innerhalb einer einzelnen XAML-Quelle eignet sich für Consumer der Werte, z. b. für dedizierte Globalisierungsprozesse oder Tools. Das typische Eindeutigkeits Modell ist, dass `x:Uid` Werte innerhalb einer XML-codierten Datei, die XAML darstellt, eindeutig sind.  
  
 Tools, die mit einem bestimmten XAML-Schema vertraut sind, können `x:Uid` nur für echte lokalisierbare Zeichen folgen anwenden, anstatt für alle Fälle, in denen ein Textzeichen folgen Wert im Markup gefunden wird.  
  
 Frameworks können eine bestimmte Eigenschaft in Ihrem Objektmodell angeben, um einen Alias für `x:Uid` zu sein, indem Sie das Attribut <xref:System.Windows.Markup.UidPropertyAttribute> auf den definierenden Typ anwenden. Wenn ein Framework eine bestimmte Eigenschaft angibt, ist es nicht zulässig, sowohl `x:Uid` als auch das Alias Element für dasselbe Objekt anzugeben. Wenn sowohl `x:Uid` als auch das Alias Element angegeben werden, löst die .NET Framework XAML-Dienste-API in diesem Fall normalerweise <xref:System.Xaml.XamlDuplicateMemberException> aus.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Weitere Informationen zur Rolle von `x:Uid` im WPF-Lokalisierungsprozess und in der BAML-Form von XAML finden Sie unter [Globalisierung für WPF](../wpf/advanced/globalization-for-wpf.md) oder <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalisierung für WPF](../wpf/advanced/globalization-for-wpf.md)
