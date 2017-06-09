---
title: "Grundlagen f&#252;r das Entwickeln von Windows&#160;Forms-Steuerelementen | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Erstellen"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Ableitungstypen"
  - "Programmierungskonzepte, Windows Forms-Steuerelemente"
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Grundlagen f&#252;r das Entwickeln von Windows&#160;Forms-Steuerelementen
Ein Windows Forms\-Steuerelement ist eine Klasse, die direkt oder indirekt von <xref:System.Windows.Forms.Control?displayProperty=fullName> ableitet.  In der folgenden Liste werden Standardszenarien bei der Entwicklung von Steuerelementen für Windows Forms beschrieben:  
  
-   Kombinieren vorhandener Steuerelemente, um ein zusammengesetztes Steuerelement zu erstellen.  
  
     Zusammengesetzte Steuerelemente kapseln eine Benutzeroberfläche, die als Steuerelement wiederverwendet werden kann.  Ein zusammengesetztes Steuerelement besteht beispielsweise aus einem Textfeld und einer Schaltfläche zum Zurücksetzen.  Visuelle Designer bieten umfangreiche Unterstützung bei der Entwicklung zusammengesetzter Steuerelemente.  Um ein zusammengesetztes Steuerelement zu erstellen, leiten Sie von <xref:System.Windows.Forms.UserControl?displayProperty=fullName> ab.  Die <xref:System.Windows.Forms.UserControl>\-Basisklasse stellt Tastaturrouting für untergeordnete Steuerelemente zur Verfügung und ermöglicht untergeordneten Steuerelementen, in einer Gruppe zu arbeiten.  Weitere Informationen finden Sie unter [Entwickeln eines zusammengesetzten Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
-   Erweitern eines vorhandenen Steuerelements, um es anzupassen oder neue Funktionen hinzuzufügen.  
  
     Beispiele für erweiterte Steuerelemente sind Schaltflächen, deren Farben nicht geändert werden können, sowie Schaltflächen, die verfolgen können, wie häufig auf sie geklickt wurde.  Sie können jedes Windows Forms\-Steuerelement anpassen, indem Sie von ihm ableiten und Eigenschaften, Methoden und Ereignisse überschreiben oder hinzufügen.  
  
-   Erstellen eines Steuerelements, das vorhandene Steuerelemente nicht kombiniert oder erweitert.  
  
     In diesem Szenario leiten Sie das Steuerelement von der Basisklasse <xref:System.Windows.Forms.Control> ab.  Sie können Eigenschaften, Methoden und Ereignisse der Basisklasse hinzufügen oder überschreiben.  Informationen über die ersten Schritte finden Sie unter [Gewusst wie: Entwickeln eines einfachen Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 Die Basisklasse der Windows Forms\-Steuerelemente, <xref:System.Windows.Forms.Control>, stellt die Grundstruktur bereit, die für die visuelle Darstellung in Windows\-basierten Anwendungen auf Clientseite notwendig ist.  <xref:System.Windows.Forms.Control> macht ein Fensterhandle verfügbar, behandelt Meldungsrouting und stellt Maus\- und Tastaturereignisse sowie viele andere Benutzeroberflächenereignisse bereit.  Es bietet ein erweitertes Layout und verfügt über Eigenschaften, die für die visuelle Darstellung spezifisch sind, z. B. <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A> und viele andere.  Darüber hinaus werden Sicherheitsfunktionen, Threadunterstützung und Interoperabilität mit ActiveX\-Steuerelementen geboten.  Da die Basisklasse bereits einen Großteil der Infrastruktur zur Verfügung stellt, ist das Erstellen eigener Windows Forms\-Steuerelemente relativ einfach.  
  
## Siehe auch  
 [Gewusst wie: Entwickeln eines einfachen Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)   
 [Entwickeln eines zusammengesetzten Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)   
 [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)   
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)