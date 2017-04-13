---
title: "Durch ge&#228;nderte Eigenschaften ausgel&#246;ste Ereignisse | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Eigenschaftenänderungen (mit Code)"
  - "Eigenschaften [Windows Forms], Änderungen"
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Durch ge&#228;nderte Eigenschaften ausgel&#246;ste Ereignisse
Wenn das Steuerelement Benachrichtigungen senden soll, sobald sich eine Eigenschaft mit dem Namen *PropertyName* ändert, müssen Sie ein Ereignis mit dem Namen *PropertyName*`Changed` und eine Methode mit dem Namen `On`*PropertyName*`Changed` definieren, die das Ereignis auslöst.  Gemäß der Konvention für die Namensgebung in Windows Forms muss das Wort *Changed* hinter dem Namen der Eigenschaft angefügt werden.  Der zugeordnete Ereignisdelegattyp für durch geänderte Eigenschaften ausgelöste Ereignisse ist <xref:System.EventHandler>, der Ereignisdatentyp ist <xref:System.EventArgs>.  Die Basisklasse <xref:System.Windows.Forms.Control> definiert viele durch geänderte Eigenschaften ausgelöste Ereignisse, z. B. <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>.  Hintergrundinformationen über Ereignisse finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md) und [Ereignisse in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).  
  
 Änderungsereignisse für Eigenschaften sind sinnvoll, da Consumer eines Steuerelements mit ihrer Hilfe Ereignishandler verknüpfen können, die auf die Änderung reagieren.  Wenn das Steuerelement auf ein durch geänderte Eigenschaften ausgelöstes Ereignis reagieren soll, überschreiben Sie die entsprechende `On`*PropertyName*`Changed`\-Methode, anstatt einen Delegaten an das Ereignis anzufügen.  Ein Steuerelement reagiert in der Regel auf ein Änderungsereignis für eine Eigenschaft, indem es andere Eigenschaften aktualisiert oder einen Teil bzw. die gesamte Zeichnungsoberfläche neu zeichnet.  
  
 Im folgenden Beispiel wird gezeigt, wie das benutzerdefinierte Steuerelement `FlashTrackBar` auf einige der durch geänderte Eigenschaften ausgelösten Ereignisse reagiert, die es von <xref:System.Windows.Forms.Control> erbt.  Das vollständige Beispiel finden Sie unter [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## Siehe auch  
 [Ereignisse](../../../../docs/standard/events/index.md)   
 [Ereignisse in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [Eigenschaften von Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)