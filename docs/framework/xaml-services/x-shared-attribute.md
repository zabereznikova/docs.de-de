---
title: x:Shared-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: 1c718522a20fb2047ebf500adbf4044265e3af3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542254"
---
# <a name="xshared-attribute"></a>x:Shared-Attribut
Bei Festlegung auf `false`, verändert WPF Abrufen von Ressourcen, damit Anforderungen für die attributierte Ressource eine neue Instanz für jede Anforderung und nicht gemeinsam dieselbe Instanz für alle Anforderungen erstellen.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Hinweise  
 `x:Shared` die XAML-Namespace der XAML-Sprache zugeordnet ist, und wird von .NET Framework-XAML-Dienste und die XAML-Leser als ein gültiger XAML-Sprachelement erkannt. Allerdings die genannten Funktionen von `x:Shared` sind nur dann relevant, für die WPF-Anwendungen und der WPF XAML-Parser. In WPF `x:Shared` ist nur als Attribut nützlich, wenn es auf ein Objekt angewendet wird, die innerhalb einer WPF <xref:System.Windows.ResourceDictionary>. Andere Verwendungen lösen keine Ausnahmen der Analyse oder ein anderer Fehler, aber sie haben keine Auswirkungen.  
  
 Die Bedeutung der `x:Shared` in der XAML-Sprachspezifikation nicht angegeben ist. Andere XAML-Implementierungen, z. B. diejenigen, die auf .NET Framework-XAML-Dienste, bieten nicht notwendigerweise Ressourcenfreigabe Unterstützung. Diese XAML-Implementierungen können in der unterstützenden Framework, die auch verwendet ein ähnliches Verhalten bereitstellen `x:Shared` Werte.  
  
 In WPF, die standardmäßige `x:Shared` Bedingung für Ressourcen ist `true`. Dies bedeutet, dass alle Anforderungen für die angegebene Ressource gibt immer die gleiche Instanz zurück.  
  
 Ändern eines Objekts, das über eine Ressourcen-API, wie z. B. zurückgegeben wird <xref:System.Windows.FrameworkElement.FindResource%2A>, oder Ändern eines Objekts direkt innerhalb einer <xref:System.Windows.ResourceDictionary>, ändert sich die ursprüngliche Ressource. Würde die Verweise auf diese Ressource dynamische Ressourcenverweise, erhalten die Consumer der Ressource, die die geänderte Ressource an.  
  
 Wenn Verweise auf die Ressource statische Ressourcenverweise wurden, ändert sich auf die Ressource nach [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Verarbeitungszeit sind irrelevant. Weitere Informationen zu statischen oder dynamischen Ressourcenverweis verwenden, finden Sie unter [XAML-Ressourcen](../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Explizite Angabe `x:Shared="true"` selten erfolgt, da dies bereits die Standardeinstellung ist. Es gibt keinen direkten Code für die entsprechende `x:Shared` Objektmodell in WPF-Anwendungen; es kann nur in einer XAML-Verwendung angegeben werden und muss verarbeitet werden, mit der WPF-Standardverhalten oder in eine zwischen XAML-Knotenstream auf dem Ladepfad, wenn mithilfe von .NET Framework-XAML-Se verarbeitet Rvices und die XAML-Leser.  
  
 Ein Szenario für `x:Shared="false"` ist, wenn Sie definieren eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse als eine Ressource, und klicken Sie dann Sie die Elementressource in einem Inhaltsmodell. `x:Shared="false"` kann eine Elementressource mehrfach in der gleichen Auflistung eingefügt werden (z. B. eine <xref:System.Windows.Controls.UIElementCollection>). Ohne `x:Shared="false"` Dies ist ungültig, da erzwingt die Eindeutigkeit des Inhalts die Auflistung. Allerdings die `x:Shared="false"` Verhalten erstellt eine weitere identische Instanz der Ressource die gleiche Instanz zurückgeben.  
  
 Ein weiteres Szenario für `x:Shared="false"` ist bei Verwendung einer <xref:System.Windows.Freezable> Ressource für die Animationswerte, aber die Ressource auf einer Basis pro Animation ändern möchten.  
  
 Die Zeichenfolgenbehandlung von `false` wird Groß-/ Kleinschreibung nicht berücksichtigt.  
  
 In WPF `x:Shared` gilt nur unter folgenden Bedingungen:  
  
-   Die <xref:System.Windows.ResourceDictionary> , enthält die Elemente mit `x:Shared` muss kompiliert werden. Die <xref:System.Windows.ResourceDictionary> in loose XAML nicht möglich, oder für Designs verwendet.  
  
-   Die <xref:System.Windows.ResourceDictionary> , enthält die Elemente müssen innerhalb einer anderen nicht geschachtelt werden <xref:System.Windows.ResourceDictionary>. Beispielsweise können keine `x:Shared` für Elemente in einer <xref:System.Windows.ResourceDictionary> , der sich im eine <xref:System.Windows.Style> , der sich bereits ein <xref:System.Windows.ResourceDictionary> Element.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.ResourceDictionary>
- [XAML-Ressourcen](../../../docs/framework/wpf/advanced/xaml-resources.md)
- [Basiselemente](../../../docs/framework/wpf/advanced/base-elements.md)
