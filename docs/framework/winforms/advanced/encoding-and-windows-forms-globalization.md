---
title: Codierung und die Globalisierung von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
ms.openlocfilehash: 3a9d891fe898cf691a5f0d36e6360c2a73fb199d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629228"
---
# <a name="encoding-and-windows-forms-globalization"></a>Codierung und die Globalisierung von Windows Forms
Windows Forms-Anwendungen sind vollständig Unicode-aktiviert, was bedeutet, dass jedes Zeichen durch eine eindeutige Nummer, unabhängig von Plattform, Programm oder Sprache, dargestellt wird. Weitere Informationen zu Unicode finden Sie unter den [Website des Unicode Consortium](https://www.unicode.org).  
  
## <a name="benefits-of-unicode"></a>Vorteile von Unicode  
 Zu den Vorteilen von Unicode-aktivierten Formularen zählt die Möglichkeit, mit Skripts zu arbeiten, die nur aus Unicode bestehen, z. B. Hindi. Außerdem können Sie in einem Formular mehrere Sprachen verwenden. In Unicode sind alle Zeichen zwei Byte lang. Doppelbyte-Zeichen können also ohne besonderen Aufwand dargestellt werden. Sie können zudem einen einzigen Codesatz schreiben, der auf allen Plattformen funktioniert. Dies ist eine Änderung gegenüber früheren Versionen von Visual Basic, in dem Sie die unterschiedlichen Code für verschiedene Plattformen, z. B. Windows NT schreiben musste und [!INCLUDE[win98](../../../../includes/win98-md.md)].  
  
 Bestimmte Steuerelemente unterstützen jedoch Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] und Windows Millennium Edition nicht. Diese Steuerelemente, die allesamt dem allgemeinen Steuerelement untergeordnet sind, verarbeiten Daten mit den Windows-Codepages als [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)]. Diese Steuerelemente sind: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> und <xref:System.Windows.Forms.StatusBar>. Sie können daher in diesen Steuerelementen auf den aufgeführten Plattformen keine Unicode-Daten anzeigen. Sie können z. B. japanische Zeichen nicht auf einem englischen [!INCLUDE[win98](../../../../includes/win98-md.md)]-Betriebssystem anzeigen.  
  
 Unicode-kompatible Alternativen zu den <xref:System.Windows.Forms.ToolBar>- und <xref:System.Windows.Forms.StatusBar>-Steuerelementen stellen die <xref:System.Windows.Forms.ToolStrip>- und <xref:System.Windows.Forms.StatusStrip>-Steuerelemente dar, die diese älteren Steuerelemente ersetzen. Um ein ähnliches Erscheinungsbild der visuellen Elemente in der Anwendung zu gewährleisten, verwenden Sie anstelle des <xref:System.Windows.Forms.MainMenu>-Steuerelements das <xref:System.Windows.Forms.MenuStrip>-Steuerelement zum Rendern von Menüs. Wie <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.StatusStrip> kann auch <xref:System.Windows.Forms.MenuStrip> Unicode-Zeichen verarbeiten und anzeigen.  
  
## <a name="see-also"></a>Siehe auch

- [Globalisieren von Windows Forms-Anwendungen](globalizing-windows-forms.md)
