---
title: "Entwurfszeitfehler im Windows Forms-Designer | Microsoft Docs"
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
  - "DTELErrorList"
  - "WhyDTELPage"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Entwurfszeitfehler [Windows Forms-Designer]"
  - "Fehler [Windows Forms-Designer]"
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Entwurfszeitfehler im Windows Forms-Designer
In diesem Thema werden die Bedeutung und der Verwendungszweck der Entwurfszeitfehlerliste erläutert, die in Microsoft Visual Studio angezeigt wird, wenn der Windows Forms\-Designer nicht geladen werden kann.  Wenn diese Fehlerliste angezeigt wird, sollte dies nicht als Fehler im Designer gewertet werden. Vielmehr handelt es sich um eine Hilfe zur Korrektur von Codefehlern.  
  
 Ein grundlegendes Verständnis dieser Fehlerliste hilft Ihnen, Anwendungen zu debuggen, indem detaillierte Informationen zu den Fehlern sowie Lösungsvorschläge angezeigt werden.  
  
## Die Oberfläche der Entwurfszeitfehlerliste  
 Wenn der Windows Forms\-Designer nicht geladen werden kann, wird eine Fehlerliste im Designer angezeigt.  Die Fehler sind in Kategorien unterteilt.  Wenn Sie beispielsweise über vier Instanzen nicht deklarierter Variablen verfügen, werden diese in derselben Fehlerkategorie gruppiert.  Jede Fehlerkategorie enthält eine kurze Beschreibung mit einer Fehlerzusammenfassung.  
  
 Sie können eine Fehlerkategorie erweitern oder reduzieren, indem Sie entweder auf die Überschrift der Fehlerkategorie oder auf das Chevron\-Zeichen zum Erweitern\/Reduzieren klicken.  Wenn Sie eine Fehlerkategorie erweitern, wird die folgende zusätzliche Hilfe angezeigt:  
  
-   Instanzen dieses Fehlers  
  
-   Hilfe zu diesem Fehler  
  
-   Forumsbeiträge zu diesem Fehler  
  
### Instanzen dieses Fehlers  
 In der zusätzlichen Hilfe sind alle Instanzen des Fehlers im aktuellen Projekt aufgelistet.  Bei vielen Fehlern wird die genaue Position im folgenden Format angezeigt: *\[Projektname\]* *\[Formularname\]* Zeile:*\[Zeilennummer\]* Spalte:*\[Spaltennummer\]*.  Über den Link **Gehe zu Code** gelangen Sie zu der Stelle im Code, an der der Fehler aufgetreten ist.  
  
 Wenn eine Aufrufliste mit dem Fehler verknüpft ist, können Sie auf den Link **Aufrufliste anzeigen** klicken. Dadurch wird der Fehler erweitert und die Aufrufliste angezeigt.  Durch Überprüfen des Stapels können Sie wertvolle Debuginformationen erhalten.  Beispielsweise können Sie die Funktionen nachverfolgen, die vor Auftreten des Fehlers aufgerufen wurden.  Die Aufrufliste ist auswählbar und kann somit kopiert und gespeichert werden.  
  
> [!NOTE]
>  In Visual Basic wird in der Entwurfszeitfehlerliste nicht mehr als ein Fehler angezeigt, es können jedoch mehrere Instanzen desselben Fehlers eingeblendet werden.  In Visual C\+\+ weisen die Fehler keine Gehe zu Code\-Links\/Zeilennummernlinks auf.  
  
### Hilfe zu diesem Fehler  
 Wenn der Fehler einen Link zu einem verknüpften MSDN\-Hilfethema enthält, umfasst die zusätzliche Hilfe einen Link zum Hilfethema.  Wenn Sie auf den Link klicken, wird das zugehörige Hilfethema in Visual Studio angezeigt.  
  
### Forumsbeiträge zu diesem Fehler  
 Die zusätzliche Hilfe umfasst einen Link zu MSDN\-Forumsbeiträgen in Zusammenhang mit dem Fehler.  Die Foren werden auf Grundlage der Zeichenfolge der Fehlermeldung durchsucht.  Sie können auch in folgenden Foren suchen:  
  
-   [Windows Forms\-Designer\-Forum](http://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [Windows Forms\-Foren](http://go.microsoft.com/fwlink/?LinkId=203523)  
  
### Ignorieren und fortfahren  
 Sie können die Fehlerbedingung wahlweise ignorieren und mit dem Laden des Designers fortfahren.  Wenn Sie diese Aktion auswählen, kann dies zu unerwartetem Verhalten führen.  Steuerelemente werden beispielsweise nicht auf der Entwurfsoberfläche angezeigt.  
  
## Siehe auch  
 [Troubleshooting Design\-Time Development](../Topic/Troubleshooting%20Design-Time%20Development.md)   
 [Problembehandlung beim Erstellen von Komponenten und Steuerelementen](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)   
 [Entwickeln von Windows Forms\-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Windows Forms Designer Error Messages](http://msdn.microsoft.com/de-de/cf610bf4-5fe4-471c-bce7-6a05ece07bd2)