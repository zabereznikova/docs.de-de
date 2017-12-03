---
title: Implementieren eines Ressourcen-Managers
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5c153f6-4419-49e3-a5f1-a50ae4c81bf3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d9fe72090de3722137c2b0c2190c11f190be5fbc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="implementing-a-resource-manager"></a>Implementieren eines Ressourcen-Managers
Jede in einer Transaktion verwendete Ressource wird von einem Ressourcen-Manager (RM) verwaltet, dessen Aktionen von einem Transaktions-Manager (TM) koordiniert werden. RMs arbeiten mit dem TM zusammen, um der Anwendung die Unteilbarkeit und Isolation zu garantieren. Microsoft SQL Server, dauerhafte Meldungswarteschlangen und speicherinterne Hashtabellen sind Beispiele für Ressourcen-Manager.  
  
 Ein RM verwaltet entweder dauerhafte oder flüchtige Daten. Die Dauerhaftigkeit (oder im Gegensatz dazu die Flüchtigkeit) eines Ressourcen-Managers leitet sich davon ab, ob der Ressourcen-Manager die Wiederherstellung nach einem Fehler unterstützt. Wenn ein RM die Wiederherstellung nach einem Fehler unterstützt, legt er Daten während Phase1 (Vorbereitung) in einem permanenten Speicher ab, damit er sich im Falle eines Ausfalls nach der Wiederherstellung erneut in die Transaktion eintragen und entsprechend den Benachrichtigungen des TM geeignete Aktionen ausführen kann. Im Allgemeinen verwalten flüchtige RMs flüchtige Ressourcen wie beispielsweise eine speicherinterne Datenstruktur (z. B. eine speicherinterne Transaktions-Hashtabelle), und dauerhafte RMs verwalten Ressourcen, die über einen beständigeren Sicherungsspeicher verfügen (z. B. eine Datenbank, deren Sicherungsspeicher ein Datenträger ist).  
  
 Damit eine Ressource an einer Transaktion teilnehmen kann, muss sie sich in die Transaktion eintragen. Die <xref:System.Transactions.Transaction> Klasse definiert einen Satz von Methoden, deren Namen beginnen mit **eintragen** , die diese Funktionalität bereitstellen. Die verschiedenen **eintragen** Methoden entsprechen den verschiedenen Typen von Eintragung, die möglicherweise ein Ressourcen-Manager. Die <xref:System.Transactions.Transaction.EnlistVolatile%2A>-Methoden werden für flüchtige Ressourcen und die <xref:System.Transactions.Transaction.EnlistDurable%2A>-Methode wird für dauerhafte Ressourcen verwendet. Nachdem auf der Grundlage der Dauerhaftigkeit Ihrer Ressource entschieden wurde, ob die <xref:System.Transactions.Transaction.EnlistDurable%2A>-Methode oder die <xref:System.Transactions.Transaction.EnlistVolatile%2A>-Methode verwendet wird, sollten Sie Ihre Ressource für die Teilnahme an einem Zweiphasencommit (2PC) eintragen, indem Sie die <xref:System.Transactions.IEnlistmentNotification>-Schnittstelle für Ihren RM implementieren. Weitere Informationen zu 2PC, finden Sie unter [Commit einer Transaktion in Phase hat und mehreren Phasen bestehender](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md).  
  
 Indem sich der RM einträgt, stellt er sicher, dass er Rückrufe des TM erhält, wenn der Transaktionscommit ausgeführt wurde oder fehlgeschlagen ist. Es gibt eine Instanz von <xref:System.Transactions.IEnlistmentNotification> pro Eintragung. In der Regel gibt es eine Eintragung pro Transaktion, jedoch kann ein RM sich mehrmals in dieselbe Transaktion eintragen.  
  
 Nach Eintragung reagiert der RM auf die Anforderungen der Transaktion. Ein dauerhafter RM speichert genügend Informationen, um die Änderungen einer Transaktion an den vom RM verwalteten Ressourcen rückgängig zu machen oder zu wiederholen. Es gibt viele Wege, dies zu erreichen: Zwei gängige Verfahren sind das Aufzeichnen von Datenversionen oder das Führen eines Änderungsprotokolls.  
  
 Wenn die Anwendung einen Commit für die Transaktion ausführt, initiiert der TM das Zweiphasencommit-Protokoll. Der TM fragt zuerst jeden eingetragenen RM, ob er vorbereitet ist, einen Commit für die Transaktion auszuführen. Der RM muss sich auf den Commit vorbereiten, d. h. er bereitet sich vor, entweder einen Commit für die Transaktion auszuführen oder den Vorgang abzubrechen.  
  
 Während der Vorbereitungsphase erfasst der dauerhafte RM die alten und neuen Daten in einem permanenten Speicher, damit der RM sie im Falle eines Systemausfalls wiederherstellen kann. Wenn der RM die Vorbereitung vollenden konnte, informiert er den TM über seine Entscheidung, ob ein Commit für die Transaktion ausgeführt oder die Transaktion abgebrochen werden soll. Teilt einer der RMs das Fehlschlagen der Vorbereitung mit, sendet der TM einen Rollback-Befehl an alle RMs und informiert die Anwendung über das Fehlschlagen des Commit.  
  
 Nach der Vorbereitung muss ein RM warten, bis er in Phase 2 einen Commit- oder Abbruchrückruf vom TM erhält. In der Regel werden das gesamte Vorbereitungsprotokoll und das Commitprotokoll im Bruchteil einer Sekunde ausgeführt. Wenn es zu System- oder Kommunikationsfehlern kommt, kann es Minuten oder gar Stunden dauern, bis die Commit- oder Abbruchbenachrichtigung ankommt. Während dieses Zeitraums bleibt der RM im Unklaren über das Ergebnis der Transaktion. Er weiß nicht, ob ein Commit für die Transaktion ausgeführt oder die Transaktion abgebrochen wurde. Während dieser Zeit der Ungewissheit, lässt der RM die Daten geändert, indem er die Transaktion sperrt. Auf diese Weise werden die Änderungen von anderen Transaktionen isoliert.  
  
 Wenn ein RM ausfällt, werden alle seine eingetragenen Transaktionen abgebrochen, ausgenommen diejenigen, die vor dem Fehler vorbereitet wurden oder deren Commit vor dem Fehler zu Ende geführt wurde. Wenn ein dauerhafter RM neu startet, rekonstruiert er den Commitzustand der von ihm verwalteten Ressourcen, indem er die Informationen, die in der Vorbereitungsphase geschrieben wurden, abruft. Danach führt er entsprechend diesen Informationen einen Commit dieser Transaktionen aus oder bricht sie ab.  
  
 Zusammenfassend kann man sagen, dass das Zweiphasencommit-Protokoll und die RMs zusammen dafür sorgen, dass die Transaktionen unteilbar und dauerhaft sind.  
  
 Die <xref:System.Transactions.Transaction>-Klasse stellt die <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>-Methode auch bereit, um eine Erweiterbare Einphaseneintragung (PSPE) vorzunehmen. Dadurch wird es einem dauerhaften RM ermöglicht, eine Transaktion zu hosten und zu "besitzen", die später bei Bedarf eskaliert werden kann, um von MSDTC verwaltet zu werden. Weitere Informationen dazu finden Sie unter [Optimierung mit einzelnen Phase Commit und heraufstufbare Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 Die gewöhnlich von einem Ressourcen-Manager ausgeführten Schritte werden in den folgenden Themen umrissen.  
  
 [Eintragen von Ressourcen als Teilnehmer in einer Transaktion](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)  
  
 Beschreibt, wie eine dauerhafte oder flüchtige Ressource sich in eine Transaktion eintragen kann.  
  
 [Ausführen eines Commits für eine Transaktion in der Phase hat und mehreren Phasen bestehender](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md)  
  
 Beschreibt, wie ein Ressourcen-Manager auf eine Commitbenachrichtigung reagiert und den Commit vorbereitet.  
  
 [Ausführen der Wiederherstellung](../../../../docs/framework/data/transactions/performing-recovery.md)  
  
 Beschreibt, wie ein dauerhafter Ressourcen-Manager nach einem Fehler die Wiederherstellung durchführt.  
  
 [Sicherheit Vertrauensebenen in den Zugriff auf Ressourcen](../../../../docs/framework/data/transactions/security-trust-levels-in-accessing-resources.md)  
  
 Beschreibt, wie die drei Vertrauensebenen für System.Transactions den Zugriff auf die Typen von Ressourcen einschränkt, die <xref:System.Transactions> verfügbar macht.  
  
 [Optimierung mit einzelnen Phase Commit und heraufstufbare einzelnen Phase-Benachrichtigung](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)  
  
 Beschreibt Optimierungsvorgehensweisen für die Implementierung von Ressourcen-Managern.
