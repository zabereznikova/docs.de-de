---
title: ProgressBar-Formate und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: f948cf2b4f4cd2a4cb73b0cd5fc754240c850b83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770525"
---
# <a name="progressbar-styles-and-templates"></a>ProgressBar-Formate und -Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ProgressBar> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="progressbar-parts"></a>ProgressBar-Teile  
 Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.ProgressBar> Steuerelement.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|Das Objekt, das Status angibt.|  
|PART_Track|<xref:System.Windows.FrameworkElement>|Das Objekt, das den Pfad der Statusanzeige definiert.|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|Ein Objekt, das Darstellung der Statusanzeige verbessert.|  
  
## <a name="progressbar-states"></a>ProgressBar-Zustände  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Bestimmte|CommonStates|<xref:System.Windows.Controls.ProgressBar> meldet den Fortschritt basierend auf den <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> Eigenschaft.|  
|Unbestimmt|CommonStates|<xref:System.Windows.Controls.ProgressBar> meldet den generischen Fortschritt mit einer sich wiederholenden.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="progressbar-controltemplate-example"></a>ProgressBar-ControlTemplate-Beispiel  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
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
