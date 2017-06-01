---
title: "&#220;bersicht &#252;ber die ContextMenu-Komponente (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ContextMenu"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kontextmenüs, ContextMenu-Komponente"
  - "ContextMenu-Komponente [Windows Forms], Informationen über die ContextMenu-Komponente"
  - "Kontextmenüs, ContextMenu-Komponente"
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# &#220;bersicht &#252;ber die ContextMenu-Komponente (Windows&#160;Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen das <xref:System.Windows.Forms.MainMenu>\-Steuerelement und das <xref:System.Windows.Forms.ContextMenu>\-Steuerelement früherer Versionen und erweitern dieses um Funktionen, jedoch werden <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> aus Gründen der Abwärtskompatibilität und, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Mit der <xref:System.Windows.Forms.ContextMenu>\-Komponente von Windows Forms können Sie Benutzern ein leicht zugängliches Kontextmenü mit häufig verwendeten Befehlen zur Verfügung stellen, die sich direkt auf das ausgewählte Objekt beziehen.  Bei den Elementen eines Kontextmenüs handelt es sich oft um eine Auswahl der Elemente aus den Hauptmenüs, die an anderen Stellen der Anwendung zu finden sind.  Im Normalfall kann ein Benutzer durch Klicken mit der rechten Maustaste auf ein Kontextmenü zugreifen.  In Windows Forms werden Kontextmenüs zu Steuerelementen zugeordnet.  
  
## Haupteigenschaften  
 Sie können ein Kontextmenü einem Steuerelement zuordnen, indem Sie die <xref:System.Windows.Forms.Control.ContextMenu%2A>\-Eigenschaft des Steuerelements auf die <xref:System.Windows.Forms.ContextMenu>\-Komponente festlegen.  Ein einzelnes Kontextmenü kann mehreren Steuerelementen zugeordnet werden. Jedes Steuerelement kann jedoch nur ein Kontextmenü besitzen.  
  
 Die wichtigste Eigenschaft der <xref:System.Windows.Forms.ContextMenu>\-Komponente ist die <xref:System.Windows.Forms.Menu.MenuItems%2A>\-Eigenschaft.  Sie können Menüelemente hinzufügen, indem Sie programmgesteuert <xref:System.Windows.Forms.MenuItem>\-Objekte erstellen und diese der <xref:System.Windows.Forms.Menu.MenuItemCollection> des Kontextmenüs hinzufügen.  Da die Elemente eines Kontextmenüs im Allgemeinen aus anderen Menüs stammen, werden Sie die Elemente wahrscheinlich meistens durch Kopieren einem Kontextmenü hinzufügen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ContextMenu>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>