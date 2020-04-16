---
title: x:Shared-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: e1cd1d9db5c19decd840b433f986e0ba53557a8b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432647"
---
# <a name="xshared-attribute"></a>x:Shared-Attribut

Wenn auf `false`festgelegt, ändert sich das WPF-Ressourcenabrufverhalten, sodass Anforderungen für die attributierte Ressource eine neue Instanz für jede Anforderung erstellen, anstatt dieselbe Instanz für alle Anforderungen gemeinsam zu nutzen.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>Bemerkungen

`x:Shared`wird dem XAML-Codespace der XAML-Sprache zugeordnet und von .NET XAML Services und seinen XAML-Readern als gültiges XAML-Sprachelement erkannt. Die angegebenen Funktionen `x:Shared` von sind jedoch nur für WPF-Anwendungen und für den WPF XAML-Parser relevant. In WPF `x:Shared` ist es nur als Attribut nützlich, wenn es auf <xref:System.Windows.ResourceDictionary>ein Objekt angewendet wird, das innerhalb eines WPF vorhanden ist. Andere Verwendungen werfen keine Analyseausnahmen oder andere Fehler aus, haben jedoch keine Auswirkungen.

Die Bedeutung `x:Shared` von ist in der XAML-Sprachspezifikation nicht angegeben. Andere XAML-Implementierungen, z. B. solche, die auf .NET XAML Services aufbauen, bieten nicht unbedingt Unterstützung für die gemeinsame Nutzung von Ressourcen. Solche XAML-Implementierungen können ein ähnliches Verhalten `x:Shared` im unterstützenden Framework liefern, das auch Werte verwendet.

In WPF ist `x:Shared` `true`die Standardbedingung für Ressourcen . Diese Bedingung bedeutet, dass jede Ressourcenanforderung immer dieselbe Instanz zurückgibt.

Das Ändern eines Objekts, das über <xref:System.Windows.FrameworkElement.FindResource%2A>eine Ressourcen-API zurückgegeben wird, z. B. , oder das Ändern eines Objekts direkt in einem <xref:System.Windows.ResourceDictionary>ändert die ursprüngliche Ressource. Wenn es sich bei verweisend auf diese Ressource um dynamische Ressourcenverweise handelt, erhalten die Consumer dieser Ressource die geänderte Ressource.

Wenn es sich bei verweisend auf die [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Ressource um statische Ressourcenverweise handelt, sind Änderungen an der Ressource nach der Verarbeitungszeit irrelevant. Weitere Informationen zu statischen und dynamischen Ressourcenreferenzen finden Sie unter [XAML-Ressourcen](../fundamentals/xaml-resources-define.md).

Explizite `x:Shared="true"` Angabe erfolgt selten, da dies bereits der Standardwert ist. Im WPF-Objektmodell `x:Shared` gibt es kein direktes Codeäquivalent. Sie kann nur in einer XAML-Verwendung angegeben werden und muss entweder durch das standardmäßige WPF-Verhalten oder in einem XAML-Zwischenknotenstream auf dem Ladepfad verarbeitet werden, wenn sie mit .NET XAML Services und seinen XAML-Readern verarbeitet wird.

Ein Szenario `x:Shared="false"` für ist, <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> wenn Sie eine oder abgeleitete Klasse als Ressource definieren und dann die Elementressource in ein Inhaltsmodell einführen. `x:Shared="false"`ermöglicht das Mehrfacheinwerden einer Elementressource in derselben <xref:System.Windows.Controls.UIElementCollection>Auflistung (z. B. eine ). Andernfalls `x:Shared="false"` ist dies ungültig, da die Auflistung die Eindeutigkeit ihres Inhalts erzwingt. Das `x:Shared="false"` Verhalten erstellt jedoch eine andere identische Instanz der Ressource, anstatt dieselbe Instanz zurückzugeben.

Ein weiteres `x:Shared="false"` Szenario ist, <xref:System.Windows.Freezable> wenn Sie eine Ressource für Animationswerte verwenden, die Ressource jedoch pro Animationsbasis ändern möchten.

Bei der `false` Zeichenfolgenbehandlung von wird die Groß-/Kleinschreibung nicht berücksichtigt.

In WPF, `x:Shared` ist nur unter den folgenden Bedingungen gültig:

- Der, <xref:System.Windows.ResourceDictionary> der die `x:Shared` Elemente enthält, muss kompiliert werden. Der <xref:System.Windows.ResourceDictionary> kann nicht innerhalb von losem XAML sein oder für Designs verwendet werden.

- Der, <xref:System.Windows.ResourceDictionary> der die Elemente enthält, <xref:System.Windows.ResourceDictionary>darf nicht in einem anderen geschachtelt werden. Sie können z. `x:Shared` B. <xref:System.Windows.ResourceDictionary> nicht für <xref:System.Windows.Style> Elemente in <xref:System.Windows.ResourceDictionary> einem Element verwendet werden, das sich innerhalb eines befindet, das bereits ein Element ist.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.ResourceDictionary>
- [XAML-Ressourcen](../fundamentals/xaml-resources-define.md)
- [Basiselemente](../../framework/wpf/advanced/base-elements.md)
