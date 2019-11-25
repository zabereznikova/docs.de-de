---
title: ToggleButton-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: a4c449a561017659db7f54fd3cdb8964742650de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283672"
---
# <a name="togglebutton-styles-and-templates"></a>ToggleButton-Stile und -Vorlagen

In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Primitives.ToggleButton>-Steuerelement beschrieben. Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.

## <a name="togglebutton-parts"></a>Teile

Das <xref:System.Windows.Controls.Primitives.ToggleButton>-Steuerelement verfügt über keine benannten Teile.

## <a name="togglebutton-states"></a>Objektstatus

In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.ToggleButton>-Steuerelement aufgelistet.

|VisualState-Name|VisualStateGroup-Name|Beschreibung|
|-|-|-|
|Normal|CommonStates|Der Standardzustand|
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|
|Gedrückt|CommonStates|Das Steuerelement wird gedrückt.|
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|
|Mit Fokus|FocusStates|Der Fokus liegt auf dem Steuerelement.|
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|
|Aktiviert|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `true`.|
|Benem|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `false`.|
|Unbestimmten|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> ist `true`, und <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `null`.|
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|

> [!NOTE]
> Wenn der Unbestimmtheit des visuellen Zustands nicht in der Steuerelement Vorlage vorhanden ist, wird der nicht überprüfte visuelle Zustand als visueller Standardzustand verwendet.

## <a name="togglebutton-controltemplate-example"></a>Beispiel für eine Beispiel-ControlTemplate

Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Primitives.ToggleButton>-Steuerelement definiert wird.

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

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
