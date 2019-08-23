---
title: 'Vorgehensweise: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: bf5602d0526fdd97f0cc14382339095a793f13c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922768"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Vorgehensweise: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms
> [!NOTE]
> Obwohl <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenuStrip> die-und- <xref:System.Windows.Forms.ContextMenu> Steuerelemente früherer Versionen ersetzen und Funktionen hinzu <xref:System.Windows.Forms.MainMenu> fügen <xref:System.Windows.Forms.ContextMenu> , werden Sie sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie auswählen.  
  
 Die <xref:System.Windows.Forms.NotifyIcon> Komponente zeigt ein Symbol im Status Benachrichtigungsbereich der Taskleiste an. Häufig können Sie mit der rechten Maustaste auf dieses Symbol klicken, um Befehle an die von ihm dargestellte Anwendung zu senden. Indem Sie der <xref:System.Windows.Forms.NotifyIcon> Komponente <xref:System.Windows.Forms.ContextMenu> eine Komponente zuordnen, können Sie diese Funktionalität ihren Anwendungen hinzufügen.  
  
> [!NOTE]
> Wenn Sie möchten, dass Ihre Anwendung beim Start minimiert wird, während eine Instanz der <xref:System.Windows.Forms.NotifyIcon> Komponente auf der Taskleiste angezeigt wird, legen Sie die <xref:System.Windows.Forms.Form.WindowState%2A> -Eigenschaft <xref:System.Windows.Forms.FormWindowState.Minimized> des Haupt Formulars auf <xref:System.Windows.Forms.NotifyIcon> fest, <xref:System.Windows.Forms.NotifyIcon.Visible%2A> und stellen Sie sicher, dass die-Eigenschaft der Komponente ist auf `true`festgelegt.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>So ordnen Sie der NotifyIcon-Komponente zur Entwurfszeit ein Kontextmenü zu  
  
1. Fügen Sie <xref:System.Windows.Forms.NotifyIcon> dem Formular eine Komponente hinzu, und legen Sie die wichtigen Eigenschaften wie die <xref:System.Windows.Forms.NotifyIcon.Icon%2A> - <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaft und die-Eigenschaft fest.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: Fügen Sie der Taskleiste mit der Windows Forms NotifyIcon-Komponente](app-icons-to-the-taskbar-with-wf-notifyicon.md)Anwendungs Symbole hinzu.  
  
2. Fügen Sie <xref:System.Windows.Forms.ContextMenu> Ihrem Windows Form eine Komponente hinzu.  
  
     Fügen Sie dem Kontextmenü Menü Elemente hinzu, die die Befehle darstellen, die zur Laufzeit verfügbar gemacht werden sollen. Dies ist auch ein guter Zeitpunkt, diesen Menü Elementen, z. b. Zugriffstasten, Menü Erweiterungen hinzuzufügen.  
  
3. Legen Sie <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> die-Eigenschaft <xref:System.Windows.Forms.NotifyIcon> der Komponente auf das Kontextmenü fest, das Sie hinzugefügt haben.  
  
     Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt, wenn auf das Symbol auf der Taskleiste geklickt wird.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>So ordnen Sie der NotifyIcon-Komponente Programm gesteuert ein Kontextmenü zu  
  
1. Erstellen Sie eine Instanz der <xref:System.Windows.Forms.NotifyIcon> -Klasse und <xref:System.Windows.Forms.ContextMenu> eine-Klasse mit den Eigenschafts Einstellungen, die für die<xref:System.Windows.Forms.NotifyIcon.Icon%2A> Anwendung <xref:System.Windows.Forms.NotifyIcon.Visible%2A> erforderlich sind ( <xref:System.Windows.Forms.NotifyIcon> und Eigenschaften für die Komponente, <xref:System.Windows.Forms.ContextMenu> Menü Elemente für das Komponente).  
  
2. Legen Sie <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> die-Eigenschaft <xref:System.Windows.Forms.NotifyIcon> der Komponente auf das Kontextmenü fest, das Sie hinzugefügt haben.  
  
     Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt, wenn auf das Symbol auf der Taskleiste geklickt wird.  
  
    > [!NOTE]
    > Im folgenden Codebeispiel wird eine einfache Menüstruktur erstellt. Sie müssen die Menü Optionen für die Anwendung anpassen, die Sie entwickeln. Außerdem sollten Sie Code schreiben, um die <xref:System.Windows.Forms.MenuItem.Click> Ereignisse für diese Menü Elemente zu behandeln.  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _   
          (System.Environment.GetFolderPath _   
          (System.Environment.SpecialFolder.Personal)  _   
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
> Sie müssen initialisieren `notifyIcon1` und `contextMenu1,` ausführen, indem Sie die folgenden Anweisungen in den Konstruktor Ihres Formulars einschließen:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Vorgehensweise: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der Windows Forms NotifyIcon-Komponente](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [NotifyIcon-Komponente](notifyicon-component-windows-forms.md)
- [Übersicht über die NotifyIcon-Komponente](notifyicon-component-overview-windows-forms.md)
