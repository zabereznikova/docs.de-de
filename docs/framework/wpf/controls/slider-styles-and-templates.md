---
title: Slider-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: f533142d5ba202bd4aaf628487eaaa2a18a535d0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283389"
---
# <a name="slider-styles-and-templates"></a>Slider-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Slider>-Steuerelement beschrieben. Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.  
  
## <a name="slider-parts"></a>Schieberegler-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Slider>-Steuerelement aufgelistet.  
  
|-Komponente|Typ|Beschreibung|  
|-|-|-|  
|PART_Track|<xref:System.Windows.Controls.Primitives.Track>|Der Container für das Element, das die Position des <xref:System.Windows.Controls.Slider>angibt.|  
|PART_SelectionRange|<xref:System.Windows.FrameworkElement>|Das Element, das einen Auswahlbereich entlang der <xref:System.Windows.Controls.Slider>anzeigt.  Der Auswahlbereich ist nur sichtbar, wenn die <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A>-Eigenschaft `true`ist.|  
  
## <a name="slider-states"></a>Schieberegler-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Slider>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardstatus.|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Deaktiviert|CommonStates|Das Steuerelement ist deaktiviert.|  
|Mit Fokus|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="slider-controltemplate-example"></a>Beispiel für Schieberegler-ControlTemplate  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Slider>-Steuerelement definiert wird.  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
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
