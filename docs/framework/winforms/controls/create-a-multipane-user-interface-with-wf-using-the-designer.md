---
title: 'Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 9c8cab952fd9d0c58380a308dd360dcedb2ea8f1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44131736"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms mithilfe des Designers
Im folgenden Verfahren erstellen Sie eine multipane-Benutzeroberfläche, die der ähnelt der Verwendung in Microsoft Outlook ist eine **Ordner** Liste eine **Nachrichten** Bereich und eine **Vorschau** Bereich. In dieser Anordnung erfolgt hauptsächlich durch Andocken von Steuerelementen mit dem Formular.  
  
 Wenn Sie ein Steuerelement andocken, legen Sie fest, welchen Rand des übergeordneten Containers ein Steuerelement angedockt ist. Folglich setzen Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Right>, dem rechten Rand des Steuerelements an den rechten Rand seines übergeordneten Steuerelements angedockt wird. Darüber hinaus wird der verankerte Rand des Steuerelements Größe des Containersteuerelements entsprechen. Weitere Informationen zur Funktionsweise des <xref:System.Windows.Forms.SplitContainer.Dock%2A> -Eigenschaft funktioniert, finden Sie unter [Vorgehensweise: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Dieses Verfahren konzentriert sich auf die Anordnung der <xref:System.Windows.Forms.SplitContainer> und andere Steuerelemente auf dem Formular und nicht zum Hinzufügen von Funktionen, die Anwendung, die Microsoft Outlook nachahmen soll.  
  
 Um diese Benutzeroberfläche zu erstellen, platzieren Sie alle Steuerelemente innerhalb einer <xref:System.Windows.Forms.SplitContainer> -Steuerelement, das enthält eine <xref:System.Windows.Forms.TreeView> Steuerelement im linken Bereich. Der rechte Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement enthält eine zweite <xref:System.Windows.Forms.SplitContainer> steuern Sie mit einer <xref:System.Windows.Forms.ListView> -Steuerelement über eine <xref:System.Windows.Forms.RichTextBox> Steuerelement. Diese <xref:System.Windows.Forms.SplitContainer> Steuerelemente ermöglichen unabhängigen Ändern der Größe der anderen Steuerelemente im Formular. Sie können die Verfahren in diesem Verfahren zum Erstellen benutzerdefinierter Benutzeroberflächen selbst anpassen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Erstellen Sie eine Outlook-Stil-Benutzeroberfläche zur Entwurfszeit  
  
1.  Erstellen Sie ein neues Windows-Anwendungsprojekt (**Datei** > **neu** > **Projekt** > **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular. In der **Eigenschaften** legen die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.TreeView> -Steuerelement aus der **Toolbox** um im linken Bereich von der <xref:System.Windows.Forms.SplitContainer> Steuerelement. In der **Eigenschaften** legen die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Left> durch Klicken auf den linken Bereich im Wert-Editor angezeigt, wenn auf der Dropdownpfeil geklickt wird.  
  
4.  Ziehen Sie ein weiteres <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox**; platzieren Sie es im rechten Bereich mit der <xref:System.Windows.Forms.SplitContainer> Kontrolle, die Sie dem Formular hinzugefügt. In der **Eigenschaften** legen die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill> und <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Eigenschaft <xref:System.Windows.Forms.Orientation.Horizontal>.  
  
5.  Ziehen Sie eine <xref:System.Windows.Forms.ListView> -Steuerelement aus der **Toolbox** in den oberen Bereich des zweiten <xref:System.Windows.Forms.SplitContainer> Kontrolle, die Sie dem Formular hinzugefügt. Legen Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A>-Eigenschaft des <xref:System.Windows.Forms.ListView>-Steuerelements auf <xref:System.Windows.Forms.DockStyle.Fill> fest.  
  
6.  Ziehen Sie eine <xref:System.Windows.Forms.RichTextBox> -Steuerelement aus der **Toolbox** in den unteren Bereich des zweiten <xref:System.Windows.Forms.SplitContainer> Steuerelement. Legen Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A>-Eigenschaft des <xref:System.Windows.Forms.RichTextBox>-Steuerelements auf <xref:System.Windows.Forms.DockStyle.Fill> fest.  
  
     Wenn Sie zum Ausführen der Anwendung F5 drücken, zeigt das Formular an diesem Punkt dreiteiligen Benutzeroberfläche, die von Microsoft Outlook ähnelt.  
  
    > [!NOTE]
    >  Wenn Sie den Mauszeiger über eines der Splitter innerhalb Einfügen der <xref:System.Windows.Forms.SplitContainer> -Steuerelemente, Sie können die Größe der internen Dimensionen.  
  
     An diesem Punkt haben Sie bei der Entwicklung eine anspruchsvolle Benutzeroberfläche konzipiert. Der nächste Schritt ist Programmieren der Anwendung selbst, z. B. durch das Verbinden der <xref:System.Windows.Forms.TreeView> Steuerelement und <xref:System.Windows.Forms.ListView> Steuerelemente in eine Art der Datenquelle. Weitere Informationen zum Verbinden von Steuerelementen an Daten finden Sie unter [Datenbindung und Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
