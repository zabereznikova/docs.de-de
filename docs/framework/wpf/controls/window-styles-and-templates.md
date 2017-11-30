---
title: Window-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0415bfae8e1065759efaac1a779655444451fa24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="window-styles-and-templates"></a>Window-Stile und -Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Window> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="window-parts"></a>Fenster teilen  
 Die <xref:System.Windows.Window> Steuerelement enthält keine benannten Teile.  
  
## <a name="window-states"></a>Fenster-Zustände  
 Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Window> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.|  
  
## <a name="window-controltemplate-example"></a>Beispiel für Fenster-ControlTemplate  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Window> Steuerelement.  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Steuerelementformate und -vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
