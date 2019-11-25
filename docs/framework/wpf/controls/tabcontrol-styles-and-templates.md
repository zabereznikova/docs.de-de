---
title: TabControl-Formate und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TabControl
- TabControl [WPF], styles and templates [WPF]
- parts [WPF], TabControl
- styles [WPF], TabControl
- states [WPF], TabControl
- templates [WPF], TabControl
ms.assetid: f6b19a30-f10e-4fa1-96ce-f17a54092ab6
ms.openlocfilehash: c1410714660eb1dd867428b85a7cfacc881e5e56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283717"
---
# <a name="tabcontrol-styles-and-templates"></a>TabControl-Formate und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.TabControl>-Steuerelement beschrieben. Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.  
  
## <a name="tabcontrol-parts"></a>TabControl-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.TabControl>-Steuerelement aufgelistet.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_SelectedContentHost|<xref:System.Windows.Controls.ContentPresenter>|Das-Objekt, das den Inhalt der aktuell ausgewählten <xref:System.Windows.Controls.TabItem>anzeigt.|  
  
 Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.TabControl>erstellen, enthält die Vorlage möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb eines <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element in der <xref:System.Windows.Controls.TabControl>an; das <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen im Steuerelement).  Wenn das <xref:System.Windows.Controls.ItemsPresenter> nicht das direkt untergeordnete Element des <xref:System.Windows.Controls.ScrollViewer>ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.  
  
## <a name="tabcontrol-states"></a>TabControl-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.TabControl>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardzustand|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="tabitem-parts"></a>TabItem-Teile  
 Das <xref:System.Windows.Controls.TabItem>-Steuerelement verfügt über keine benannten Teile.  
  
## <a name="tabitem-states"></a>TabItem-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.TabItem>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|Mit Fokus|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|Ausgewählt|SelectionStates|Das Steuerelement ist ausgewählt.|  
|Nicht markiert|SelectionStates|Das Steuerelement ist nicht ausgewählt.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="tabcontrol-controltemplate-example"></a>TabControl ControlTemplate-Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.TabControl>-und <xref:System.Windows.Controls.TabItem>-Steuerelemente definieren.  
  
 [!code-xaml[ControlTemplateExamples#TabControl](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tabcontrol.xaml#tabcontrol)]  
  
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
