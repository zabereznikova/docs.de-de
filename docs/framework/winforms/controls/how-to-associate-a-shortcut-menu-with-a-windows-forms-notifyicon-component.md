---
title: Zuordnen eines Shortcut-Menüs zur NotifyIcon-Komponente
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
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182254"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Gewusst wie: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms
> [!NOTE]
> Obwohl <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> und ersetzen und <xref:System.Windows.Forms.MainMenu> fügen <xref:System.Windows.Forms.ContextMenu> Sie Funktionen <xref:System.Windows.Forms.MainMenu> zu <xref:System.Windows.Forms.ContextMenu> den und Steuerelementen der früheren Versionen, und werden für die Abwärtskompatibilität und zukünftige Verwendung beibehalten, wenn Sie wählen.  
  
 Die <xref:System.Windows.Forms.NotifyIcon> Komponente zeigt ein Symbol im Statusbenachrichtigungsbereich der Taskleiste an. In der Regel können Sie mit Anwendungen mit der rechten Maustaste auf dieses Symbol klicken, um Befehle an die von ihr vertretene Anwendung zu senden. Durch Zuordnen einer <xref:System.Windows.Forms.ContextMenu> Komponente zu <xref:System.Windows.Forms.NotifyIcon> der Komponente können Sie diese Funktionalität zu Ihren Anwendungen hinzufügen.  
  
> [!NOTE]
> Wenn Sie möchten, dass Ihre Anwendung beim Start <xref:System.Windows.Forms.NotifyIcon> minimiert wird, während eine Instanz der <xref:System.Windows.Forms.Form.WindowState%2A> Komponente <xref:System.Windows.Forms.FormWindowState.Minimized> in der <xref:System.Windows.Forms.NotifyIcon> Taskleiste <xref:System.Windows.Forms.NotifyIcon.Visible%2A> angezeigt wird, legen Sie die Eigenschaft des Hauptformulars auf , und stellen Sie sicher, dass die Eigenschaft der Komponente auf `true`festgelegt ist.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>So ordnen Sie der NotifyIcon-Komponente zur Entwurfszeit ein Kontextmenü zu  
  
1. Fügen <xref:System.Windows.Forms.NotifyIcon> Sie dem Formular eine Komponente hinzu, und <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> legen Sie die wichtigen Eigenschaften fest, z. B. die und eigenschaften.  
  
     Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der Windows Forms NotifyIcon-Komponente](app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2. Fügen <xref:System.Windows.Forms.ContextMenu> Sie Ihrem Windows-Formular eine Komponente hinzu.  
  
     Fügen Sie dem Kontextmenü Menüelemente hinzu, die die Befehle darstellen, die Sie zur Laufzeit verfügbar machen möchten. Dies ist auch ein guter Zeitpunkt, um Menüverbesserungen zu diesen Menüelementen hinzuzufügen, z. B. Zugriffstasten.  
  
3. Legen <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> Sie die <xref:System.Windows.Forms.NotifyIcon> Eigenschaft der Komponente auf das von Ihnen hinzugefügte Kontextmenü fest.  
  
     Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt, wenn auf das Symbol auf der Taskleiste geklickt wird.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>So ordnen Sie der NotifyIcon-Komponente programmgesteuert ein Kontextmenü zu  
  
1. Erstellen Sie eine <xref:System.Windows.Forms.NotifyIcon> Instanz <xref:System.Windows.Forms.ContextMenu> der Klasse und eine Klasse, mit<xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> allen Eigenschafteneinstellungen, die für die Anwendung erforderlich sind (und Eigenschaften für die <xref:System.Windows.Forms.NotifyIcon> Komponente, Menüelemente für die <xref:System.Windows.Forms.ContextMenu> Komponente).  
  
2. Legen <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> Sie die <xref:System.Windows.Forms.NotifyIcon> Eigenschaft der Komponente auf das von Ihnen hinzugefügte Kontextmenü fest.  
  
     Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt, wenn auf das Symbol auf der Taskleiste geklickt wird.  
  
    > [!NOTE]
    > Im folgenden Codebeispiel wird eine grundlegende Menüstruktur erstellt. Sie müssen die Menüoptionen an die Menüoptionen anpassen, die zu der Anwendung passen, die Sie entwickeln. Darüber hinaus sollten Sie Code schreiben, um die <xref:System.Windows.Forms.MenuItem.Click> Ereignisse für diese Menüelemente zu behandeln.  
  
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
> Sie müssen `notifyIcon1` initialisieren und `contextMenu1,` können die folgenden Anweisungen in den Konstruktor Ihres Formulars einbeziehen:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [NotifyIcon-Komponente](notifyicon-component-windows-forms.md)
- [Übersicht über die NotifyIcon-Komponente](notifyicon-component-overview-windows-forms.md)
