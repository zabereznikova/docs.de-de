---
title: "Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9324a7b2634eb7a42b2dbd00814e9647e6741369
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit
Dieses Verfahren wird gezeigt, wie ein Windows Presentation Foundation (WPF)-Steuerelement in einem Windows Form zu kopieren.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a>Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit  
  
1.  Fügen Sie eine neue WPF <xref:System.Windows.Controls.UserControl> dem Windows Forms-Projekt. Verwenden Sie den Standardnamen (`UserControl1.xaml`) für den Steuerelementtyp. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  In der **Eigenschaften** Fenster, legen Sie den Wert von der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften des `UserControl1` auf `200`.  
  
3.  Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf `Blue` fest.  
  
4.  Erstellen Sie das Projekt.  
  
5.  Öffnen Sie `Form1` im Windows Forms-Designer.  
  
6.  Aus der **Toolbox**, ziehen Sie eine Instanz des `UserControl1` auf das Formular.  
  
     Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.  
  
7.  Während `elementHost1` ausgewählt ist, drücken Sie STRG + C, um das Steuerelement in die Zwischenablage zu kopieren.  
  
8.  Drücken Sie STRG + V, um das kopierte Steuerelement auf das Formular einfügen.  
  
     Ein neues <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement namens `elementHost2` wird auf dem Formular erstellt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Exemplarische Vorgehensweise: Kopieren und Einfügen eines ElementHost-Steuerelements in separate Windows Forms](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Verwenden von WPF-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF-Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
