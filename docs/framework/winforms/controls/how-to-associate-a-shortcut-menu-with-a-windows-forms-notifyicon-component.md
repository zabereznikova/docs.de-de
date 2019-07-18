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
ms.openlocfilehash: f2a086cc25eb6996b2643742a887bccf481916d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010942"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Vorgehensweise: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms
> [!NOTE]
>  Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen und Erweitern der Funktionalität für die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente aus früheren Versionen, <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie auswählen.  
  
 Die <xref:System.Windows.Forms.NotifyIcon> Komponente zeigt ein Symbol im Statusbereich der Taskleiste. In der Regel können Anwendungen mit der rechten Maustaste dieses Symbol, um Befehle an die Anwendung zu senden, den es darstellt. Durch Zuordnen einer <xref:System.Windows.Forms.ContextMenu> Komponente mit dem die <xref:System.Windows.Forms.NotifyIcon> Komponente ist, können Sie diese Funktionalität zu Ihren Anwendungen hinzufügen.  
  
> [!NOTE]
>  Wenn Sie Ihre Anwendung beim Start minimiert werden, beim Anzeigen einer Instanz von möchten der <xref:System.Windows.Forms.NotifyIcon> Komponentensatz in der Taskleiste des Hauptformulars <xref:System.Windows.Forms.Form.WindowState%2A> Eigenschaft, um <xref:System.Windows.Forms.FormWindowState.Minimized> und achten Sie darauf die <xref:System.Windows.Forms.NotifyIcon> Komponente <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaft nastaven NA hodnotu `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Zum Zuordnen eines Kontextmenüs mit der NotifyIcon-Komponente zur Entwurfszeit  
  
1. Hinzufügen einer <xref:System.Windows.Forms.NotifyIcon> -Komponente zum Formular, und legen Sie die wichtigen Eigenschaften, z. B. die <xref:System.Windows.Forms.NotifyIcon.Icon%2A> und <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaften.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der Windows Forms NotifyIcon-Komponente](app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2. Hinzufügen einer <xref:System.Windows.Forms.ContextMenu> Ihrem Windows-Formular.  
  
     Hinzufügen von Menüelementen, die im Kontextmenü die Befehle, die zur Laufzeit zur Verfügung stellen möchten darstellt. Dies ist auch ein guter Zeitpunkt, zu diesen Menüelementen wie den Zugriffsschlüssel im Menü-Erweiterungen hinzugefügt.  
  
3. Legen Sie die <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> Eigenschaft der <xref:System.Windows.Forms.NotifyIcon> Komponente dem Kontextmenü aus, die Sie hinzugefügt.  
  
     Diese Eigenschaft festgelegt ist wird das Kontextmenü angezeigt, wenn das Symbol auf der Taskleiste geklickt wird.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Um programmgesteuert Zuordnen eines Kontextmenüs mit der NotifyIcon-Komponente  
  
1. Erstellen Sie eine Instanz von der <xref:System.Windows.Forms.NotifyIcon> Klasse und ein <xref:System.Windows.Forms.ContextMenu> Klasse, dabei werden alle eigenschafteneinstellungen für die Anwendung erforderlich sind (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> und <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaften für die <xref:System.Windows.Forms.NotifyIcon> -Komponente, die Menüelemente für die <xref:System.Windows.Forms.ContextMenu> die Komponente).  
  
2. Legen Sie die <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> Eigenschaft der <xref:System.Windows.Forms.NotifyIcon> Komponente dem Kontextmenü aus, die Sie hinzugefügt.  
  
     Diese Eigenschaft festgelegt ist wird das Kontextmenü angezeigt, wenn das Symbol auf der Taskleiste geklickt wird.  
  
    > [!NOTE]
    >  Im folgenden Codebeispiel wird eine grundlegende Menüstruktur erstellt. Sie müssen an die Menüoptionen, mit denen die Anwendung anpassen, die Sie entwickeln. Darüber hinaus sollten Sie zum Schreiben von Code zum Behandeln von der <xref:System.Windows.Forms.MenuItem.Click> Ereignisse für diese Menüelemente.  
  
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
>  Sie müssen initialisieren `notifyIcon1` und `contextMenu1,` Dies können Sie dazu die folgenden Anweisungen im Konstruktor des Formulars:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Vorgehensweise: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [NotifyIcon-Komponente](notifyicon-component-windows-forms.md)
- [Übersicht über die NotifyIcon-Komponente](notifyicon-component-overview-windows-forms.md)
