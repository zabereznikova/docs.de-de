---
title: "Exemplarische Vorgehensweise: Kopieren und Einf&#252;gen eines ElementHost-Steuerelements in separate Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ElementHost-Steuerelement, Kopieren und Einfügen zur Entwurfszeit"
  - "Interoperabilität [WPF]"
  - "Windows Forms, Kopieren und Einfügen von Inhalt"
  - "WPF-Benutzersteuerelement, Hosten in Windows Forms"
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Exemplarische Vorgehensweise: Kopieren und Einf&#252;gen eines ElementHost-Steuerelements in separate Windows Forms
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie ein WPF\-Steuerelement \(Windows Presentation Foundation\) von einem Windows Form\-Objekt in ein anderes kopiert wird.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen des Projekts  
  
-   Kopieren eines WPF\-Steuerelements  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Erstellen des Projekts  
 Zunächst muss das Windows Forms\-Projekt erstellt werden.  
  
> [!NOTE]
>  Beim Hosten von WPF\-Inhalt werden nur C\#\- und Visual Basic\-Projekte unterstützt.  
  
#### So erstellen Sie das Projekt  
  
-   Erstellen Sie in Visual Basic oder Visual C\# ein neues Windows Forms\-Anwendungsprojekt mit dem Namen `CopyElementHost`.  
  
## Kopieren eines WPF\-Steuerelements  
 Nachdem Sie dem Projekt ein WPF\-Steuerelement hinzugefügt haben, können Sie es auf andere Formulare im Projekt kopieren.  
  
#### So kopieren Sie ein WPF\-Steuerelement  
  
1.  Fügen Sie der Projektmappe ein neues WPF\-<xref:System.Windows.Controls.UserControl>\-Projekt hinzu.  Verwenden Sie den Standardnamen \(`UserControl1.xaml`\) für den Steuerelementtyp.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF\-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Erstellen Sie das Projekt.  
  
3.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
4.  Ziehen Sie aus der **Toolbox** eine Instanz von `UserControl1` auf das Formular.  
  
     Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement namens `elementHost1` gehostet.  
  
5.  Während `elementHost1` ausgewählt ist, drücken Sie STRG \+ C, um das Steuerelement in die Zwischenablage zu kopieren.  
  
6.  Fügen Sie dem Projekt ein neues Windows Form\-Objekt hinzu.  Verwenden Sie den Standardnamen für den Formulartyp, `Form2`.  
  
7.  Während `Form2` im Windows Forms\-Designer geöffnet ist, drücken Sie STRG\+V, um eine Kopie von `elementHost1` auf dem Formular einzufügen.  
  
     Das kopierte Steuerelement erhält ebenfalls den Namen `elementHost1`, da es ein privates Feld der `Form2`\-Klasse ist.  Es gibt keinen Namenskonflikt mit `elementHost1` in der `Form1`\-Klasse.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Verwenden von WPF\-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)