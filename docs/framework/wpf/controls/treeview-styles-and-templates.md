---
title: TreeView-Format und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TreeView
- templates [WPF], TreeView
- parts [WPF], TreeView
- states [WPF], TreeView
- styles [WPF], TreeView
- TreeView [WPF], styles and templates
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
ms.openlocfilehash: 9f963e4b60193197ae56e2021d76d541ad6bfbef
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="treeview-styles-and-templates"></a>TreeView-Format und -Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.TreeView> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="treeview-parts"></a>TreeView-Teile  
 Die <xref:System.Windows.Controls.TreeView> Steuerelement enthält keine benannten Teile.  
  
 Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.TreeView>, Ihrer Vorlage enthalten möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> wird jedes Element in der <xref:System.Windows.Controls.TreeView>; das <xref:System.Windows.Controls.ScrollViewer> Bildlauf im Steuerelement aktiviert).  Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.  
  
## <a name="treeview-states"></a>TreeView-Zustände  
 Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.TreeView> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.|  
  
## <a name="treeviewitem-parts"></a>TreeViewItem-Teile  
 Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.TreeViewItem> Steuerelement.  
  
|Segment|Typ|Beschreibung|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Ein visuelles Element, das diesen Inhalt der Header enthält das <xref:System.Windows.Controls.TreeView> Steuerelement.|  
  
## <a name="treeviewitem-states"></a>TreeViewItem-Zustände  
 Die folgende Tabelle enthält die visueller Zustände für <xref:System.Windows.Controls.TreeViewItem> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Befindet sich der Mauszeiger über dem <xref:System.Windows.Controls.TreeViewItem>.|  
|Deaktiviert|CommonStates|Die <xref:System.Windows.Controls.TreeViewItem> ist deaktiviert.|  
|Focused|FocusStates|Die <xref:System.Windows.Controls.TreeViewItem> den Fokus hat.|  
|Ohne Fokus|FocusStates|Die <xref:System.Windows.Controls.TreeViewItem> verfügt nicht über den Fokus.|  
|Erweitert|ExpansionStates|Die <xref:System.Windows.Controls.TreeViewItem> Steuerelement erweitert ist.|  
|Reduziert|ExpansionStates|Die <xref:System.Windows.Controls.TreeViewItem> Steuerelement reduziert wird.|  
|"HasItems"|HasItemsStates|Die <xref:System.Windows.Controls.TreeViewItem> Elemente enthält.|  
|NoItems|HasItemsStates|Die <xref:System.Windows.Controls.TreeViewItem> besitzt keine Elemente.|  
|Ausgewählt|SelectionStates|Die <xref:System.Windows.Controls.TreeViewItem> ausgewählt ist.|  
|SelectedInactive|SelectionStates|Die <xref:System.Windows.Controls.TreeViewItem> ist ausgewählt, aber nicht aktiv.|  
|Nicht markiert|SelectionStates|Die <xref:System.Windows.Controls.TreeViewItem> nicht ausgewählt ist.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.|  
  
## <a name="treeview-controltemplate-example"></a>TreeView-ControlTemplate-Beispiel  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.TreeView> -Steuerelement und seine zugehörigen Typen.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Steuerelementformate und -vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
