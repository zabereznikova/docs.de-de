---
title: Debuggen von LINQ to DataSet-Abfragen
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: 38eda9f352c4a8d8590e5e57b48c694eadd0397b
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67503981"
---
# <a name="debugging-linq-to-dataset-queries"></a>Debuggen von LINQ to DataSet-Abfragen

Visual Studio unterstützt das Debuggen von LINQ zu DataSet-Code. Es gibt jedoch einige Unterschiede zwischen Debuggen von LINQ zu DataSet-Code und nicht-LINQ to DataSet, die verwalteten Code. Die meisten Debugfunktionen arbeiten mit LINQ, um DataSet-Anweisungen, z. B., schrittweise ausführen, das Festlegen von Haltepunkten und das Anzeigen von Ergebnissen, die in Debuggerfenstern angezeigt werden. Jedoch verzögerte abfrageausführung in verfügt über einige Nebenwirkungen, die Sie beim Debuggen von LINQ zu DataSet-Code berücksichtigen sollten, und es gibt einige Einschränkungen, die mit bearbeiten und fortfahren. Dieses Thema erläutert Aspekte des Debuggens, die LINQ to DataSet, die im Vergleich zu nicht-LINQ to DataSet, die verwalteten Code eindeutig sind.  
  
## <a name="viewing-results"></a>Anzeigen von Ergebnissen  
 Sie können das Ergebnis einer LINQ to DataSet-Anweisung mithilfe von DataTips, die Fenster "überwachen" und das Dialogfeld Schnellüberwachung anzeigen. Bei Verwendung eines Quellcodefensters können Sie den Mauszeiger auf eine Abfrage im Quellcodefenster bewegen, woraufhin ein <legacyBold>DataTip</legacyBold> eingeblendet wird. Sie können kopieren eine LINQ DataSet-Variablen, und fügen Sie ihn in das Überwachungsfenster oder im Dialogfeld "Schnellüberwachung". Eine Abfrage wird in LINQ to DataSet werden nicht ausgewertet, wenn es erstellt oder deklariert wird, aber nur, wenn die Abfrage ausgeführt wird. Dies wird als bezeichnet *verzögerte Ausführung*. Deshalb besitzt die Abfragevariable erst nach der Auswertung einen Wert. Weitere Informationen finden Sie unter [Abfragen in LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Der Debugger muss eine Abfrage auswerten, um die Abfrageergebnisse anzeigen zu können. Diese implizite Auswertung erfolgt, wenn Sie eine LINQ to DataSet-Abfrageergebnisses im Debugger anzeigen, und es hat einige Auswirkungen, die Sie berücksichtigen sollten. Jede Auswertung der Abfrage dauert einige Zeit. Das Erweitern des Ergebnisknotens nimmt ebenfalls Zeit in Anspruch. Bei einigen Abfragen kann eine wiederholte Auswertung zu beträchtlichen Leistungseinbußen führen. Die Auswertung einer Abfrage kann auch dazu führen, dass der Datenwert oder Zustand des Programms geändert wird. Nicht alle Abfragen verfügen über Nebeneffekte. Um festzustellen, ob eine Abfrage ohne Nebeneffekte sicher ausgewertet werden kann, sollten Sie sich den Code verdeutlichen, durch den die Abfrage implementiert wird. Weitere Informationen finden Sie unter [Nebeneffekte und Ausdrücke](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/a7a250bs(v=vs.120)).  
  
## <a name="edit-and-continue"></a>Bearbeiten und Fortfahren  
 Bearbeiten und Fortfahren unterstützt keine Änderungen an LINQ to DataSet-abfragen. Wenn Sie hinzufügen, entfernen oder eine LINQ für DataSet-Anweisung während einer Debugsitzung ändern, wird ein Dialogfeld, das Ihnen mitteilt, dass die Änderung von bearbeiten und Fortfahren nicht unterstützt wird angezeigt. An diesem Punkt können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und eine neue Sitzung mit dem bearbeiteten Code starten.  
  
 Darüber hinaus bearbeiten und Fortfahren unterstützt nicht das Ändern des Typs oder der Wert einer Variablen, die in einer LINQ to DataSet-Anweisung verwendet wird. Auch hier können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und neu starten.  
  
 In visuellen C# in Visual Studio können keine bearbeiten und Fortfahren für Code in eine Methode, die eine LINQ to DataSet-Abfrage enthält.  
  
 In Visual Basic in Visual Studio können Sie bearbeiten und Fortfahren für nicht-LINQ to DataSet-Code, sogar in einer Methode verwenden, die eine LINQ to DataSet-Abfrage enthält. Sie können hinzufügen oder Entfernen von Code vor der LINQ to DataSet-Anweisung, selbst wenn die Änderungen wirken sich die Zeilennummer der LINQ to DataSet-Abfrage auf. Für nicht-LINQ to DataSet-Code Debuggen in Visual Basic bleibt dasselbe wie vor der Einführung von LINQ to DataSet. Sie können nicht ändern, hinzufügen oder entfernen eine LINQ to DataSet-Abfrage jedoch, es sei denn, Sie beenden, Debuggen, um die Änderungen zu übernehmen.  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von verwaltetem Code](/visualstudio/debugger/debugging-managed-code)
- [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
