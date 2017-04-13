---
title: "Exemplarische Vorgehensweise: Automatisches F&#252;llen der Toolbox mit benutzerdefinierten Komponenten | Microsoft Docs"
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
  - "Benutzerdefinierte Komponenten, Hinzufügen zur Toolbox"
  - "IToolboxService-Schnittstelle"
  - "Toolbox [Windows Forms], Auffüllen"
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Exemplarische Vorgehensweise: Automatisches F&#252;llen der Toolbox mit benutzerdefinierten Komponenten
Wenn die Komponenten durch ein Projekt in der momentan geöffneten Projektmappe definiert sind, werden sie automatisch in der **Toolbox** angezeigt, ohne dass hierfür eine Aktion erforderlich ist.  Sie können die **Toolbox** auch manuell mit den benutzerdefinierten Komponenten füllen, indem Sie das [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/de-de/bd07835f-18a8-433e-bccc-7141f65263bb) verwenden. Die **Toolbox** berücksichtigt allerdings Elemente in den Buildausgaben der Projektmappe, einschließlich folgender Merkmale:  
  
-   Implementiert <xref:System.ComponentModel.IComponent>;  
  
-   Hat <xref:System.ComponentModel.ToolboxItemAttribute> nicht auf `false` festgelegt;  
  
-   Hat <xref:System.ComponentModel.DesignTimeVisibleAttribute> nicht auf `false` festgelegt.  
  
> [!NOTE]
>  Die **Toolbox** folgt keinen Verweisketten, d. h., sie zeigt keine Elemente an, die nicht von einem Projekt in der Projektmappe erstellt wurden.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie eine benutzerdefinierte Komponente automatisch in der **Toolbox** angezeigt wird, sobald die Komponente erstellt wird.  In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms\-Projekts  
  
-   Erstellen einer benutzerdefinierten Komponente  
  
-   Erstellen einer Instanz einer benutzerdefinierten Komponente  
  
-   Entladen und erneutes Laden einer benutzerdefinierten Komponente  
  
 Anschließend werden Sie sehen, dass die **Toolbox** mit einer von Ihnen erstellten Komponente gefüllt ist.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Erstellen des Projekts  
 Zunächst wird das Projekt erstellt und das Formular eingerichtet.  
  
#### So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows\-basiertes Anwendungsprojekt mit dem Namen `ToolboxExample`.  
  
     Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Fügen Sie dem Projekt eine neue Komponente hinzu.  Nennen Sie sie `DemoComponent`.  
  
     Weitere Informationen finden Sie unter [NIB:How to: Add New Project Items](http://msdn.microsoft.com/de-de/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  
  
3.  Erstellen Sie das Projekt.  
  
4.  Klicken Sie im Menü **Extras** auf das Element **Optionen**.  Klicken Sie unter dem Element **Windows Forms\-Designer** auf **Allgemein**, und vergewissern Sie sich, dass die **AutoToolboxPopulate**\-Option auf **True** festgelegt ist.  
  
## Erstellen einer Instanz einer benutzerdefinierten Komponente  
 Der nächste Schritt besteht darin, auf dem Formular eine Instanz der benutzerdefinierten Komponente zu erstellen.  Da die neue Komponente in der **Toolbox** automatisch berücksichtigt wird, ist dieser Schritt ebenso einfach wie das Erstellen einer anderen Komponente oder eines Steuerelements.  
  
#### So erstellen Sie eine Instanz einer benutzerdefinierten Komponente  
  
1.  Öffnen Sie das Formular des Projekts im **Windows Forms\-Designer**.  
  
2.  Klicken Sie in der **Toolbox** auf die neue Registerkarte **ToolboxExample\-Komponenten**.  
  
     Sobald Sie auf die Registerkarte klicken, sehen Sie **DemoComponent**.  
  
    > [!NOTE]
    >  Aus Leistungsgründen zeigen Komponenten im automatisch gefüllten Bereich der **Toolbox** keine benutzerdefinierten Bitmaps an, und das <xref:System.Drawing.ToolboxBitmapAttribute> wird nicht unterstützt.  Um in der **Toolbox** ein Symbol für eine benutzerdefinierte Komponente anzuzeigen, laden Sie die Komponente mithilfe des Dialogfelds **Toolboxelemente auswählen**.  
  
3.  Ziehen Sie die Komponente auf das Formular.  
  
     Eine Instanz der Komponente wird erstellt und der **Komponentenleiste** hinzugefügt.  
  
## Entladen und erneutes Laden einer benutzerdefinierten Komponente  
 Die **Toolbox** berücksichtigt die Komponenten in jedem geladenen Projekt. Wenn ein Projekt entladen wird, entfernt sie Verweise auf die Projektkomponenten.  
  
#### So testen Sie die Auswirkung des Entladens und erneuten Ladens von Komponenten auf die Toolbox  
  
1.  Entladen Sie das Projekt aus der Projektmappe.  
  
     Weitere Informationen über das Entladen von Projekten finden Sie unter [NIB:How to: Unload and Reload Projects](http://msdn.microsoft.com/de-de/abc0155b-8fcb-4ffc-95b6-698518a7100b).  Wenn Sie aufgefordert werden zu speichern, wählen Sie **Ja** aus.  
  
2.  Fügen Sie der Projektmappe ein neues Projekt vom Typ **Windows\-Anwendung** hinzu.  Öffnen Sie das Formular im **Designer**.  
  
     Die Registerkarte **ToolboxExample\-Komponenten** aus dem vorherigen Projekt ist nicht mehr verfügbar.  
  
3.  Laden Sie das `ToolboxExample`\-Projekt erneut.  
  
     Die Registerkarte **ToolboxExample\-Komponenten** wird wieder angezeigt.  
  
## Nächste Schritte  
 Diese exemplarische Vorgehensweise veranschaulicht, dass die **Toolbox** nicht nur die Komponenten eines Projekts berücksichtigt, sondern auch die  Steuerelemente.  Experimentieren Sie mit den benutzerdefinierten Steuerelementen, indem Sie Steuerelementprojekte der Projektmappe hinzufügen und daraus entfernen.  
  
## Siehe auch  
 [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/de-de/8dd170af-72f0-4212-b04b-034ceee92834)   
 [How to: Manipulate Toolbox Tabs](http://msdn.microsoft.com/de-de/21285050-cadd-455a-b1f5-a2289a89c4db)   
 [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/de-de/bd07835f-18a8-433e-bccc-7141f65263bb)   
 [Einfügen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)