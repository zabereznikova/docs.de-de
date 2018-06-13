---
title: 'Gewusst wie: Formatieren von Steuerelementen auf einer Symbolleiste'
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: cc5ac9dd64072c34ff999255a27dd92f311cda0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551816"
---
# <a name="how-to-style-controls-on-a-toolbar"></a>Gewusst wie: Formatieren von Steuerelementen auf einer Symbolleiste
Die <xref:System.Windows.Controls.ToolBar> definiert <xref:System.Windows.ResourceKey> Objekte an, den Stil von Steuerelementen innerhalb der <xref:System.Windows.Controls.ToolBar>.  So formatieren Sie ein Steuerelement in ein <xref:System.Windows.Controls.ToolBar>legen die `x:key` Attribut des Formats, eine <xref:System.Windows.ResourceKey> in definierten <xref:System.Windows.Controls.ToolBar>.  
  
 Die <xref:System.Windows.Controls.ToolBar> definiert die folgenden <xref:System.Windows.ResourceKey> Objekte:  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert Stile für die Steuerelemente in einem <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
