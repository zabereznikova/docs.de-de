---
title: "Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d795df8e8b514345632491fd6afdd618c2f18ec2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms
Windows Forms <xref:System.Windows.Forms.NotifyIcon> Komponente zeigt ein einzelnes Symbol im Statusbereich der Taskleiste. Um mehrere Symbole im Statusbereich anzuzeigen, benötigen Sie mehrere <xref:System.Windows.Forms.NotifyIcon> Komponenten auf dem Formular. Um das Symbol angezeigt, die für ein Steuerelement festzulegen, verwenden die <xref:System.Windows.Forms.NotifyIcon.Icon%2A> Eigenschaft. Sie können auch Code schreiben, der <xref:System.Windows.Forms.NotifyIcon.DoubleClick> -Ereignishandler so, dass etwas passiert, wenn der Benutzer auf das Symbol doppelklickt. Beispielsweise können Sie ein Dialogfeld für den Benutzer so konfigurieren Sie die im Hintergrund ausgeführten Prozess, dargestellt durch das Symbol angezeigt vornehmen.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.NotifyIcon> Komponente nur aus Gründen der Benachrichtigung verwendet wird, um Benutzer darauf aufmerksam, die eine Aktion oder ein Ereignis aufgetreten ist oder eine Änderung des Status von irgendeine stattgefunden hat. Sie sollten Menüs, Symbolleisten und andere Elemente der Benutzeroberfläche für die standard-Interaktion mit Anwendungen verwenden.  
  
### <a name="to-set-the-icon"></a>Das Symbol "festlegen  
  
1.  Weisen Sie einen Wert an die <xref:System.Windows.Forms.NotifyIcon.Icon%2A> Eigenschaft. Der Wert muss vom Typ `System.Drawing.Icon` und kann aus einer ICO‑Datei geladen werden. Sie können die Symboldatei angeben, im Code oder durch Klicken auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben der <xref:System.Windows.Forms.NotifyIcon.Icon%2A> Eigenschaft in der  **Eigenschaften** Fenster, und wählen Sie dann die Datei in die **öffnen** im daraufhin geöffneten Dialogfeld.  
  
2.  Legen Sie die <xref:System.Windows.Forms.NotifyIcon.Visible%2A>-Eigenschaft auf `true` fest.  
  
3.  Legen Sie die <xref:System.Windows.Forms.NotifyIcon.Text%2A> Eigenschaft, um eine entsprechende QuickInfo-Zeichenfolge.  
  
     Im folgenden Codebeispiel legen der Pfad für der Speicherort des Symbols wird die **eigene** Ordner. Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass dieser Ordner die meisten Computer das Windows-Betriebssystem ausgeführt wird enthält. Dieser Speicherort kann auch Benutzer mit minimalen sicher auf die Anwendung auszuführen. Das folgende Beispiel erfordert ein Formular mit einem <xref:System.Windows.Forms.NotifyIcon> Steuerelement bereits hinzugefügt. Darüber hinaus müssen eine Symboldatei mit dem Namen `Icon.ico`.  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [Gewusst wie: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [NotifyIcon-Komponente](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [Übersicht über die NotifyIcon-Komponente](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
