---
title: ListBox-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
ms.openlocfilehash: 552df5df6bdf8d9cdd8241c3e68cae671a24c6a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577762"
---
# <a name="listbox-styles-and-templates"></a>ListBox-Stile und -Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ListBox> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="listbox-parts"></a>ListBox-Teile  
 Die <xref:System.Windows.Controls.ListBox> Steuerelement enthält keine benannten Teile.  
  
 Bei der Erstellung einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ListBox>, Ihrer Vorlage enthalten möglicherweise ein <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> stellt jedes Element in der <xref:System.Windows.Controls.ListBox>; die <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen innerhalb des Steuerelements).  Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen, `ItemsPresenter`.  
  
## <a name="listbox-states"></a>ListBox-Zustände  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ListBox> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Gültig|ValidationStates|Das Steuerelement ist gültig.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
  
## <a name="listboxitem-parts"></a>ListBoxItem-Teile  
 Die <xref:System.Windows.Controls.ListBoxItem> Steuerelement enthält keine benannten Teile.  
  
## <a name="listboxitem-states"></a>ListBoxItem-Zustände  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ListBox> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich auf dem Steuerelement.|  
|Deaktiviert|CommonStates|Das Element ist deaktiviert.|  
|Focused|FocusStates|Das Element besitzt den Fokus.|  
|Ohne Fokus|FocusStates|Das Element besitzt den Fokus nicht.|  
|Nicht markiert|SelectionStates|Das Element ist nicht ausgewählt.|  
|Ausgewählt|SelectionStates|Das Element ist zurzeit ausgewählt.|  
|SelectedUnfocused|SelectionStates|Das Element ist ausgewählt, besitzt jedoch keinen Fokus.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="listbox-controltemplate-example"></a>ListBox-ControlTemplate-Beispiel  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.ListBoxItem> Steuerelemente.  
  
 [!code-xaml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Steuerelementformate und -vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)
- [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
