---
title: Transaktionsgrundlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 353f4ee2-e6bf-4b1c-b1c8-385fc8a486c0
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a21de968f5fbd241bd71169cf9f444b84c05b599
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="transaction-fundamentals"></a>Transaktionsgrundlagen
In Transaktionen werden mehrere Aufgaben zusammengefasst. Stellen Sie sich z.&#160;B. vor, dass eine Anwendung zwei Aufgaben ausführt. Zuerst erstellt sie eine neue Tabelle in einer Datenbank. Danach ruft sie ein spezielles Objekt auf, um Daten zu sammeln, zu formatieren und in die neue Tabelle einzufügen. Diese beiden Aufgaben sind aufeinander bezogen und sogar voneinander abhängig, da nur dann eine neue Tabelle erstellt werden sollte, wenn diese mit Daten gefüllt werden kann. Wenn beide Aufgaben im Bereich einer Transaktion ausgeführt werden, wird die zwischen ihnen bestehende Beziehung verstärkt. Falls die zweite Aufgabe fehlschlägt, wird die erste Aufgabe bis zu einem Punkt rückgängig gemacht, der vor der Erstellung der Tabelle liegt.  
  
 Um ein vorhersagbares Verhalten sicherzustellen, müssen alle Transaktionen die vier grundlegenden Eigenschaften Unteilbarkeit, Konsistenz, Isolation und Dauerhaftigkeit besitzen.. Diese Eigenschaften verstärken der Rolle termingebundener Transaktionen als Projekte, die entweder ganz oder gar nicht ausgeführt werden. Weitere Informationen zu den ACID-Eigenschaften, finden Sie unter [ACID-Eigenschaften](http://go.microsoft.com/fwlink/?LinkId=98791). Durch diese vier Eigenschaften wird also garantiert, dass ein Satz verwandter Aufgaben entweder insgesamt erfolgreich ausgeführt wird oder fehlschlägt. In der Terminologie der Transaktionsverarbeitung heißt dies, dass für eine Transaktion entweder ein Commit oder ein Rollback durchgeführt wird. Damit für eine Transaktion ein Commit ausgeführt werden kann, müssen alle Teilnehmer garantieren, ausschließlich permanente Änderungen an Daten vorzunehmen. Änderungen müssen auch im Fall von Systemausfällen oder anderen unvorhergesehenen Ereignissen dauerhaft sein. Wenn auch nur ein einziger Teilnehmer dies nicht garantieren kann, schlägt die gesamte Transaktion fehl. Alle Änderungen an Daten, die im Bereich der Transaktion vorgenommen wurden, werden bis zu einem bestimmten definierten Punkt rückgängig gemacht.  
  
 Eine Transaktion kann auf eine einzelne Datenressource beschränkt werden, z.&#160;B. eine Datenbank oder eine Meldungswarteschlange. In diesem Szenario wird die lokale Transaktion vom dem in <xref:System.Transactions> verfügbaren Transaktions-Manager verwaltet, Da sie von der Datenressource gesteuert werden, sind diese Transaktionen effizient und leicht zu verwalten.  
  
 Transaktionen können auch mehrere Datenressourcen umfassen. Verteilte Transaktionen versetzen Sie in die Lage, verschiedene Operationen, die in unterschiedlichen Systemen ausgeführt werden, in einer Alles-oder-Nichts-Aktion zusammenzufassen. In diesem Szenario werden die Transaktionen vom Microsoft Distributed Transaction Coordinator (MSDTC) koordiniert, der auf jedem System vorhanden ist.  
  
 Wenn Sie mithilfe der in <xref:System.Transactions> verfügbaren Klassen eine Transaktionsanwendung entwickeln, müssen Sie weder um den erforderlichen Typ von Transaktion noch um den benötigten Transaktions-Manager Gedanken machen. Die <xref:System.Transactions>-Infrastruktur verwaltet diese automatisch für Sie.  
  
 Beim Erstellen einer Transaktion können Sie die Isolationsstufe angeben, die für die Transaktion gelten soll. Die durch die <xref:System.Transactions.IsolationLevel>-Klasse definierte Isolationsstufe einer Transaktion bestimmt, über welche Zugriffsebene auf die von der Transaktion betroffenen Daten andere Transaktionen verfügen.  
  
 Sie können mithilfe von ADO.NET, Transaktionen erstellen <xref:System.EnterpriseServices>, oder das transaktionsprogrammierungsmodell durch die <xref:System.Transactions> Namespace. Die [Features von System.Transactions](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md) Thema wird erläutert, die Funktionen, die Sie verwenden können, zum Schreiben einer transaktionsanwendung mit der <xref:System.Transactions> Namespace.  
  
## <a name="see-also"></a>Siehe auch  
 [Von System.Transactions bereitgestellte Funktionen](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)
