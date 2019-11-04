---
title: x:Shared-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: c820a9b1d9708e24b1460378199a6addc1e20899
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459930"
---
# <a name="xshared-attribute"></a>x:Shared-Attribut
Wenn diese Einstellung auf `false`festgelegt ist, wird das WPF-Ressourcen Abruf Verhalten geändert, sodass Anforderungen für die attributierte Ressource für jede Anforderung eine neue Instanz erstellen, anstatt dieselbe Instanz für alle Anforderungen zu verwenden.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Hinweise  
 `x:Shared` wird dem XAML-Namespace der XAML-Sprache zugeordnet und als gültiges XAML-sprach Element durch .NET Framework XAML-Dienste und deren XAML-Reader erkannt. Die angegebenen Funktionen von `x:Shared` sind jedoch nur für WPF-Anwendungen und für den WPF-XAML-Parser relevant. In WPF ist `x:Shared` nur als Attribut nützlich, wenn es auf ein Objekt angewendet wird, das in einem WPF-<xref:System.Windows.ResourceDictionary>vorhanden ist. Andere Verwendungen lösen keine analysieren-Ausnahmen oder andere Fehler aus, aber Sie haben keine Auswirkung.  
  
 Die Bedeutung von `x:Shared` ist nicht in der XAML-Sprachspezifikation angegeben. Andere XAML-Implementierungen, wie z. b. solche, die auf .NET Framework XAML-Diensten aufbauen, bieten nicht notwendigerweise Unterstützung für Ressourcen Freigabe. Solche XAML-Implementierungen können ein ähnliches Verhalten im unterstützenden Framework bereitstellen, das auch `x:Shared` Werte verwendet.  
  
 In WPF ist die Standard `x:Shared` Bedingung für Ressourcen `true`. Diese Bedingung bedeutet, dass jede angegebene Ressourcen Anforderung immer dieselbe Instanz zurückgibt.  
  
 Wenn Sie ein Objekt ändern, das über eine Ressourcen-API zurückgegeben wird, z. b. <xref:System.Windows.FrameworkElement.FindResource%2A>, oder ein Objekt direkt innerhalb eines <xref:System.Windows.ResourceDictionary>ändern, wird die ursprüngliche Ressource geändert. Wenn Verweise auf diese Ressource dynamische Ressourcen Verweise waren, erhalten die Consumer dieser Ressource die geänderte Ressource.  
  
 Wenn Verweise auf die Ressource statische Ressourcen Verweise waren, sind Änderungen an der Ressource nach [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Verarbeitungszeit irrelevant. Weitere Informationen zu statischen und dynamischen Ressourcen verweisen finden Sie unter [XAML-Ressourcen](../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Das explizite Angeben von `x:Shared="true"` wird nur selten durchgeführt, da dies bereits der Standardwert ist. Es gibt keinen direkten Code gleichwertig für `x:Shared` im WPF-Objektmodell. Sie kann nur in einer XAML-Verwendung angegeben werden und muss entweder durch das standardmäßige WPF-Verhalten oder in einem zwischenxaml-knotenstream auf dem Ladepfad verarbeitet werden, wenn Sie mit .NET Framework XAML-Diensten und ihren XAML-Lesern verarbeitet werden.  
  
 Ein Szenario für `x:Shared="false"` ist, wenn Sie eine <xref:System.Windows.FrameworkElement> oder eine <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse als Ressource definieren und anschließend die Element Ressource in ein Inhalts Modell einführen. `x:Shared="false"` ermöglicht, dass eine Element Ressource mehrmals in derselben Auflistung (z. b. einer <xref:System.Windows.Controls.UIElementCollection>) eingeführt werden kann. Ohne `x:Shared="false"` ist dies ungültig, da die Auflistung die Eindeutigkeit des Inhalts erzwingt. Das `x:Shared="false"` Verhalten erstellt jedoch eine andere identische Instanz der Ressource, anstatt dieselbe Instanz zurückzugeben.  
  
 Ein weiteres Szenario für `x:Shared="false"` ist, wenn Sie eine <xref:System.Windows.Freezable> Ressource für Animations Werte verwenden, aber die Ressource auf der Basis der Animation ändern möchten.  
  
 Bei der Zeichen folgen Behandlung `false` wird die Groß-/Kleinschreibung nicht beachtet  
  
 In WPF ist `x:Shared` nur unter den folgenden Bedingungen gültig:  
  
- Die <xref:System.Windows.ResourceDictionary>, die die Elemente mit `x:Shared` enthält, muss kompiliert werden. Der <xref:System.Windows.ResourceDictionary> darf nicht in einem losen XAML-Code oder für Designs verwendet werden.  
  
- Die <xref:System.Windows.ResourceDictionary>, die die Elemente enthält, darf nicht in einem anderen <xref:System.Windows.ResourceDictionary>geschachtelt werden. Beispielsweise können Sie `x:Shared` nicht für Elemente in einer <xref:System.Windows.ResourceDictionary> verwenden, die sich innerhalb eines <xref:System.Windows.Style> befindet, das bereits ein <xref:System.Windows.ResourceDictionary> Element ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ResourceDictionary>
- [XAML-Ressourcen](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Basiselemente](../wpf/advanced/base-elements.md)
