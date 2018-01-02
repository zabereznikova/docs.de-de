---
title: Debuggen von LINQ to DataSet-Abfragen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 08c66309d4c789acc0f2ddf6159a11c5fb963e80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-linq-to-dataset-queries"></a>Debuggen von LINQ to DataSet-Abfragen
[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] unterstützt das Debugging von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Code. Zwischen dem Debuggen von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Code und nicht von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] verwaltetem Code gibt es aber einige Unterschiede. Die meisten Debugfunktionen arbeiten mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Anweisungen, z. B. für das schrittweise Ausführen, das Festlegen von Haltepunkten und das Anzeigen von Ergebnissen in Debuggerfenstern. Allerdings verzögerte abfrageauswertung hat einige Nebenwirkungen, die Sie während des Debuggens berücksichtigen sollten [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] code ein, und es gibt einige Einschränkungen bei der Verwendung von bearbeiten und fortfahren. In diesem Thema erläutert Aspekte des Debuggens, die nur für die [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] im Vergleich zu nicht -[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] von verwaltetem Code.  
  
## <a name="viewing-results"></a>Anzeigen von Ergebnissen  
 Sehen Sie das Ergebnis einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Anweisung mithilfe von DataTips, Fenster "überwachen" und das Dialogfeld Schnellüberwachung. Bei Verwendung eines Quellcodefensters können Sie den Mauszeiger auf eine Abfrage im Quellcodefenster bewegen, woraufhin ein <legacyBold>DataTip</legacyBold> eingeblendet wird. Sie können eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Variable kopieren und in das Überwachungsfenster oder das Dialogfeld Schnellüberwachung einfügen. In [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] wird eine Abfrage nicht beim Erstellen oder Deklarieren, sondern erst bei ihrer Ausführung ausgewertet. Hierbei spricht *verzögerte Ausführung*. Deshalb besitzt die Abfragevariable erst nach der Auswertung einen Wert. Weitere Informationen finden Sie unter [Abfragen in LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Der Debugger muss eine Abfrage auswerten, um die Abfrageergebnisse anzeigen zu können. Diese implizite Auswertung erfolgt, wenn Sie eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] -Abfrageergebnis in den Debugger, und es hat einige Auswirkungen, die Sie berücksichtigen sollten. Jede Auswertung der Abfrage dauert einige Zeit. Das Erweitern des Ergebnisknotens nimmt ebenfalls Zeit in Anspruch. Bei einigen Abfragen kann eine wiederholte Auswertung zu beträchtlichen Leistungseinbußen führen. Die Auswertung einer Abfrage kann auch dazu führen, dass der Datenwert oder Zustand des Programms geändert wird. Nicht alle Abfragen verfügen über Nebeneffekte. Um festzustellen, ob eine Abfrage ohne Nebeneffekte sicher ausgewertet werden kann, sollten Sie sich den Code verdeutlichen, durch den die Abfrage implementiert wird. Weitere Informationen finden Sie unter [Nebeneffekte und Ausdrücke](http://msdn.microsoft.com/library/e1f8a6ea-9e19-481d-b6bd-df120ad3bf4e).  
  
## <a name="edit-and-continue"></a>Bearbeiten und Fortfahren  
 Bearbeiten und Fortfahren unterstützt keine Änderungen an [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen. Wenn Sie Daten hinzufügen, entfernen oder Ändern einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] -Anweisung während einer Debugsitzung ein Dialogfeld wird angezeigt, die Sie informiert, die Änderung von bearbeiten und Fortfahren nicht unterstützt wird. An diesem Punkt können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und eine neue Sitzung mit dem bearbeiteten Code starten.  
  
 Darüber hinaus bearbeiten und Fortfahren unterstützt nicht das Ändern des Typs oder der Wert einer Variablen, die verwendet wird eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Anweisung. Auch hier können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und neu starten.  
  
 In Visual c# in Visual Studio können keine bearbeiten und Fortfahren für Code in einer Methode, enthält eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage.  
  
 In Visual Basic in Visual Studio können Sie bearbeiten und Fortfahren für nicht -[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Code, sogar in einer Methode, die enthält eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage. Können Sie hinzufügen oder Entfernen von Code vor der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] -Anweisung, selbst wenn die Änderungen betreffen die Nummer der Zeile in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage. Für das Debugverhalten in Visual Basic nicht[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] -Code bleibt dasselbe wie vor dem [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] eingeführt wurde. Sie können nicht ändern, hinzufügen oder Entfernen einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen jedoch, es sei denn, Sie Beenden des Debuggens, um die Änderungen zu übernehmen.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von verwaltetem Code](/visualstudio/debugger/debugging-managed-code)  
 [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
