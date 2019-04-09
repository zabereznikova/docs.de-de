---
title: Debuggen von LINQ to DataSet-Abfragen
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: 0e015cc6042a21bf6d35915c3e19bfeb9b0dbb2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133328"
---
# <a name="debugging-linq-to-dataset-queries"></a>Debuggen von LINQ to DataSet-Abfragen

Visual Studio unterstützt das Debuggen von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Code. Zwischen dem Debuggen von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Code und nicht von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] verwaltetem Code gibt es aber einige Unterschiede. Die meisten Debugfunktionen arbeiten mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Anweisungen, z. B. für das schrittweise Ausführen, das Festlegen von Haltepunkten und das Anzeigen von Ergebnissen in Debuggerfenstern. Jedoch verzögerte abfrageauswertung hat einige Nebenwirkungen, die Sie, während des Debuggens berücksichtigen sollten [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] code ein, und es gibt einige Einschränkungen, die mit bearbeiten und fortfahren. In diesem Thema erläutert Aspekte des Debuggens, die nur für [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] im Vergleich zu anderen[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] von verwaltetem Code.  
  
## <a name="viewing-results"></a>Anzeigen von Ergebnissen  
 Sehen Sie das Ergebnis einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] mithilfe von DataTips, die Fenster "überwachen" und das Dialogfeld "Schnellüberwachung". Bei Verwendung eines Quellcodefensters können Sie den Mauszeiger auf eine Abfrage im Quellcodefenster bewegen, woraufhin ein <legacyBold>DataTip</legacyBold> eingeblendet wird. Sie können eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Variable kopieren und in das Überwachungsfenster oder das Dialogfeld Schnellüberwachung einfügen. In [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] wird eine Abfrage nicht beim Erstellen oder Deklarieren, sondern erst bei ihrer Ausführung ausgewertet. Dies wird als bezeichnet *verzögerte Ausführung*. Deshalb besitzt die Abfragevariable erst nach der Auswertung einen Wert. Weitere Informationen finden Sie unter [Abfragen in LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Der Debugger muss eine Abfrage auswerten, um die Abfrageergebnisse anzeigen zu können. Diese implizite Auswertung erfolgt, wenn Sie eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrageergebnis in den Debugger, und es hat einige Auswirkungen, die Sie berücksichtigen sollten. Jede Auswertung der Abfrage dauert einige Zeit. Das Erweitern des Ergebnisknotens nimmt ebenfalls Zeit in Anspruch. Bei einigen Abfragen kann eine wiederholte Auswertung zu beträchtlichen Leistungseinbußen führen. Die Auswertung einer Abfrage kann auch dazu führen, dass der Datenwert oder Zustand des Programms geändert wird. Nicht alle Abfragen verfügen über Nebeneffekte. Um festzustellen, ob eine Abfrage ohne Nebeneffekte sicher ausgewertet werden kann, sollten Sie sich den Code verdeutlichen, durch den die Abfrage implementiert wird. Weitere Informationen finden Sie unter [Nebeneffekte und Ausdrücke](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/a7a250bs(v=vs.120)).  
  
## <a name="edit-and-continue"></a>Bearbeiten und Fortfahren  
 Bearbeiten und Fortfahren unterstützt keine Änderungen an [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen. Wenn Sie Daten hinzufügen, entfernen oder Ändern einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] -Anweisung während einer Debugsitzung ein Dialogfeld angezeigt wird, der anzeigt, die Änderung wird von bearbeiten und Fortfahren nicht unterstützt. An diesem Punkt können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und eine neue Sitzung mit dem bearbeiteten Code starten.  
  
 Darüber hinaus bearbeiten und Fortfahren unterstützt nicht das Ändern des Typs oder der Wert einer Variablen, die verwendet wird eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Anweisung. Auch hier können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und neu starten.  
  
 In Visual c# in Visual Studio können keine bearbeiten und Fortfahren für Code in eine Methode, enthält eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage.  
  
 In Visual Basic in Visual Studio können Sie bearbeiten und Fortfahren für nicht -[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Code auch in eine Methode, enthält eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage. Sie können hinzufügen oder Entfernen von Code vor der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] -Anweisung, selbst wenn die Änderungen wirken sich die Nummer der Zeile auf die [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage. Für das Debugverhalten in Visual Basic nicht[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] -Code bleibt dasselbe wie vor [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] wurde eingeführt. Sie können nicht zu ändern, hinzufügen oder Entfernen einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] abzufragen, aber es sei denn, Sie beenden, Debuggen, um die Änderungen zu übernehmen.  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von verwaltetem Code](/visualstudio/debugger/debugging-managed-code)
- [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
