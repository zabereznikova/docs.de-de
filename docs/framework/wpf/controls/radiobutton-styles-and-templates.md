---
title: RadioButton-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: f11a8338c96d14c3c518713865061e4095ff23b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078719"
---
# <a name="radiobutton-styles-and-templates"></a>RadioButton-Stile und -Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.RadioButton> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="radiobutton-parts"></a>RadioButton-Teile  
 Die <xref:System.Windows.Controls.RadioButton> Steuerelement enthält keine benannten Teile.  
  
## <a name="radiobutton-states"></a>RadioButton-Zustände  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.RadioButton> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Gedrückt|CommonStates|Das Steuerelement wird gedrückt.|  
|Deaktiviert|CommonStates|Das Steuerelement ist deaktiviert.|  
|Focused|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|Aktiviert|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.|  
|deaktiviert|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.|  
|Unbestimmt|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> ist `true`, und <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `null`.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="radiobutton-controltemplate-example"></a>RadioButton-ControlTemplate-Beispiel  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.RadioButton> Steuerelement.  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
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
