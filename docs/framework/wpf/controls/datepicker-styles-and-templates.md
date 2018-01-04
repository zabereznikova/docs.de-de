---
title: DatePicker-Stile und Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4683ebd66afb2d4ac5bfa615336787c4006b4335
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="datepicker-styles-and-templates"></a>DatePicker-Stile und Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.DatePicker> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="datepicker-parts"></a>DatePicker-Teile  
 Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.DatePicker> Steuerelement.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|Der Stamm des Steuerelements.|  
|PART_Button|<xref:System.Windows.Controls.Button>|Schaltfläche öffnet und schließt die <xref:System.Windows.Controls.Calendar>.|  
|"PART_TextBox"|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|Das Textfeld, das Ihnen ermöglicht, geben Sie ein Datum.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Das Popup für die <xref:System.Windows.Controls.DatePicker> Steuerelement.|  
  
## <a name="datepicker-states"></a>DatePicker-Zustände  
 Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.DatePicker> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Deaktiviert|CommonStates|Die <xref:System.Windows.Controls.DatePicker> ist deaktiviert.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.|  
  
## <a name="datepickertextbox-parts"></a>DatePickerTextBox-Teile  
 Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.Primitives.DatePickerTextBox> Steuerelement.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|Das Element mit dem ersten Text in die <xref:System.Windows.Controls.DatePicker>.|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|Ein visuelles Element, das enthalten kann eine <xref:System.Windows.FrameworkElement>. Der Text, der die <xref:System.Windows.Controls.TextBox> wird in diesem Element angezeigt.|  
  
## <a name="datepickertextbox-states"></a>DatePickerTextBox-Zustände  
 Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Primitives.DatePickerTextBox> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Deaktiviert|CommonStates|Die <xref:System.Windows.Controls.Primitives.DatePickerTextBox> ist deaktiviert.|  
|MouseOver|CommonStates|Befindet sich der Mauszeiger über dem <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|ReadOnly|CommonStates|Der Benutzer kann nicht geändert werden den Text in der <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|Focused|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|Mit einem Wasserzeichen versehen|WatermarkStates|Das Steuerelement wird der ursprünglichen Text.  Die <xref:System.Windows.Controls.Primitives.DatePickerTextBox> ist in den Zustand, wenn der Benutzer nicht eingegebenen Text oder ein Datum ausgewählt hat.|  
|Unwatermarked|WatermarkStates|Der Benutzer hat eingegebene Text in die <xref:System.Windows.Controls.Primitives.DatePickerTextBox> oder ein Datum im ausgewählten der <xref:System.Windows.Controls.DatePicker>.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.|  
  
## <a name="datepicker-controltemplate-example"></a>DatePicker-ControlTemplate-Beispiel  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.DatePicker> Steuerelement.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
 Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Steuerelementformate und -vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
