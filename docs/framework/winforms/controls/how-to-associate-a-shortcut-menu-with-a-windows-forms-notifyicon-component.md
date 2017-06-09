---
title: "Gewusst wie: Zuordnen eines Kontextmen&#252;s zu einer NotifyIcon-Komponente in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kontextmenüs, Für Hintergrundprozesse"
  - "NotifyIcon-Komponente, Zuordnen von Kontextmenüs"
  - "Kontextmenüs, Für Hintergrundprozesse"
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Zuordnen eines Kontextmen&#252;s zu einer NotifyIcon-Komponente in Windows Forms
> [!NOTE]
>  <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen das <xref:System.Windows.Forms.MainMenu>\-Steuerelement und das <xref:System.Windows.Forms.ContextMenu>\-Steuerelement früherer Versionen und erweitern dieses um Funktionen, jedoch werden <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> aus Gründen der Abwärtskompatibilität und, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Die <xref:System.Windows.Forms.NotifyIcon>\-Komponente in Windows Forms zeigt ein Symbol im Statusbereich der Taskleiste an.  In der Regel können Sie in Anwendungen mit der rechten Maustaste auf das Symbol klicken, um Befehle an die durch das Symbol repräsentierte Anwendung zu senden.  Sie können diese Funktionalität den Anwendungen hinzufügen, indem Sie der <xref:System.Windows.Forms.NotifyIcon>\-Komponente eine <xref:System.Windows.Forms.ContextMenu>\-Komponente zuordnen.  
  
> [!NOTE]
>  Wenn die Anwendung beim Start minimiert und eine Instanz der <xref:System.Windows.Forms.NotifyIcon>\-Komponente in der Taskleiste angezeigt werden soll, legen Sie die <xref:System.Windows.Forms.Form.WindowState%2A>\-Eigenschaft des Hauptformulars auf <xref:System.Windows.Forms.FormWindowState> fest, und stellen Sie sicher, dass die <xref:System.Windows.Forms.NotifyIcon.Visible%2A>\-Eigenschaft der <xref:System.Windows.Forms.NotifyIcon>\-Komponente auf `true` festgelegt ist.  
  
### So ordnen Sie der der NotifyIcon\-Komponente zur Entwurfszeit ein Kontextmenü zu  
  
1.  Fügen Sie eine <xref:System.Windows.Forms.NotifyIcon>\-Komponente zum Formular hinzu, und legen Sie wichtige Eigenschaften fest, z. B. die <xref:System.Windows.Forms.NotifyIcon.Icon%2A>\-Eigenschaft und die <xref:System.Windows.Forms.NotifyIcon.Visible%2A>\-Eigenschaft.  
  
     Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2.  Fügen Sie dem Windows Form eine <xref:System.Windows.Forms.ContextMenu>\-Komponente hinzu.  
  
     Fügen Sie die Menüelemente zur Darstellung der Befehle, die zur Laufzeit verfügbar sein sollen, dem Kontextmenü hinzu.  Zu diesem Zeitpunkt empfiehlt es sich, den Menüelementen Menüerweiterungen wie Zugriffstasten hinzuzufügen.  
  
3.  Legen Sie die <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>\-Eigenschaft der<xref:System.Windows.Forms.NotifyIcon>\-Komponente auf das Kontextmenü fest, das Sie hinzugefügt haben.  
  
     Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü jedes Mal angezeigt, wenn in der Taskleiste auf das Symbol geklickt wird.  
  
### So ordnen Sie der NotifyIcon\-Komponente ein Kontextmenü zur Entwurfszeit programmgesteuert zu  
  
1.  Erstellen Sie eine Instanz der <xref:System.Windows.Forms.NotifyIcon>\-Klasse und eine <xref:System.Windows.Forms.ContextMenu>\-Klasse mit den Eigenschafteneinstellungen, die für die Anwendung erforderlich sind \(die <xref:System.Windows.Forms.NotifyIcon.Icon%2A>\-Eigenschaft und <xref:System.Windows.Forms.NotifyIcon.Visible%2A>\-Eigenschaft für die <xref:System.Windows.Forms.NotifyIcon>\-Komponente, Menüelemente für die <xref:System.Windows.Forms.ContextMenu>\-Komponente\).  
  
2.  Legen Sie die <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>\-Eigenschaft der<xref:System.Windows.Forms.NotifyIcon>\-Komponente auf das Kontextmenü fest, das Sie hinzugefügt haben.  
  
     Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü jedes Mal angezeigt, wenn in der Taskleiste auf das Symbol geklickt wird.  
  
    > [!NOTE]
    >  Mit dem folgenden Codebeispiel wird eine grundlegende Menüstruktur erstellt.  Sie müssen die Menüoptionen an die Optionen der von Ihnen entwickelten Anwendung anpassen.  Zusätzlich können Sie Code zum Behandeln der <xref:System.Windows.Forms.MenuItem.Click>\-Ereignisse für diese Menüelemente schreiben.  
  
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
>  Sie müssen den `notifyIcon1` und `contextMenu1,` initialisieren. Sie können dazu die folgenden Anweisungen in den Konstruktor des Formulars einfügen:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## Siehe auch  
 <xref:System.Windows.Forms.NotifyIcon>   
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>   
 [Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)   
 [NotifyIcon\-Komponente](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)   
 [Übersicht über die NotifyIcon\-Komponente](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)