---
title: x:Uid-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 3de02702e6fd2be63bc2d099dad11f896b281ad1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543497"
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
|`identifier`|Eine manuell erstellte oder automatisch generierte Zeichenfolge, die in einer Datei eindeutig sein sollte, wenn Sie von einem Consumer interpretiert wird `x:Uid` .|

## <a name="remarks"></a>Hinweise

In [MS-XAML] `x:Uid` ist als-Direktive definiert. Weitere Informationen finden Sie im [ \[ Abschnitt zu MS-XAML \] 5.3.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

`x:Uid` ist aufgrund des `x:Name` angegebenen XAML-Lokalisierungs Szenarios diskret und so, dass Bezeichner, die für die Lokalisierung verwendet werden, keine Abhängigkeiten von den Auswirkungen des-Programmiermodells von haben `x:Name` . Außerdem `x:Name` wird durch den XAML-Namescope geregelt; wird jedoch `x:Uid` nicht von einem XAML-sprach definiertem Konzept der Eindeutigkeits Erzwingung gesteuert. Bei XAML-Prozessoren (Prozessoren, die nicht Teil des Lokalisierungsprozesses sind) wird davon ausgegangen, dass Sie die Eindeutigkeit von Werten nicht erzwingen `x:Uid` . Diese Verantwortung ist konzeptionell für den Absender der Werte. Die Annahme der Eindeutigkeit von `x:Uid` Werten innerhalb einer einzelnen XAML-Quelle eignet sich für Consumer der Werte, z. b. für dedizierte Globalisierungsprozesse oder Tools. Das typische Eindeutigkeits Modell ist, dass die `x:Uid` Werte innerhalb einer XML-codierten Datei, die XAML darstellt, eindeutig sind.

Tools, die über bedeutende Kenntnisse eines bestimmten XAML-Schemas verfügen, können auswählen, dass es `x:Uid` nur für echte lokalisierbare Zeichen folgen gilt, anstatt für alle Fälle, in denen ein Textzeichen folgen Wert im Markup gefunden wird.

Frameworks können eine bestimmte Eigenschaft in Ihrem Objektmodell als Alias angeben, `x:Uid` indem Sie das-Attribut <xref:System.Windows.Markup.UidPropertyAttribute> auf den definierenden Typ anwenden. Wenn ein Framework eine bestimmte Eigenschaft angibt, ist es nicht zulässig, sowohl `x:Uid` als auch das Alias Element für dasselbe Objekt anzugeben. Wenn sowohl `x:Uid` als auch das Alias Element angegeben werden, löst die .net XAML Services-API in diesem Fall in der Regel <xref:System.Xaml.XamlDuplicateMemberException> aus.

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Weitere Informationen zur Rolle von `x:Uid` im WPF-Lokalisierungsprozess und in der BAML-Form von XAML finden Sie unter [Globalisierung für WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf) oder <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalisierung für WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf)
