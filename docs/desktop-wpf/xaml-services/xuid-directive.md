---
title: x:Uid-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: b5b480016d2183268422dea861510c6a169ac27b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432617"
---
# <a name="xuid-directive"></a>x:Uid-Anweisung

Stellt einen eindeutigen Bezeichner für Markupelemente bereit. In vielen Szenarien wird dieser eindeutige Bezeichner von XAML-Lokalisierungsprozessen und -tools verwendet.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`identifier`|Eine manuell erstellte oder automatisch generierte Zeichenfolge, die in `x:Uid` einer Datei eindeutig sein soll, wenn sie von einem Consumer interpretiert wird.|

## <a name="remarks"></a>Bemerkungen

In [MS-XAML] `x:Uid` ist sie als Direktive definiert. Weitere Informationen finden Sie unter [ \[\] MS-XAML Abschnitt 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

`x:Uid`ist aufgrund `x:Name` des angegebenen XAML-Lokalisierungsszenarios diskret von beiden und so, dass Bezeichner, die `x:Name`für die Lokalisierung verwendet werden, keine Abhängigkeiten von den Auswirkungen des Programmiermodells von haben. `x:Name` Wird auch vom XAML-Namescope gesteuert. `x:Uid` Wird jedoch nicht von einem XAML-Sprachdefinierten Konzept der Eindeutigkeitserzwingung bestimmt. XAML-Prozessoren im weitesten Sinne (Prozessoren, die nicht Teil des Lokalisierungsprozesses `x:Uid` sind) werden nicht erwartet, dass sie die Eindeutigkeit von Werten erzwingen. Diese Verantwortung liegt konzeptionell beim Urheber der Werte. Die Erwartung der `x:Uid` Eindeutigkeit von Werten innerhalb einer einzigen XAML-Quelle ist für Verbraucher der Werte, z. B. dedizierte Globalisierungsprozesse oder -tools, angemessen. Das typische Eindeutigkeitsmodell besteht darin, dass `x:Uid` Werte in einer XML-codierten Datei, die XAML darstellt, eindeutig sind.

Tools, die über umfangreiche Kenntnisse eines bestimmten XAML-Schemas verfügen, können nur für echte lokalisierbare Zeichenfolgen gelten, `x:Uid` anstatt für alle Fälle, in denen ein Textzeichenfolgenwert in Markup gefunden wird.

Frameworks können eine bestimmte Eigenschaft in ihrem Objektmodell als Alias angeben, `x:Uid` indem das Attribut <xref:System.Windows.Markup.UidPropertyAttribute> auf den definierenden Typ angewendet wird. Wenn ein Framework eine bestimmte Eigenschaft angibt, `x:Uid` ist es ungültig, sowohl als auch den Aliasmember für dasselbe Objekt anzugeben. Wenn `x:Uid` beide und der Alias-Member angegeben sind, wird <xref:System.Xaml.XamlDuplicateMemberException> die .NET XAML Services-API in der Regel für diesen Fall ausgelöst.

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Weitere Informationen zur Rolle `x:Uid` des WPF-Lokalisierungsprozesses und in der BAML-Form von XAML finden Sie unter [Globalisierung für WPF](../../framework/wpf/advanced/globalization-for-wpf.md) oder<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalisierung für WPF](../../framework/wpf/advanced/globalization-for-wpf.md)
