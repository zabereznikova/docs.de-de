---
title: "Drag&#160;&amp;&#160;Drop-Funktionen in Windows Forms | Microsoft Docs"
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
  - "Drag & Drop, Windows Forms"
  - "Windows Forms, Drag & Drop"
ms.assetid: 65cd2c03-8782-474e-b958-cbe43eeb902c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Drag&#160;&amp;&#160;Drop-Funktionen in Windows Forms
Windows Forms umfasst eine Reihe von Methoden, Ereignissen und Klassen, die das Drag & Drop\-Verhalten implementieren.  Dieses Thema enthält eine Übersicht über die Drag & Drop\-Unterstützung in Windows Forms.  Weitere Informationen finden Sie unter [Drag & Drop\-Operationen und Unterstützung der Zwischenablage](http://msdn.microsoft.com/library/fe5ebfwe%20\(v=vs.110\)).  
  
## Ausführen von Drag & Drop\-Vorgängen  
 Um einen Drag & Drop\-Vorgang auszuführen, verwenden Sie die <xref:System.Windows.Forms.Control.DoDragDrop%2A>\-Methode der <xref:System.Windows.Forms.Control>\-Klasse.  Weitere Informationen, wie ein Drag & Drop\-Vorgang ausgeführt wird, finden Sie unter <xref:System.Windows.Forms.Control.DoDragDrop%2A>.  Um das Rechteck abzurufen, über das der Mauszeiger gezogen werden muss, bevor ein Drag & Drop\-Vorgang beginnt, verwenden Sie die <xref:System.Windows.Forms.SystemInformation.DragSize%2A>\-Eigenschaft der <xref:System.Windows.Forms.SystemInformation>\-Klasse.  
  
## Ereignisse im Zusammenhang mit Drag & Drop\-Vorgängen  
 Es gibt zwei Kategorien von Ereignissen in einem Drag & Drop\-Vorgang: Ereignisse, die im aktuellen Ziel des Drag & Drop\-Vorgangs auftreten, und Ereignisse, die in der Quelle des Drag & Drop\-Vorgangs auftreten.  
  
### Ereignisse im aktuellen Ziel  
 Die folgende Tabelle zeigt die Ereignisse, die im aktuellen Ziel eines Drag & Drop\-\-Vorgangs auftreten.  
  
|Mausereignis|Beschreibung|  
|------------------|------------------|  
|<xref:System.Windows.Forms.Control.DragEnter>|Dieses Ereignis tritt auf, wenn ein Objekt in die Begrenzungen des Steuerelements gezogen wird.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragOver>|Dieses Ereignis tritt auf, wenn ein Objekt gezogen wird, während sich der Mauszeiger innerhalb der Grenzen des Steuerelements befindet.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragDrop>|Dieses Ereignis tritt auf, wenn ein Drag & Drop\-Vorgang abgeschlossen wurde.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragLeave>|Dieses Ereignis tritt auf, wenn ein Objekt über die Grenzen des Steuerelements nach außen gezogen wird.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.EventArgs>.|  
  
 Die <xref:System.Windows.Forms.DragEventArgs>\-Klasse stellt die Position des Mauszeigers, den aktuellen Zustand der Maustasten und der Zusatztasten der Tastatur, die gezogenen Daten und die <xref:System.Windows.Forms.DragDropEffects>\-Werte bereit, die die Vorgänge, die für die Quelle des Ziehereignisses zulässig sind, sowie den Zielablegeeffekt für den Vorgang angeben.  
  
### Ereignisse in der Quelle  
 Die folgende Tabelle zeigt die Ereignisse, die in der Quelle eines Drag & Drop\-Vorgangs auftreten.  
  
|Mausereignis|Beschreibung|  
|------------------|------------------|  
|<xref:System.Windows.Forms.Control.GiveFeedback>|Dieses Ereignis tritt während eines Ziehvorgangs auf.  Es bietet die Möglichkeit, dem Benutzer einen visuellen Hinweis zu geben, dass der Drag & Drop\-Vorgang auftritt, z. B. Ändern des Mauszeigers.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.GiveFeedbackEventArgs>.|  
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|Dieses Ereignis wird während eines Drag & Drop\-Vorgangs ausgelöst. Dadurch kann die Quelle des Ziehvorgangs bestimmen, ob der Drag & Drop\-Vorgang abgebrochen werden soll.  Der Handler für dieses Ereignis empfängt ein Argument des Typs <xref:System.Windows.Forms.QueryContinueDragEventArgs>.|  
  
 Die <xref:System.Windows.Forms.QueryContinueDragEventArgs>\-Klasse stellt Folgendes bereit: den aktuellen Zustand der Maus und der Zusatztasten der Tastatur, einen Wert, der angibt, ob die ESC\-Taste gedrückt wurde, und einen <xref:System.Windows.Forms.DragAction>\-Wert, der festgelegt werden kann, um anzugeben, ob der Drag & Drop\-Vorgang fortgesetzt werden soll.  
  
## Siehe auch  
 [Mauseingabe in einer Windows Forms\-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)