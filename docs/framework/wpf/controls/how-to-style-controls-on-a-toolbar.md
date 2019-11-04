---
title: 'Gewusst wie: Formatieren von Steuerelementen auf einer Symbolleiste'
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 78b9fc505c3c9045a0ca16ddaa1361c90bcc896a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459402"
---
# <a name="how-to-style-controls-on-a-toolbar"></a>Gewusst wie: Formatieren von Steuerelementen auf einer Symbolleiste
Der <xref:System.Windows.Controls.ToolBar> definiert <xref:System.Windows.ResourceKey> Objekte, um den Stil der Steuerelemente innerhalb der <xref:System.Windows.Controls.ToolBar>anzugeben.  Wenn Sie ein Steuerelement in einem <xref:System.Windows.Controls.ToolBar>formatieren möchten, legen Sie das `x:key`-Attribut des-Stils auf einen in <xref:System.Windows.Controls.ToolBar>definierten <xref:System.Windows.ResourceKey> fest.  
  
 In der <xref:System.Windows.Controls.ToolBar> werden die folgenden <xref:System.Windows.ResourceKey> Objekte definiert:  
  
- <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Stile für die Steuerelemente in einem <xref:System.Windows.Controls.ToolBar>definiert.  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
