---
title: 'Vorgehensweise: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: 2d7fb1dfbdfb7cf9be33fc8c9711b4fbdc3efc2d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880552"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Vorgehensweise: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.NotifyIcon> Komponente zeigt ein einzelnes Symbol im Statusbereich der Taskleiste. Wenn mehrere Symbole im Statusbereich anzeigen zu können, benötigen Sie mehrere <xref:System.Windows.Forms.NotifyIcon> Komponenten auf Ihrem Formular. Um das Symbol angezeigt, die für ein Steuerelement festzulegen, verwenden die <xref:System.Windows.Forms.NotifyIcon.Icon%2A> Eigenschaft. Sie können auch Code schreiben, der <xref:System.Windows.Forms.NotifyIcon.DoubleClick> -Ereignishandler so, dass etwas passiert, wenn der Benutzer das Symbol doppelklickt. Sie können z. B. ein Dialogfeld, das für den Benutzer so konfigurieren Sie den Hintergrundprozess, der durch das Symbol angezeigt vornehmen.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.NotifyIcon> Komponente wird für Benachrichtigungszwecke nur verwendet, um Benutzer, der eine Aktion oder ein Ereignis aufgetreten ist, oder es wurde eine Änderung in den Status eines. Sie sollten die Menüs, Symbolleisten und andere Elemente der Benutzeroberfläche für die standard-Interaktion mit Anwendungen verwenden.  
  
### <a name="to-set-the-icon"></a>Zum Festlegen des Symbols  
  
1.  Weisen Sie einen Wert, der <xref:System.Windows.Forms.NotifyIcon.Icon%2A> Eigenschaft. Der Wert muss vom Typ `System.Drawing.Icon` und kann über eine ICO-Datei geladen werden. Sie können die Datei mit dem Symbol angeben, im Code oder durch Klicken auf die Schaltfläche mit den Auslassungspunkten (![die Auslassungszeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben dem <xref:System.Windows.Forms.NotifyIcon.Icon%2A> -Eigenschaft in der **Eigenschaften** Fenster, und wählen Sie dann die Datei in die **öffnen** im angezeigten Dialogfeld.  
  
2. Legen Sie die <xref:System.Windows.Forms.NotifyIcon.Visible%2A> -Eigenschaft auf `true`fest.  
  
3. Legen Sie die <xref:System.Windows.Forms.NotifyIcon.Text%2A> Eigenschaft, um eine entsprechende QuickInfo-Zeichenfolge.  
  
     Das folgende Codebeispiel zeigt der Pfad festgelegt, für der Speicherort des Symbols ist die **eigene** Ordner. Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass dieser Ordner die meisten Computer, die das Windows-Betriebssystem ausgeführt wird enthält. Dieser Speicherort kann auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Das folgende Beispiel erfordert ein Formular mit einem <xref:System.Windows.Forms.NotifyIcon> Steuerelement bereits hinzugefügt. Darüber hinaus müssen eine Symboldatei, die mit dem Namen `Icon.ico`.  
  
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

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Vorgehensweise: Zuordnen eines Kontextmenüs mit einer NotifyIcon-Komponente in Windows Forms](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [NotifyIcon-Komponente](notifyicon-component-windows-forms.md)
- [Übersicht über die NotifyIcon-Komponente](notifyicon-component-overview-windows-forms.md)
