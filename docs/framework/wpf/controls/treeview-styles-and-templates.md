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
ms.openlocfilehash: 45276d23380fe956fc3d59b90d5baae23ee8a7e2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283638"
---
# <a name="treeview-styles-and-templates"></a>TreeView-Format und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.TreeView>-Steuerelement beschrieben. Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.  
  
## <a name="treeview-parts"></a>TreeView-Teile  
 Das <xref:System.Windows.Controls.TreeView>-Steuerelement verfügt über keine benannten Teile.  
  
 Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.TreeView>erstellen, enthält die Vorlage möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb eines <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element in der <xref:System.Windows.Controls.TreeView>an; das <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen im Steuerelement).  Wenn das <xref:System.Windows.Controls.ItemsPresenter> nicht das direkt untergeordnete Element des <xref:System.Windows.Controls.ScrollViewer>ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.  
  
## <a name="treeview-states"></a>TreeView-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.TreeView>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="treeviewitem-parts"></a>TreeViewItem-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.TreeViewItem>-Steuerelement aufgelistet.  
  
|-Komponente|Typ|Beschreibung|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Ein visuelles Element, das den Header Inhalt des <xref:System.Windows.Controls.TreeView> Steuer Elements enthält.|  
  
## <a name="treeviewitem-states"></a>TreeViewItem-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für <xref:System.Windows.Controls.TreeViewItem>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardstatus.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über dem <xref:System.Windows.Controls.TreeViewItem>.|  
|Deaktiviert|CommonStates|Der <xref:System.Windows.Controls.TreeViewItem> ist deaktiviert.|  
|Mit Fokus|FocusStates|Der <xref:System.Windows.Controls.TreeViewItem> hat den Fokus.|  
|Ohne Fokus|FocusStates|Der <xref:System.Windows.Controls.TreeViewItem> hat keinen Fokus.|  
|Erweitert|Expansions Zustände|Das <xref:System.Windows.Controls.TreeViewItem> Steuerelement ist erweitert.|  
|Reduziert|Expansions Zustände|Das <xref:System.Windows.Controls.TreeViewItem> Steuerelement ist reduziert.|  
|HasItems|HasItemsStates|Der <xref:System.Windows.Controls.TreeViewItem> verfügt über Elemente.|  
|NoItems|HasItemsStates|Der <xref:System.Windows.Controls.TreeViewItem> weist keine Elemente auf.|  
|Ausgewählt|SelectionStates|Der <xref:System.Windows.Controls.TreeViewItem> ist ausgewählt.|  
|Selectedinactive|SelectionStates|Der <xref:System.Windows.Controls.TreeViewItem> ist ausgewählt, aber nicht aktiv.|  
|Nicht markiert|SelectionStates|Der <xref:System.Windows.Controls.TreeViewItem> ist nicht ausgewählt.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="treeview-controltemplate-example"></a>TreeView ControlTemplate-Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.TreeView>-Steuerelement und die zugehörigen Typen definiert werden.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Steuerelementformate und -vorlagen](control-styles-and-templates.md)
- [Anpassung von Steuerelementen](control-customization.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Erstellen einer Vorlage für ein Steuerelement](../../../desktop-wpf/themes/how-to-create-apply-template.md)
