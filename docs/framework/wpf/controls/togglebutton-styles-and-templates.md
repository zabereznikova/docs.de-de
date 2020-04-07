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
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805914"
---
# <a name="togglebutton-styles-and-templates"></a>ToggleButton-Stile und -Vorlagen

In diesem Thema werden die <xref:System.Windows.Controls.Primitives.ToggleButton> Stile und Vorlagen für das Steuerelement beschrieben. Sie können die <xref:System.Windows.Controls.ControlTemplate> Standardeinstellung ändern, um dem Steuerelement ein eindeutiges Erscheinungsbild zu verleihen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein Steuerelement](../../../desktop-wpf/themes/how-to-create-apply-template.md).

## <a name="togglebutton-parts"></a>ToggleButton-Teile

Das <xref:System.Windows.Controls.Primitives.ToggleButton> Steuerelement enthält keine benannten Teile.

## <a name="togglebutton-states"></a>ToggleButton-Zustände

In der folgenden Tabelle sind <xref:System.Windows.Controls.Primitives.ToggleButton> die visuellen Zustände für das Steuerelement aufgeführt.

|VisualState-Name|VisualStateGroup-Name|BESCHREIBUNG|
|-|-|-|
|Normal|CommonStates|Der Standardzustand|
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|
|Gedrückt|CommonStates|Das Steuerelement wird gedrückt.|
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|
|Mit Fokus|FocusStates|Der Fokus liegt auf dem Steuerelement.|
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|
|Aktiviert|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `true`|
|Deaktiviert|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `false`|
|Unbestimmten|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> ist `true`, und <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `null`.|
|Gültig|ValidationStates|Das Steuerelement <xref:System.Windows.Controls.Validation> verwendet die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Klasse, `false`und die angefügte Eigenschaft ist .|
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte `true` Eigenschaft ist und das Steuerelement hat den Fokus.|
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte `true` Eigenschaft ist und das Steuerelement hat keinen Fokus.|

> [!NOTE]
> Wenn der visuelle Status Unbestimmt in der Steuerelementvorlage nicht vorhanden ist, wird der visuelle Status Ungeprüft als visueller Standardstatus verwendet.

## <a name="togglebutton-controltemplate-example"></a>ToggleButton ControlTemplate Beispiel

Das folgende Beispiel zeigt, <xref:System.Windows.Controls.ControlTemplate> wie <xref:System.Windows.Controls.Primitives.ToggleButton> sie eine für das Steuerelement definieren.

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Steuerelementformate und -vorlagen](control-styles-and-templates.md)
- [Anpassung von Steuerelementen](control-customization.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Erstellen einer Vorlage für ein Steuerelement](../../../desktop-wpf/themes/how-to-create-apply-template.md)
