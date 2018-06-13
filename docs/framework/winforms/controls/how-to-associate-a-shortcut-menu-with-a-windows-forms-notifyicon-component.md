---
title: 'Gewusst wie: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms'
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
ms.openlocfilehash: c0371dfb30c70bd2c4d98362abc7dc06926a5e88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527881"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Gewusst wie: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms
> [!NOTE]
>  Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzt und funktionell die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente von früheren Versionen <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> für Abwärtskompatibilität und für zukünftige Verwendung beibehalten werden, falls gewünscht.  
  
 Die <xref:System.Windows.Forms.NotifyIcon> Komponente zeigt ein Symbol im Statusbereich der Taskleiste. Im Allgemeinen können mit Anwendungen mit der rechten Maustaste dieses Symbol, um Befehle an die Anwendung zu senden, den er darstellt. Durch das Zuordnen einer <xref:System.Windows.Forms.ContextMenu> Komponente mit der <xref:System.Windows.Forms.NotifyIcon> -Komponente, Sie können diese Funktionalität hinzufügen, um Ihre Anwendungen.  
  
> [!NOTE]
>  Wenn Sie wünschen, dass Ihre Anwendung beim Start minimiert werden, beim Anzeigen einer Instanz von der <xref:System.Windows.Forms.NotifyIcon> Komponentensatz in der Taskleiste des Hauptformulars <xref:System.Windows.Forms.Form.WindowState%2A> Eigenschaft <xref:System.Windows.Forms.FormWindowState.Minimized> und achten Sie darauf die <xref:System.Windows.Forms.NotifyIcon> Komponente <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaft -Wert von `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Zuordnen ein Kontextmenüs mit der NotifyIcon-Komponente zur Entwurfszeit  
  
1.  Hinzufügen einer <xref:System.Windows.Forms.NotifyIcon> -Komponente in Ihr Formular, und legen Sie die wichtigen Eigenschaften wie z. B. die <xref:System.Windows.Forms.NotifyIcon.Icon%2A> und <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaften.  
  
     Weitere Informationen finden Sie unter [wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2.  Hinzufügen einer <xref:System.Windows.Forms.ContextMenu> Komponente zu einem Windows Form.  
  
     Hinzufügen von Menüelementen im Kontextmenü Darstellung der Befehle, die Sie zur Laufzeit verfügbar machen möchten. Dies ist auch ein guter Zeitpunkt, Menü-Erweiterungen auf diese Menüelemente, z. B. Zugriffstasten hinzuzufügen.  
  
3.  Festlegen der <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> Eigenschaft von der <xref:System.Windows.Forms.NotifyIcon> -Komponente auf das Kontextmenü, das Sie hinzugefügt.  
  
     Diese Eigenschaft festgelegt ist wird das Kontextmenü angezeigt werden, beim Klicken auf das Symbol auf der Taskleiste.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Um ein Kontextmenü mit der NotifyIcon-Komponente programmgesteuert zu verknüpfen  
  
1.  Erstellen Sie eine Instanz von der <xref:System.Windows.Forms.NotifyIcon> Klasse und ein <xref:System.Windows.Forms.ContextMenu> -Klasse, mit die Einstellungen der Eigenschaften für die Anwendung erforderlich sind (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> und <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaften für die <xref:System.Windows.Forms.NotifyIcon> -Komponente, die Menüelemente für die die <xref:System.Windows.Forms.ContextMenu> die Komponente).  
  
2.  Festlegen der <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> Eigenschaft von der <xref:System.Windows.Forms.NotifyIcon> -Komponente auf das Kontextmenü, das Sie hinzugefügt.  
  
     Diese Eigenschaft festgelegt ist wird das Kontextmenü angezeigt werden, beim Klicken auf das Symbol auf der Taskleiste.  
  
    > [!NOTE]
    >  Im folgenden Codebeispiel wird eine grundlegende Menüstruktur erstellt. Sie müssen an die Menüoptionen, mit denen die Anwendung anpassen, die Sie entwickeln. Darüber hinaus sollten so schreiben Sie Code zum Behandeln der <xref:System.Windows.Forms.MenuItem.Click> Ereignisse für diese Menüelemente.  
  
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
>  Sie müssen initialisieren `notifyIcon1` und `contextMenu1,` wozu Sie z. B. die folgenden Anweisungen im Konstruktor des Formulars verwenden können:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)  
 [NotifyIcon-Komponente](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [Übersicht über die NotifyIcon-Komponente](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
