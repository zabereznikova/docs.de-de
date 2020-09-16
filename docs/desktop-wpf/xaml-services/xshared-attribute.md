---
title: x:Shared-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: d5000b51d83066ec2d529db2033d8ac54f7ad329
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557787"
---
# <a name="xshared-attribute"></a>x:Shared-Attribut

Wenn diese Einstellung auf festgelegt `false` ist, wird das WPF-Ressourcen Abruf Verhalten geändert, sodass Anforderungen der attributierten Ressource für jede Anforderung eine neue Instanz erstellen, anstatt dieselbe Instanz für alle Anforderungen zu verwenden.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>Hinweise

`x:Shared` wird dem XAML-Namespace der XAML-Sprache zugeordnet und als gültiges XAML-sprach Element durch .net XAML-Dienste und deren XAML-Reader erkannt. Die angegebenen Funktionen von sind jedoch `x:Shared` nur für WPF-Anwendungen und für den WPF-XAML-Parser relevant. In WPF `x:Shared` ist nur als Attribut nützlich, wenn es auf ein Objekt angewendet wird, das in einem WPF vorhanden ist <xref:System.Windows.ResourceDictionary> . Andere Verwendungen lösen keine analysieren-Ausnahmen oder andere Fehler aus, aber Sie haben keine Auswirkung.

Die Bedeutung von `x:Shared` ist nicht in der XAML-Sprachspezifikation angegeben. Andere XAML-Implementierungen, wie z. b. solche, die auf .net XAML-Diensten aufbauen, bieten nicht notwendigerweise Unterstützung für Ressourcen Freigabe. Solche XAML-Implementierungen können ein ähnliches Verhalten im unterstützenden Framework bereitstellen, das auch- `x:Shared` Werte verwendet.

In WPF ist die Standard `x:Shared` Bedingung für-Ressourcen `true` . Diese Bedingung bedeutet, dass jede angegebene Ressourcen Anforderung immer dieselbe Instanz zurückgibt.

Wenn Sie ein Objekt ändern, das über eine Ressourcen-API zurückgegeben wird, z. b. <xref:System.Windows.FrameworkElement.FindResource%2A> oder ein Objekt direkt innerhalb eines-Objekts ändert <xref:System.Windows.ResourceDictionary> , wird die ursprüngliche Ressource geändert. Wenn Verweise auf diese Ressource dynamische Ressourcen Verweise waren, erhalten die Consumer dieser Ressource die geänderte Ressource.

Wenn Verweise auf die Ressource statische Ressourcen Verweise waren, sind Änderungen an der Ressource nach der [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Verarbeitungszeit irrelevant. Weitere Informationen zu statischen und dynamischen Ressourcen verweisen finden Sie unter [XAML-Ressourcen](../fundamentals/xaml-resources-define.md).

Die explizite Angabe von erfolgt `x:Shared="true"` selten, da dies bereits der Standardwert ist. Im WPF-Objektmodell ist keine direkte Code Entsprechung für vorhanden `x:Shared` . Sie kann nur in einer XAML-Verwendung angegeben werden und muss entweder durch das WPF-Standardverhalten oder in einem zwischengeschalteten XAML-knotenstream auf dem Ladepfad verarbeitet werden, wenn Sie mithilfe von .net XAML-Diensten und ihren XAML-Lesern verarbeitet wird.

Ein Szenario für `x:Shared="false"` ist, wenn Sie eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse als Ressource definieren und anschließend die Element Ressource in ein Inhalts Modell einführen. `x:Shared="false"` ermöglicht, dass eine Element Ressource mehrmals in derselben Auflistung (z. b. in) eingeführt werden kann <xref:System.Windows.Controls.UIElementCollection> . Ohne `x:Shared="false"` Diese ist ungültig, da die Auflistung die Eindeutigkeit des Inhalts erzwingt. Das `x:Shared="false"` Verhalten erstellt jedoch eine andere identische Instanz der Ressource, anstatt dieselbe Instanz zurückzugeben.

Ein anderes Szenario für `x:Shared="false"` ist, wenn Sie eine <xref:System.Windows.Freezable> Ressource für Animations Werte verwenden, aber die Ressource auf der Basis der Animation ändern möchten.

Bei der Zeichen folgen Behandlung von `false` wird keine Groß-/Kleinschreibung beachtet

In WPF `x:Shared` ist nur unter den folgenden Bedingungen gültig:

- Die <xref:System.Windows.ResourceDictionary> , die die Elemente mit enthält, `x:Shared` muss kompiliert werden. <xref:System.Windows.ResourceDictionary>Kann nicht in einem losen XAML-Code oder für Designs verwendet werden.

- Die <xref:System.Windows.ResourceDictionary> , die die Elemente enthält, darf nicht in einer anderen geschachtelt werden <xref:System.Windows.ResourceDictionary> . Beispielsweise können Sie nicht `x:Shared` für Elemente in einem verwenden, das <xref:System.Windows.ResourceDictionary> sich innerhalb eines befindet <xref:System.Windows.Style> , das bereits ein- <xref:System.Windows.ResourceDictionary> Element ist.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ResourceDictionary>
- [XAML-Ressourcen](../fundamentals/xaml-resources-define.md)
- [Basiselemente](/dotnet/desktop/wpf/advanced/base-elements)
