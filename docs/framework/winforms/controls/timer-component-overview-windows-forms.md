---
title: "&#220;bersicht &#252;ber die Timer-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "Timer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Timer-Komponente [Windows Forms], Informationen über Timer-Komponenten"
  - "Zeitgeber, Informationen über Zeitgeber"
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# &#220;bersicht &#252;ber die Timer-Komponente (Windows&#160;Forms)
Die <xref:System.Windows.Forms.Timer>\-Komponente in Windows Forms löst in regelmäßigen Abständen ein Ereignis aus.  Diese Komponente ist für eine Windows Forms\-Umgebung gedacht.  Wenn Sie einen Zeitgeber benötigen, der für eine Serverumgebung geeignet ist, informieren Sie sich unter [Introduction to Server\-Based Timers](http://msdn.microsoft.com/de-de/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## Wichtige Eigenschaften, Methoden und Ereignisse  
 Die Länge der Intervalle wird von der <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft definiert, deren Wert in Millisekunden angegeben wird.  Wenn die Komponente aktiviert ist, wird das <xref:System.Windows.Forms.Timer.Tick>\-Ereignis bei jedem Intervall ausgelöst.  Hier würden Sie den auszuführenden Code einfügen.  Weitere Informationen finden Sie unter [Gewusst wie: Ausführen von Prozeduren in festgelegten Abständen mit der Timer\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).  Die wichtigsten Methoden der <xref:System.Windows.Forms.Timer>\-Komponente sind <xref:System.Windows.Forms.Timer.Start%2A> und <xref:System.Windows.Forms.Timer.Stop%2A>, die den Zeitgeber aktivieren und deaktivieren.  Wenn der Zeitgeber deaktiviert ist, wird er zurückgesetzt. Es gibt keine Möglichkeit, eine <xref:System.Windows.Forms.Timer>\-Komponente \(vorübergehend\) anzuhalten.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Timer>   
 [Timer\-Komponente](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)   
 [Einschränkungen für die Interval\-Eigenschaft der Timer\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)