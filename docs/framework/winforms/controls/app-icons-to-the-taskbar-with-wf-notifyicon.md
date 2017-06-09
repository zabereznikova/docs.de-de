---
title: "Gewusst wie: Hinzuf&#252;gen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TrayIcon"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Symbole, Hinzufügen zur Taskleiste"
  - "NotifyIcon-Komponente"
  - "Statusbereichsymbole"
  - "Taskleiste, Hinzufügen von Symbolen"
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Hinzuf&#252;gen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows&#160;Forms
Die <xref:System.Windows.Forms.NotifyIcon>\-Komponente in Windows Forms zeigt ein einzelnes Symbol im Statusbereich der Taskleiste an.  Wenn Sie im Statusbereich mehrere Symbole anzeigen möchten, muss Ihr Formular mehrere <xref:System.Windows.Forms.NotifyIcon>\-Komponenten enthalten.  Verwenden Sie zum Festlegen des für ein Steuerelement angezeigten Symbols die <xref:System.Windows.Forms.NotifyIcon.Icon%2A>\-Eigenschaft.  Darüber hinaus können Sie in den <xref:System.Windows.Forms.NotifyIcon.DoubleClick>\-Ereignishandler Code schreiben, um beim Doppelklicken des Symbols den gewünschten Vorgang auszulösen.  Beispielsweise könnten Sie ein Dialogfeld anzeigen lassen, in dem die Benutzer den Hintergrundprozess, für den das Symbol steht, konfigurieren können.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.NotifyIcon>\-Komponente wird nur zu Benachrichtigungszwecken verwendet, um Benutzer darauf hinzuweisen, dass eine Aktion ausgeführt wurde bzw. ein Ereignis aufgetreten ist oder sich der Status in irgendeiner Weise geändert hat.  Es empfiehlt sich, Menüs, Symbolleisten und andere Elemente der Benutzeroberfläche für Standardinteraktionen mit Anwendungen zu verwenden.  
  
### So stellen Sie das Symbol ein  
  
1.  Weisen Sie der <xref:System.Windows.Forms.NotifyIcon.Icon%2A>\-Eigenschaft einen Wert zu.  Dieser Wert muss vom Typ `System.Drawing.Icon` sein und kann aus einer ICO\-Datei geladen werden.  Sie können die Symboldatei entweder im Code angeben oder durch Klicken der Schaltfläche zum Durchsuchen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) neben der <xref:System.Windows.Forms.NotifyIcon.Icon%2A>\-Eigenschaft im **Eigenschaftenfenster** und anschließendes Auswählen der Datei im Dialogfeld **Öffnen**.  
  
2.  Legen Sie die <xref:System.Windows.Forms.NotifyIcon.Visible%2A>\-Eigenschaft auf `true` fest.  
  
3.  Legen Sie für die <xref:System.Windows.Forms.NotifyIcon.Text%2A>\-Eigenschaft eine geeignete QuickInfo\-Zeichenfolge fest.  
  
     Im folgenden Codebeispiel wurde als Speicherort für das Symbol der Ordner **Eigene Dateien** festgelegt.  Dieser Speicherort wird verwendet, weil vorausgesetzt werden kann, dass die meisten Computer mit Windows als Betriebssystem über einen Ordner mit diesem Namen verfügen.  Dieser Speicherort ermöglicht auch Benutzern mit minimalen Systemzugriffsberechtigungen, die Anwendung sicher auszuführen.  Im folgenden Beispiel wird davon ausgegangen, dass einem Formular bereits ein <xref:System.Windows.Forms.NotifyIcon>\-Steuerelement hinzugefügt wurde.  Zudem ist eine Symboldatei mit dem Namen `Icon.ico` erforderlich.  
  
     \[Visual Basic\]  
  
    ```  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
  
    ```  
  
     \[C\#\]  
  
    ```  
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
  
     \[cpp\]  
  
    ```  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.NotifyIcon>   
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>   
 [Gewusst wie: Zuordnen eines Kontextmenüs zu einer NotifyIcon\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)   
 [NotifyIcon\-Komponente](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)   
 [Übersicht über die NotifyIcon\-Komponente](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)