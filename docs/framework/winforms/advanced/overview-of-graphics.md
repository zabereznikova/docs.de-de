---
title: "&#220;bersicht &#252;ber Grafiken | Microsoft Docs"
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
  - "Grafiken, Informationen über Grafiken"
  - "Grafiken, Verwenden einer verwalteten Schnittstelle"
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# &#220;bersicht &#252;ber Grafiken
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ist eine Anwendungsprogrammierschnittstelle \(Application Programming Interface, API\), die das Subsystem von Microsoft Windows bildet. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] hat die Aufgabe, Informationen auf Bildschirmen anzuzeigen und an Drucker auszugeben.  Wie der Name andeutet, ist [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] der Nachfolger von [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], die Schnittstelle für Grafikgeräte \(Graphics Device Interface\), die in früheren Versionen von Windows enthalten ist.  
  
## Schnittstelle für verwaltete Klassen  
 Die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-API wird über einen Satz von Klassen verfügbar gemacht, die als verwalteter Code bereitgestellt werden.  Dieser Satz von Klassen wird als *Schnittstelle für verwaltete Klassen* für [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bezeichnet.  Die Schnittstelle für verwaltete Klassen besteht aus den folgenden Namespaces:  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 Mit einem Graphics Device Interface wie [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie Informationen auf einem Bildschirm anzeigen oder an einen Drucker senden, ohne sich Gedanken über die Details des jeweiligen Ausgabegeräts machen zu müssen.  Der Programmierer ruft Methoden auf, die von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-Klassen bereitgestellt werden. In diesen Methoden wiederum werden die speziellen Gerätetreiber aufgerufen.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] isoliert die jeweilige Anwendung von der Grafikhardware. Diese Isolierung versetzt den Programmierer in die Lage, geräteunabhängige Anwendungen erstellen zu können.  
  
## Siehe auch  
 [Übersicht über Grafiken](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)