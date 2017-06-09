---
title: "Entwickeln eines zusammengesetzten Windows&#160;Forms-Steuerelements | Microsoft Docs"
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
  - "Zusammengesetzte Steuerelemente"
  - "Zusammengesetzte Steuerelemente, Windows Forms"
  - "Steuerelemente [Windows Forms], Zusammengesetzt"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Zusammengesetzte Steuerelemente"
  - "UserControl-Klasse"
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Entwickeln eines zusammengesetzten Windows&#160;Forms-Steuerelements
Sie können ein zusammengesetztes Windows Forms\-Steuerelement entwickeln, indem Sie andere Windows Forms\-Steuerelemente kombinieren.  Zusammengesetzte Steuerelemente, die von [System.Windows.Forms.UserControl](frlrfSystemWebUIUserControlClassTopic) abgeleitet werden, werden als Benutzersteuerelemente bezeichnet.  Die Basisklasse, <xref:System.Windows.Forms.UserControl>, ermöglicht Tastaturrouting für die untergeordneten Steuerelemente und stellt damit sicher, dass untergeordnete Steuerelemente den Fokus erhalten können.  Ein Beispiel für ein Benutzersteuerelement finden Sie im <xref:System.Windows.Forms.UserControl>\-Beispiel unter [Gewusst wie: Anwenden von Attributen auf Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
 Der Windows Forms\-Designer in [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] stellt umfassende Entwurfszeitunterstützung für die Erstellung von Benutzersteuerelementen bereit.  
  
-   [Gewusst wie: Anzeigen eines Steuerelements im Dialogfeld "Toolboxelemente auswählen"](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Vererben von einem Windows Forms\-Steuerelement mit Visual C\#](http://msdn.microsoft.com/en-us/library/5h0k2e6x\(v=vs.110\))  
  
-   [Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [Gewusst wie: Erben von vorhandenen Windows Forms\-Steuerelementen](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms\-Steuerelementen zur Entwurfszeit](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [Gewusst wie: Erben von der Control\-Klasse](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))  
  
-   [Gewusst wie: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [Gewusst wie: Erben von der UserControl\-Klasse](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [Gewusst wie: Erstellen von Steuerelementen für Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [Gewusst wie: Erstellen von zusammengesetzten Steuerelementen](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C\#](http://msdn.microsoft.com/de-de/library/a6h7e207\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das Entwurfszeitfeatures nutzt](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das Entwurfszeitfeatures nutzt](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## Siehe auch  
 [Gewusst wie: Anwenden von Attributen auf Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)   
 [Entwickeln benutzerdefinierter Windows Forms\-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)