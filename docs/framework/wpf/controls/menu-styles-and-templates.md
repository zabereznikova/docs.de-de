---
title: Menu-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: 3f5e1b85059727b97b08a03b5ee494e5d2b37fb2
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457564"
---
# <a name="menu-styles-and-templates"></a>Menu-Stile und -Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Menu> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="menu-parts"></a>Menu-Teile  
 Die <xref:System.Windows.Controls.Menu> Steuerelement enthält keine benannten Teile.  
  
 Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Menu>, Ihrer Vorlage enthalten möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> wird jedes Element in der <xref:System.Windows.Controls.Menu>; das <xref:System.Windows.Controls.ScrollViewer> Bildlauf im Steuerelement aktiviert).  Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.  
  
## <a name="menu-states"></a>Menüzustände  
 Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Menu> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.|  
  
## <a name="menuitem-parts"></a>"MenuItem"-Teile  
 Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.Menu> Steuerelement.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Der Bereich für das Untermenü.|  
  
 Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.MenuItem>, Ihrer Vorlage enthalten möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> wird jedes Element in der <xref:System.Windows.Controls.MenuItem>; das <xref:System.Windows.Controls.ScrollViewer> Bildlauf im Steuerelement aktiviert).  Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.  
  
## <a name="menuitem-states"></a>Status "MenuItem"  
 Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.MenuItem> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a>Menü- und "MenuItem" ControlTemplate-Beispiel  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Menu> Steuerelement.  
  
 [!code-xaml[ControlTemplateExamples#Menu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.MenuItem> Steuerelement.  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 Das folgende Beispiel definiert die `MenuScrollViewer`, der im vorherigen Beispiel verwendet wird.  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 Die <xref:System.Windows.Controls.ControlTemplate> Beispiele verwenden eine oder mehrere der folgenden Ressourcen.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Steuerelementformate und -vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
