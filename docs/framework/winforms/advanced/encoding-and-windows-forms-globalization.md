---
title: "Codierung und die Globalisierung von Windows&#160;Forms | Microsoft Docs"
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
  - "DateTimePicker-Steuerelement [Windows Forms], Keine Unicode-Unterstützung"
  - "Globalisierung [Windows Forms], Zeichensätze"
  - "ImageList-Komponente [Windows Forms], Keine Unicode-Unterstützung"
  - "Internationale Anwendungen [Windows Forms], Zeichenanzeige"
  - "Internationale Zeichen"
  - "ListView-Steuerelement [Windows Forms], Keine Unicode-Unterstützung"
  - "Lokalisierung [Windows Forms], Zeichensätze"
  - "MonthCalendar-Steuerelement [Windows Forms], Keine Unicode-Unterstützung"
  - "ProgressBar-Steuerelement [Windows Forms], Unicodefähige Formulare"
  - "StatusBar-Steuerelement [Windows Forms], Keine Unicode-Unterstützung"
  - "TabControl-Steuerelement [Windows Forms], Keine Unicode-Unterstützung"
  - "ToolBar-Steuerelement [Windows Forms], Keine Unicode-Unterstützung"
  - "TrackBar-Steuerelement [Windows Forms], Keine Unicode-Unterstützung"
  - "TreeView-Steuerelement [Windows Forms], Keine Unicode-Unterstützung"
  - "Unicode [Windows Forms]"
  - "Windows Forms, Codierung"
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Codierung und die Globalisierung von Windows&#160;Forms
Windows Forms\-Anwendungen sind vollständig Unicode\-aktiviert, was bedeutet, dass jedes Zeichen durch eine eindeutige Nummer, unabhängig von Plattform, Programm oder Sprache, dargestellt wird.  Weitere Informationen zu Unicode finden Sie auf der [Website des Unicode\-Konsortiums](http://www.unicode.org).  
  
## Vorteile von Unicode  
 Zu den Vorteilen von Unicode\-aktivierten Formularen zählt die Möglichkeit, mit Skripts zu arbeiten, die nur aus Unicode bestehen, z. B. Hindi.  Außerdem können Sie in einem Formular mehrere Sprachen verwenden.  In Unicode sind alle Zeichen zwei Byte lang. Doppelbyte\-Zeichen können also ohne besonderen Aufwand dargestellt werden.  Sie können zudem einen einzigen Codesatz schreiben, der auf allen Plattformen funktioniert.  Dies ist eine Änderung gegenüber früheren Versionen von [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], die unterschiedlichen Code für unterschiedliche Plattformen \(z. B. Windows NT und [!INCLUDE[win98](../../../../includes/win98-md.md)]\) voraussetzten.  
  
 Bestimmte Steuerelemente unterstützen jedoch Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] und Windows Millennium Edition nicht.  Diese Steuerelemente, die allesamt dem allgemeinen Steuerelement untergeordnet sind, verarbeiten Daten mit den Windows\-Codepages als [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].  Diese Steuerelemente sind: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> und <xref:System.Windows.Forms.StatusBar>.  Sie können daher in diesen Steuerelementen auf den aufgeführten Plattformen keine Unicode\-Daten anzeigen.  Sie können z. B. japanische Zeichen nicht auf einem englischen [!INCLUDE[win98](../../../../includes/win98-md.md)]\-Betriebssystem anzeigen.  
  
 Unicode\-kompatible Alternativen zu den <xref:System.Windows.Forms.ToolBar>\- und <xref:System.Windows.Forms.StatusBar>\-Steuerelementen stellen die <xref:System.Windows.Forms.ToolStrip>\- und <xref:System.Windows.Forms.StatusStrip>\-Steuerelemente dar, die diese älteren Steuerelemente ersetzen.  Um ein ähnliches Erscheinungsbild der visuellen Elemente in der Anwendung zu gewährleisten, verwenden Sie anstelle des <xref:System.Windows.Forms.MainMenu>\-Steuerelements das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement zum Rendern von Menüs.  Wie <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.StatusStrip> kann auch <xref:System.Windows.Forms.MenuStrip> Unicode\-Zeichen verarbeiten und anzeigen.  
  
## Siehe auch  
 [Globalisieren von Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)