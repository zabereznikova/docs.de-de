---
title: ScrollBar-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 016556fb825ddf60af7dc572d6fda7323b9bb09d
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671984"
---
# <a name="scrollbar-styles-and-templates"></a>ScrollBar-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für <xref:System.Windows.Controls.Primitives.ScrollBar> das-Steuerelement beschrieben. Sie können die Standardeinstellung <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="scrollbar-parts"></a>ScrollBar-Teile  
 In der folgenden Tabelle sind die benannten Teile für <xref:System.Windows.Controls.Primitives.ScrollBar> das-Steuerelement aufgeführt.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_Track|<xref:System.Windows.Controls.Primitives.Track>|Der Container für das Element, das die Position <xref:System.Windows.Controls.Primitives.ScrollBar>der angibt.|  
  
## <a name="scrollbar-states"></a>ScrollBar-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für <xref:System.Windows.Controls.Primitives.ScrollBar> das-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich auf dem Steuerelement.|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|Gültig|ValidationStates|Das Steuerelement verwendet <xref:System.Windows.Controls.Validation> die-Klasse <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> , und die `false`angefügte-Eigenschaft ist.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte- `true` Eigenschaft ist, und das Steuerelement besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte- `true` Eigenschaft ist, und das Steuerelement besitzt keinen Fokus.|  
  
## <a name="scrollbar-controltemplate-example"></a>ScrollBar ControlTemplate-Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Primitives.ScrollBar> -Steuerelement definiert wird.  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
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
