---
title: "Einschr&#228;nkungen f&#252;r die Interval-Eigenschaft der Timer-Komponente in Windows&#160;Forms | Microsoft Docs"
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
  - "Interval-Eigenschaft, Einschränkungen"
  - "Timer-Komponente [Windows Forms], Einschränkungen für die Interval-Eigenschaft"
  - "Zeitgeber, Ereignisintervalle"
  - "Zeitgeber, Windows-basiert"
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Einschr&#228;nkungen f&#252;r die Interval-Eigenschaft der Timer-Komponente in Windows&#160;Forms
Die <xref:System.Windows.Forms.Timer>\-Komponente in Windows Forms verfügt über eine <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft, durch die die Anzahl der Millisekunden zwischen zwei Zeitgeberereignissen festgelegt wird.  Solange die Komponente nicht deaktiviert wird, erhält ein Zeitgeber in ungefähr gleichen Zeitabständen <xref:System.Windows.Forms.Timer.Tick>\-Ereignisse.  
  
 Diese Komponente ist für eine Windows Forms\-Umgebung gedacht.  Wenn Sie einen Zeitgeber benötigen, der für eine Serverumgebung geeignet ist, informieren Sie sich unter [Introduction to Server\-Based Timers](http://msdn.microsoft.com/de-de/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## Die Interval\-Eigenschaft  
 Bei der Programmierung einer <xref:System.Windows.Forms.Timer>\-Komponente sind einige Einschränkungen für die <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft zu beachten:  
  
-   Wenn Ihre oder eine andere Anwendung das System stark beansprucht \(beispielsweise durch lange Schleifen, aufwendige Berechnungen oder Zugriffe auf Laufwerke, Netzwerke bzw. Anschlüsse\), empfängt Ihre Anwendung möglicherweise nicht so häufig Zeitgeberereignisse, wie durch die <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft festgelegt.  
  
-   Es ist nicht gewährleistet, dass das Intervall genau zum angegebenen Zeitpunkt abläuft.  Um die Genauigkeit sicherzustellen, sollte der Zeitgeber bei Bedarf die Systemuhr überprüfen, anstatt die bisher abgelaufene Zeit intern zu verfolgen.  
  
-   Die Genauigkeit der <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft liegt im Millisekundenbereich.  Einige Computer stellen einen hochauflösenden Zähler zur Verfügung, dessen Auflösung über dem Millisekundenbereich liegt.  Ob ein solcher Zähler verfügbar ist, ist von der Prozessorhardware des Computers abhängig.  Weitere Informationen finden Sie im Microsoft Knowledge Base\-Artikel 172338, "How To Use QueryPerformanceCounter to Time Code", unter http:\/\/support.microsoft.com.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Timer>   
 [Timer\-Komponente](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)   
 [Übersicht über die Timer\-Komponente](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)