---
title: "Debuggen von LINQ to DataSet-Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Debuggen von LINQ to DataSet-Abfragen
[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] unterstützt das Debugging von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Code.  Zwischen dem Debuggen von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Code und nicht von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] verwaltetem Code gibt es aber einige Unterschiede. Die meisten Debugfunktionen arbeiten mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Anweisungen, z. B. für das schrittweise Ausführen, das Festlegen von Haltepunkten und das Anzeigen von Ergebnissen in Debuggerfenstern.  Die verzögerte Abfrageauswertung hat aber einige Nebenwirkungen, die Sie beim Debuggen von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Code berücksichtigen sollten. Außerdem gelten für die Verwendung von "Bearbeiten und Fortfahren" einige Einschränkungen.  In diesem Thema werden Aspekte des Debuggens erläutert, die so nur in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] eine Rolle spielen. Für das Debuggen von nicht von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] verwaltetem Code sind sie nicht relevant.  
  
## Anzeigen von Ergebnissen  
 Das Ergebnis einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Anweisung kann mithilfe von \<legacyBold\>DataTips\<\/legacyBold\>, über das Überwachungsfenster oder im Dialogfeld \<legacyBold\>Schnellüberwachung\<\/legacyBold\> angezeigt werden.  Bei Verwendung eines Quellcodefensters können Sie den Mauszeiger auf eine Abfrage im Quellcodefenster bewegen, woraufhin ein \<legacyBold\>DataTip\<\/legacyBold\> eingeblendet wird.  Sie können eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Variable kopieren und in das Überwachungsfenster oder das Dialogfeld Schnellüberwachung einfügen. In [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] wird eine Abfrage nicht beim Erstellen oder Deklarieren, sondern erst bei ihrer Ausführung ausgewertet.  Dies wird als *verzögerte Ausführung* bezeichnet.  Deshalb besitzt die Abfragevariable erst nach der Auswertung einen Wert.  Weitere Informationen finden Sie unter [Abfragen in LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Der Debugger muss eine Abfrage auswerten, um die Abfrageergebnisse anzeigen zu können.  Diese implizite Auswertung erfolgt, wenn Sie sich ein [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrageergebnis im Debugger ansehen. Sie hat einige Auswirkungen, die Sie berücksichtigen sollten.  Jede Auswertung der Abfrage dauert einige Zeit.  Das Erweitern des Ergebnisknotens nimmt ebenfalls Zeit in Anspruch.  Bei einigen Abfragen kann eine wiederholte Auswertung zu beträchtlichen Leistungseinbußen führen.  Die Auswertung einer Abfrage kann auch dazu führen, dass der Datenwert oder Zustand des Programms geändert wird.  Nicht alle Abfragen verfügen über Nebeneffekte.  Um festzustellen, ob eine Abfrage ohne Nebeneffekte sicher ausgewertet werden kann, sollten Sie sich den Code verdeutlichen, durch den die Abfrage implementiert wird.  Weitere Informationen finden Sie unter [Nebeneffekte und Ausdrücke](../Topic/Side%20Effects%20and%20Expressions.md).  
  
## "Bearbeiten und Fortfahren"  
 "Bearbeiten und Fortfahren" unterstützt keine Änderungen an [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfragen.  Wenn Sie eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Anweisung während einer Debugsitzung hinzufügen, entfernen oder ändern, wird ein Dialogfeld mit dem Hinweis eingeblendet, dass die Änderung von \<legacyBold\>Bearbeiten und Fortfahren\<\/legacyBold\> nicht unterstützt wird.  An diesem Punkt können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und eine neue Sitzung mit dem bearbeiteten Code starten.  
  
 Außerdem bietet \<legacyBold\>Bearbeiten und Fortfahren\<\/legacyBold\> keine Unterstützung für das Ändern des Typs oder Werts einer in einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Anweisung verwendeten Variablen.  Auch hier können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und neu starten.  
  
 In Visual C\# kann "Bearbeiten und Fortfahren" nicht für Code in einer Methode verwendet werden, die eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage enthält.  
  
 In Visual Basic in Visual Studio kann "Bearbeiten und Fortfahren" für Nicht\-[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Code verwendet werden, und dies auch in einer Methode, die eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage enthält.  Sie können Code vor der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Anweisung sogar dann hinzufügen oder entfernen, wenn sich die Änderungen auf die Zeilennummer der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage auswirken.  Das Debugverhalten in Visual Basic für Nicht\-[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Code bleibt dasselbe wie vor der Einführung von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  Es ist jedoch nicht möglich, eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage zu ändern, hinzuzufügen oder zu entfernen, es sei denn, Sie beenden den Debugvorgang, um die Änderungen zu übernehmen.  
  
## Siehe auch  
 [Debuggen von verwaltetem Code](../Topic/Debugging%20Managed%20Code.md)   
 [Informationen zum Programmieren](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)