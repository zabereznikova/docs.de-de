---
title: 'Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: a61a8538fb9b4245e3f3705c5d5cbb1b45ed0b72
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47089080"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit
Dieses Verfahren zeigt, wie Sie ein Windows Presentation Foundation (WPF)-Steuerelement in Windows Forms zu kopieren.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a>Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit  
  
1.  Fügen Sie eine neue WPF <xref:System.Windows.Controls.UserControl> zu Ihrer Windows Forms-Projekt. Verwenden Sie den Standardnamen (`UserControl1.xaml`) für den Steuerelementtyp. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalt in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `UserControl1` zu `200`.  
  
3.  Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf `Blue` fest.  
  
4.  Erstellen Sie das Projekt.  
  
5.  Öffnen Sie `Form1` im Windows Forms-Designer.  
  
6.  Von der **Toolbox**, ziehen Sie eine Instanz des `UserControl1` auf das Formular.  
  
     Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.  
  
7.  Während `elementHost1` ausgewählt ist, drücken Sie STRG + C, um das Steuerelement in die Zwischenablage zu kopieren.  
  
8.  Drücken Sie STRG + V, um die Kopie des Steuerelements auf das Formular einfügen.  
  
     Ein neues <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement mit dem Namen `elementHost2` wird auf dem Formular erstellt.  
  
## <a name="see-also"></a>Siehe auch  

- <xref:System.Windows.Forms.Integration.ElementHost>  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
- [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
- [Verwenden von WPF-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)