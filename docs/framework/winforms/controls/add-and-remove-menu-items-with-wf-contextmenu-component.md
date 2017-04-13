---
title: "Gewusst wie: Hinzuf&#252;gen und Entfernen von Men&#252;elementen mit der ContextMenu-Komponente von Windows&#160;Forms | Microsoft Docs"
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
  - "Kontextmenüs, Hinzufügen von Elementen"
  - "Kontextmenüs, Beispiele"
  - "Kontextmenüs, Entfernen von Elementen"
  - "ContextMenu-Komponente [Windows Forms], Hinzufügen von Elementen"
  - "ContextMenu-Komponente [Windows Forms], Entfernen von Elementen"
  - "Beispiele [Windows Forms], Kontextmenüs"
  - "Kontextmenüs, Hinzufügen von Elementen"
  - "Kontextmenüs, Beispiele"
  - "Kontextmenüs, Entfernen von Elementen"
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Hinzuf&#252;gen und Entfernen von Men&#252;elementen mit der ContextMenu-Komponente von Windows&#160;Forms
Erläutert das Hinzufügen und Entfernen von Kontextmenüelementen in Windows Forms.  
  
 Die <xref:System.Windows.Forms.ContextMenu>\-Komponente von Windows Forms stellt ein Menü mit häufig verwendeten Befehlen bereit, die sich direkt auf das ausgewählte Objekt beziehen.  Sie können dem Kontextmenü Elemente hinzufügen, indem Sie <xref:System.Windows.Forms.MenuItem>\-Objekte der <xref:System.Windows.Forms.Menu.MenuItems%2A>\-Auflistung hinzufügen.  
  
 Sie können Elemente dauerhaft aus einem Kontextmenü entfernen. Zur Laufzeit empfiehlt es sich jedoch, die Elemente stattdessen auszublenden oder zu deaktivieren.  
  
> [!IMPORTANT]
>  <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen das <xref:System.Windows.Forms.MainMenu>\-Steuerelement und das <xref:System.Windows.Forms.ContextMenu>\-Steuerelement früherer Versionen und erweitern dieses um Funktionen, jedoch werden <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> aus Gründen der Abwärtskompatibilität und, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
### So entfernen Sie Elemente aus einem Kontextmenü  
  
1.  Verwenden Sie zum Entfernen eines bestimmten Menüelements die <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A>\-Methode oder die <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A>\-Methode der <xref:System.Windows.Forms.Menu.MenuItems%2A>\-Auflistung der <xref:System.Windows.Forms.ContextMenu>\-Komponente.  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     \- oder \-  
  
2.  Verwenden Sie zum Entfernen aller Menüelemente die `Clear`\-Methode der `MenuItems`\-Auflistung der <xref:System.Windows.Forms.ContextMenu>\-Komponente.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ContextMenu>   
 [ContextMenu\-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)   
 [Übersicht über die ContextMenu\-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)