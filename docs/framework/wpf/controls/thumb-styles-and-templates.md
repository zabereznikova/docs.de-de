---
title: Thumb-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: 0d0d88e3b527beacfa5f879027e696aa75b18147
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283683"
---
# <a name="thumb-styles-and-templates"></a>Thumb-Stile und -Vorlagen

In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement beschrieben. Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.

## <a name="thumb-parts"></a>Thumb-Teile

Das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement verfügt über keine benannten Teile.

## <a name="thumb-states"></a>Thumb-Zustände

In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement aufgelistet.

|VisualState-Name|VisualStateGroup-Name|Beschreibung|
|-|-|-|
|Normal|CommonStates|Der Standardzustand|
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|
|Gedrückt|CommonStates|Das Steuerelement wird gedrückt.|
|Deaktiviert|CommonStates|Das Steuerelement ist deaktiviert.|
|Mit Fokus|FocusStates|Der Fokus liegt auf dem Steuerelement.|
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|

## <a name="thumb-controltemplate-example"></a>Thumb ControlTemplate-Beispiel

Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement definiert wird.

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

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
