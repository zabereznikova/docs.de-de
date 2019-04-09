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
ms.openlocfilehash: 01841bb828594dd4cac0c179d70495fe392c8de5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142702"
---
# <a name="treeview-styles-and-templates"></a>TreeView-Format und -Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.TreeView> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="treeview-parts"></a>TreeView-Teile  
 Die <xref:System.Windows.Controls.TreeView> Steuerelement enthält keine benannten Teile.  
  
 Bei der Erstellung einer <xref:System.Windows.Controls.ControlTemplate> für ein <xref:System.Windows.Controls.TreeView>, Ihrer Vorlage enthalten möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> stellt jedes Element in der <xref:System.Windows.Controls.TreeView>; die <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen innerhalb des Steuerelements).  Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen, `ItemsPresenter`.  
  
## <a name="treeview-states"></a>TreeView-Zustände  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.TreeView> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="treeviewitem-parts"></a>"TreeViewItem" Teilen  
 Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.TreeViewItem> Steuerelement.  
  
|Segment|Typ|Beschreibung|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Ein visuelles Element, das diesen Inhalt der Header enthält den <xref:System.Windows.Controls.TreeView> Steuerelement.|  
  
## <a name="treeviewitem-states"></a>"TreeViewItem"-Status  
 Die folgende Tabelle enthält die visuellen Zustände <xref:System.Windows.Controls.TreeViewItem> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Befindet sich der Mauszeiger über die <xref:System.Windows.Controls.TreeViewItem>.|  
|Deaktiviert|CommonStates|Die <xref:System.Windows.Controls.TreeViewItem> ist deaktiviert.|  
|Focused|FocusStates|Die <xref:System.Windows.Controls.TreeViewItem> den Fokus besitzt.|  
|Ohne Fokus|FocusStates|Die <xref:System.Windows.Controls.TreeViewItem> keinen Fokus besitzt.|  
|Erweitert|ExpansionStates|Die <xref:System.Windows.Controls.TreeViewItem> Steuerelement erweitert ist.|  
|Reduziert|ExpansionStates|Die <xref:System.Windows.Controls.TreeViewItem> -Steuerelement reduziert ist.|  
|HasItems|HasItemsStates|Die <xref:System.Windows.Controls.TreeViewItem> über Elemente verfügt.|  
|NoItems|HasItemsStates|Die <xref:System.Windows.Controls.TreeViewItem> verfügt über keine Elemente.|  
|Ausgewählt|SelectionStates|Die <xref:System.Windows.Controls.TreeViewItem> ausgewählt ist.|  
|SelectedInactive|SelectionStates|Die <xref:System.Windows.Controls.TreeViewItem> ist ausgewählt, aber nicht aktiv.|  
|Nicht markiert|SelectionStates|Die <xref:System.Windows.Controls.TreeViewItem> nicht ausgewählt ist.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="treeview-controltemplate-example"></a>TreeView-ControlTemplate-Beispiel  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.TreeView> -Steuerelement und seine zugehörigen Typen.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Steuerelementformate und -vorlagen](control-styles-and-templates.md)
- [Anpassung von Steuerelementen](control-customization.md)
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
