---
title: GroupBox-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187475"
---
# <a name="groupbox-styles-and-templates"></a>GroupBox-Stile und -Vorlagen
<a name="introduction"></a>In diesem Thema werden die <xref:System.Windows.Controls.GroupBox> Stile und Vorlagen für das Steuerelement beschrieben. Sie können die <xref:System.Windows.Controls.ControlTemplate> Standardeinstellung ändern, um dem Steuerelement ein eindeutiges Erscheinungsbild zu verleihen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein Steuerelement](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a>GroupBox-Teile  
 Das <xref:System.Windows.Controls.GroupBox> Steuerelement enthält keine benannten Teile.  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a>GroupBox-Zustände  
 In der folgenden Tabelle sind <xref:System.Windows.Controls.GroupBox> die visuellen Zustände für das Steuerelement aufgeführt.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Gültig|ValidationStates|Das Steuerelement <xref:System.Windows.Controls.Validation> verwendet die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Klasse, `false`und die angefügte Eigenschaft ist .|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte `true` Eigenschaft hat das Steuerelement hat den Fokus.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte `true` Eigenschaft hat das Steuerelement hat keinen Fokus.|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a>GroupBox ControlTemplate Beispiel  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.ControlTemplate> wie <xref:System.Windows.Controls.GroupBox> sie eine für das Steuerelement definieren.  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 Der <xref:System.Windows.Controls.ControlTemplate> verwendet eine oder mehrere der folgenden Ressourcen.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Steuerelementformate und -vorlagen](control-styles-and-templates.md)
- [Anpassung von Steuerelementen](control-customization.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Erstellen einer Vorlage für ein Steuerelement](../../../desktop-wpf/themes/how-to-create-apply-template.md)
