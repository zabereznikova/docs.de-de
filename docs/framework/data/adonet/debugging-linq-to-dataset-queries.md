---
title: Debuggen von LINQ to DataSet-Abfragen
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: 638198ef4c78b84dd12c3d39f83bf8a015e566c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183194"
---
# <a name="debugging-linq-to-dataset-queries"></a>Debuggen von LINQ to DataSet-Abfragen

Visual Studio unterstützt das Debuggen von LINQ to DataSet-Code. Es gibt jedoch einige Unterschiede zwischen dem Debuggen LINQ to DataSet Codes und nicht LINQ to DataSet verwaltetem Code. Die meisten Debuggingfeatures funktionieren mit LINQ to DataSet-Anweisungen, einschließlich schrittweise Ausführung, Festlegung von Haltepunkten und Anzeigen der in Debuggerfenstern angezeigten Ergebnisse. Die verzögerte Abfrage Ausführung in hat jedoch einige Nebeneffekte, die Sie beim Debuggen LINQ to DataSet Codes berücksichtigen sollten, und es gibt einige Einschränkungen bei der Verwendung von "Bearbeiten und Fortfahren". In diesem Thema werden Aspekte des Debuggens erläutert, die im Vergleich zu nicht LINQ to DataSet verwaltetem Code LINQ to DataSet eindeutig sind.  
  
## <a name="viewing-results"></a>Anzeigen von Ergebnissen  

 Sie können das Ergebnis einer LINQ to DataSet Anweisung anzeigen, indem Sie DataTips, die Überwachungsfenster und das Dialogfeld schnell Überwachung verwenden. Bei Verwendung eines Quellcodefensters können Sie den Mauszeiger auf eine Abfrage im Quellcodefenster bewegen, woraufhin ein DataTip eingeblendet wird. Sie können eine LINQ to DataSet Variable kopieren und in das Dialogfeld Überwachungsfenster oder schnell Überwachung einfügen. In LINQ to DataSet wird eine Abfrage nicht ausgewertet, wenn Sie erstellt oder deklariert wird, sondern nur, wenn die Abfrage ausgeführt wird. Dies wird als *verzögerte Ausführung*bezeichnet. Deshalb besitzt die Abfragevariable erst nach der Auswertung einen Wert. Weitere Informationen finden Sie unter [Abfragen in LINQ to DataSet](queries-in-linq-to-dataset.md).  
  
 Der Debugger muss eine Abfrage auswerten, um die Abfrageergebnisse anzeigen zu können. Diese implizite Auswertung tritt auf, wenn Sie ein LINQ to DataSet Abfrageergebnis im Debugger anzeigen, und Sie hat einige Auswirkungen, die Sie berücksichtigen sollten. Jede Auswertung der Abfrage dauert einige Zeit. Das Erweitern des Ergebnisknotens nimmt ebenfalls Zeit in Anspruch. Bei einigen Abfragen kann eine wiederholte Auswertung zu beträchtlichen Leistungseinbußen führen. Die Auswertung einer Abfrage kann auch dazu führen, dass der Datenwert oder Zustand des Programms geändert wird. Nicht alle Abfragen verfügen über Nebeneffekte. Um festzustellen, ob eine Abfrage ohne Nebeneffekte sicher ausgewertet werden kann, sollten Sie sich den Code verdeutlichen, durch den die Abfrage implementiert wird. Weitere Informationen finden Sie unter [Nebeneffekte und Ausdrücke](/previous-versions/visualstudio/visual-studio-2013/a7a250bs(v=vs.120)).  
  
## <a name="edit-and-continue"></a>Bearbeiten und Fortfahren  

 "Bearbeiten und Fortfahren" unterstützt keine Änderungen an LINQ to DataSet Abfragen. Wenn Sie während einer Debugsitzung eine LINQ to DataSet Anweisung hinzufügen, entfernen oder ändern, wird ein Dialogfeld angezeigt, in dem Sie darüber informiert werden, dass die Änderung von bearbeiten und Fortfahren nicht unterstützt wird. An diesem Punkt können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und eine neue Sitzung mit dem bearbeiteten Code starten.  
  
 Außerdem wird durch Bearbeiten und Fortfahren das Ändern des Typs oder des Werts einer Variablen, die in einer LINQ to DataSet Anweisung verwendet wird, nicht unterstützt. Auch hier können Sie entweder die Änderungen rückgängig machen oder die Debugsitzung beenden und neu starten.  
  
 In Visual c# in Visual Studio können Sie "Bearbeiten und Fortfahren" nicht für Code in einer Methode verwenden, die eine LINQ to DataSet Abfrage enthält.  
  
 In Visual Basic in Visual Studio können Sie "Bearbeiten und Fortfahren" für nicht LINQ to DataSet Code verwenden, auch in einer Methode, die eine LINQ to DataSet Abfrage enthält. Sie können Code vor der LINQ to DataSet-Anweisung hinzufügen oder entfernen, auch wenn sich die Änderungen auf die Zeilennummer der LINQ to DataSet Abfrage auswirken. Die Visual Basic debuggingdarstellung für nicht LINQ to DataSet Code bleibt identisch mit dem, bevor LINQ to DataSet eingeführt wurde. Es ist jedoch nicht möglich, eine LINQ to DataSet Abfrage zu ändern, hinzuzufügen oder zu entfernen, es sei denn, Sie deaktivieren das Debugging, um die Änderungen anzuwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von verwaltetem Code](/visualstudio/debugger/debugging-managed-code)
- [Programmierhandbuch](programming-guide-linq-to-dataset.md)
