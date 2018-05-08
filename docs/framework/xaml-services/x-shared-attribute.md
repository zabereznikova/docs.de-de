---
title: x:Shared-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: bee37735382249d2919ef870ca495e6096532352
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xshared-attribute"></a>x:Shared-Attribut
Bei Festlegung auf `false`, WPF Abrufen von Ressourcen Verhalten ändert, so, dass Anforderungen für die attributierte Ressource einer neuen Instanz für jede Anforderung erstellen und für alle Anforderungen dieselbe Instanz gemeinsam.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Hinweise  
 `x:Shared` XAML-Namespace der XAML-Sprache zugeordnet ist, und wird von .NET Framework-XAML-Dienste und die XAML-Readern als ein gültiger XAML-Sprachelement erkannt. Allerdings die genannten Funktionen des `x:Shared` sind nur relevant, für die WPF-Anwendungen und der WPF XAML-Parser. In WPF `x:Shared` ist nur als Attribut nützlich, wenn auf ein Objekt angewendet wird, die eine WPF residiert <xref:System.Windows.ResourceDictionary>. Andere Verwendungen lösen Sie Ausnahmen oder ein anderer Fehler nicht, aber sie haben keine Auswirkungen.  
  
 Die Bedeutung der `x:Shared` in der XAML-Sprachspezifikation nicht angegeben ist. Andere XAML-Implementierungen, z. B. diejenigen, die auf .NET Framework XAML Services aufbauen bieten nicht notwendigerweise Ressourcenfreigabe Unterstützung. Solche Implementierungen von XAML-ähnliches Verhalten in unterstützende Framework, die auch verwendet bereitstellen konnte `x:Shared` Werte.  
  
 In WPF, die standardmäßige `x:Shared` Bedingung für Ressourcen ist `true`. Dies bedeutet, dass jede Anforderung für die angegebene Ressource immer dieselbe Instanz zurückgibt.  
  
 Ändern eines Objekts, das über eine Ressourcen-API, wie z. B. zurückgegeben wird <xref:System.Windows.FrameworkElement.FindResource%2A>, oder Ändern eines Objekts direkt innerhalb einer <xref:System.Windows.ResourceDictionary>, wird die ursprüngliche Ressource geändert. Wenn Verweise auf diese Ressource dynamische Ressourcenverweise wurden, erhalten die Consumern der Ressource, die die geänderte Ressource.  
  
 Wenn Verweise auf die Ressource statische Ressourcenverweise wurden, ändert sich auf die Ressource nach [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Verarbeitungszeit irrelevant sind. Weitere Informationen zu statischen und dynamischen Ressourcenverweise, finden Sie unter [XAML-Ressourcen](../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Explizites angeben `x:Shared="true"` selten geschieht, weil dies bereits die Standardeinstellung ist. Es ist kein direct Code für das Gegenstück zum `x:Shared` in WPF-Objektmodell; er kann nur in eine XAML-Verwendung angegeben werden und muss verarbeitet werden, mit der WPF-Standardverhalten oder in einen intermediate XAML-Knotenstreams im Ladepfad Wenn mit .NET Framework-XAML-Se verarbeitet Rvices und dessen Verwendung von XAML-Reader.  
  
 Ein Szenario für `x:Shared="false"` ist, wenn Sie definieren eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleiteten Klasse als eine Ressource, und klicken Sie dann Sie die Elementressource in einem Inhaltsmodell einführen. `x:Shared="false"` ermöglicht eine Elementressource mehrmals in der gleichen Auflistung eingeführt werden (z. B. eine <xref:System.Windows.Controls.UIElementCollection>). Ohne `x:Shared="false"` Dies ist ungültig, da die Auflistung erzwingt die Eindeutigkeit des Inhalts. Allerdings die `x:Shared="false"` Verhalten erstellt eine andere identische Instanz der Ressource anstatt der gleichen Instanz.  
  
 Ein weiteres Szenario für `x:Shared="false"` ist bei Verwendung einer <xref:System.Windows.Freezable> Ressource für die Animationswerte jedoch für die Ressource auf der Basis eines je Animation ändern möchten.  
  
 Die Behandlung von Zeichenfolgen von `false` ist nicht in der Groß-/Kleinschreibung beachtet.  
  
 In WPF `x:Shared` ist nur gültig, in den folgenden Situationen:  
  
-   Die <xref:System.Windows.ResourceDictionary> , enthält die Elemente mit `x:Shared` müssen kompiliert werden. Die <xref:System.Windows.ResourceDictionary> darf nicht in loose XAML sein oder für Designs verwendet.  
  
-   Die <xref:System.Windows.ResourceDictionary> , enthält die Elemente müssen innerhalb einer anderen nicht geschachtelt werden <xref:System.Windows.ResourceDictionary>. Angenommen, Sie können keine `x:Shared` für Elemente in einem <xref:System.Windows.ResourceDictionary> , der sich im ein <xref:System.Windows.Style> , der sich bereits ein <xref:System.Windows.ResourceDictionary> Element.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.ResourceDictionary>  
 [XAML-Ressourcen](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Basiselemente](../../../docs/framework/wpf/advanced/base-elements.md)
