---
title: "Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1752691b3cc6809f1a5da54a01e81de2d4037d19
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms mithilfe des Designers
Im folgenden Verfahren erstellen Sie eine multipane-Benutzeroberfläche, die mit dem Umwandlungsoperator in Microsoft Outlook mit verwendet wird eine **Ordner** Liste eine **Nachrichten** Bereich und einer **Vorschau** Bereich. In dieser Anordnung erfolgt hauptsächlich durch Andocken von Steuerelementen mit dem Formular.  
  
 Wenn Sie ein Steuerelement andocken, bestimmen Sie, welche Seite des übergeordneten Containers ein Steuerelement angedockt wird. Daher, wenn Sie festlegen, die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Right>, dem rechten Rand des Steuerelements an den rechten Rand am übergeordneten Steuerelement angedockt wird. Darüber hinaus wird der angedockte Rand des Steuerelements Größe des Containersteuerelements entsprechen. Weitere Informationen darüber, wie die <xref:System.Windows.Forms.SplitContainer.Dock%2A> -Eigenschaft funktioniert, finden Sie unter [Vorgehensweise: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Hierin liegt der Schwerpunkt auf Anordnen der <xref:System.Windows.Forms.SplitContainer> und anderer Steuerelemente auf dem Formular und nicht zum Hinzufügen von Funktionen, damit die Anwendung Microsoft Outlook zu imitieren.  
  
 Um diese Benutzeroberfläche zu erstellen, platzieren Sie alle Steuerelemente innerhalb einer <xref:System.Windows.Forms.SplitContainer> -Steuerelement, das enthält eine <xref:System.Windows.Forms.TreeView> Steuerelement im linken Bereich. Der rechte Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement enthält eine zweite <xref:System.Windows.Forms.SplitContainer> -Steuerelement mit einer <xref:System.Windows.Forms.ListView> Steuerelement oben ein <xref:System.Windows.Forms.RichTextBox> Steuerelement. Diese <xref:System.Windows.Forms.SplitContainer> Steuerelemente ermöglichen unabhängigen Ändern der Größe der Steuerelemente im Formular. Sie können die Verfahren in diesem Verfahren zum Erstellen benutzerdefinierter Benutzeroberflächen Ihrer Wahl anpassen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>So erstellen eine Outlook-Stil-Benutzeroberfläche zur Entwurfszeit  
  
1.  Erstellen Sie ein neues Windows-Anwendungsprojekt. Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** in das Formular. In der **Eigenschaften** legen die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.TreeView> -Steuerelement aus der **Toolbox** in den linken Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement. In der **Eigenschaften** legen die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Left> durch Klicken auf den linken Bereich im Wert-Editor angezeigt, wenn auf der Pfeil nach unten geklickt wird.  
  
4.  Ziehen Sie ein weiteres <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox**; platzieren Sie es im rechten Bereich, der die <xref:System.Windows.Forms.SplitContainer> Steuerelement dem Formular hinzugefügt. In der **Eigenschaften** legen die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft, um <xref:System.Windows.Forms.DockStyle.Fill> und die <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Eigenschaft, um <xref:System.Windows.Forms.Orientation.Horizontal>.  
  
5.  Ziehen Sie eine <xref:System.Windows.Forms.ListView> -Steuerelement aus der **Toolbox** in den oberen Bereich des zweiten <xref:System.Windows.Forms.SplitContainer> Steuerelement dem Formular hinzugefügt. Legen Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A>-Eigenschaft des <xref:System.Windows.Forms.ListView>-Steuerelements auf <xref:System.Windows.Forms.DockStyle.Fill> fest.  
  
6.  Ziehen Sie eine <xref:System.Windows.Forms.RichTextBox> -Steuerelement aus der **Toolbox** in den unteren Bereich des zweiten <xref:System.Windows.Forms.SplitContainer> Steuerelement. Legen Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A>-Eigenschaft des <xref:System.Windows.Forms.RichTextBox>-Steuerelements auf <xref:System.Windows.Forms.DockStyle.Fill> fest.  
  
     Wenn drücken Sie F5, um die Anwendung auszuführen die Sie, zeigt das Formular an diesem Punkt eine dreiteilige Benutzeroberfläche, die von Microsoft Outlook ähnelt.  
  
    > [!NOTE]
    >  Beim Platzieren Sie den Mauszeiger über eines der Splitter innerhalb der <xref:System.Windows.Forms.SplitContainer> Steuerelemente, Sie können die Größe der internen Dimensionen.  
  
     An diesem Punkt haben Sie bei der Entwicklung eine anspruchsvolle Benutzeroberfläche gestalteten. Der nächste Schritt besteht Programmieren der Anwendung selbst, z. B. durch Verbinden der <xref:System.Windows.Forms.TreeView> Steuerelement und <xref:System.Windows.Forms.ListView> Steuerelemente an eine Art von Datenquelle. Weitere Informationen zum Verbinden von Steuerelementen an Daten finden Sie unter [Datenbindung und Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
