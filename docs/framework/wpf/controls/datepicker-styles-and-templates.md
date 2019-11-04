---
title: DatePicker-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: 323768b6221061d46446ab18f85555f5f7415e74
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460371"
---
# <a name="datepicker-styles-and-templates"></a>DatePicker-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.DatePicker>-Steuerelement beschrieben. Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="datepicker-parts"></a>DatePicker-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.DatePicker>-Steuerelement aufgelistet.  
  
|Segment|Geben Sie Folgendes ein:|Beschreibung|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|Der Stamm des Steuer Elements.|  
|PART_Button|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die die <xref:System.Windows.Controls.Calendar>öffnet und schließt.|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|Das Textfeld, in dem Sie ein Datum eingeben können.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Das Popup-Element für das <xref:System.Windows.Controls.DatePicker>-Steuerelement.|  
  
## <a name="datepicker-states"></a>DatePicker-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.DatePicker>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Deaktiviert|CommonStates|Der <xref:System.Windows.Controls.DatePicker> ist deaktiviert.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="datepickertextbox-parts"></a>DatePickerTextBox-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.DatePickerTextBox>-Steuerelement aufgelistet.  
  
|Segment|Geben Sie Folgendes ein:|Beschreibung|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|Das Element, das den Anfangstext in der <xref:System.Windows.Controls.DatePicker>enthält.|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|Ein visuelles Element, das ein <xref:System.Windows.FrameworkElement>enthalten kann. Der Text des <xref:System.Windows.Controls.TextBox> wird in diesem Element angezeigt.|  
  
## <a name="datepickertextbox-states"></a>DatePickerTextBox-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.DatePickerTextBox>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Deaktiviert|CommonStates|Der <xref:System.Windows.Controls.Primitives.DatePickerTextBox> ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über dem <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|ReadOnly|CommonStates|Der Benutzer kann den Text im <xref:System.Windows.Controls.Primitives.DatePickerTextBox>nicht ändern.|  
|Mit Fokus|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|Genauer Beobachtung erfolgen|Watermarkstates|Das-Steuerelement zeigt den ursprünglichen Text an.  Der <xref:System.Windows.Controls.Primitives.DatePickerTextBox> befindet sich im Zustand, wenn der Benutzer keinen Text eingegeben hat oder ein Datum ausgewählt hat.|  
|Wasserzeichen|Watermarkstates|Der Benutzer hat Text in den <xref:System.Windows.Controls.Primitives.DatePickerTextBox> eingegeben oder ein Datum im <xref:System.Windows.Controls.DatePicker>ausgewählt.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt keinen Fokus.|  
  
## <a name="datepicker-controltemplate-example"></a>DatePicker ControlTemplate-Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.DatePicker>-Steuerelement definiert wird.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
 Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Steuerelementformate und -vorlagen](control-styles-and-templates.md)
- [Anpassung von Steuerelementen](control-customization.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
