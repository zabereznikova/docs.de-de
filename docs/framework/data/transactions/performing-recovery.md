---
title: "Durchf&#252;hren einer Wiederherstellung  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6dd17bf6-ba42-460a-a44b-8046f52b10d0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Durchf&#252;hren einer Wiederherstellung 
Ein Ressourcen\-Manager erleichtert das Auflösen dauerhafter Eintragungen in einer Transaktion, indem er den Transaktionsteilnehmer nach einem Fehler der Ressource neu einträgt.  
  
## Der Wiederherstellungsprozess  
 Um eine Ressource dauerhaft einzutragen \(wird durch eine Implementierung der <xref:System.Transactions.IEnlistmentNotification>\-Schnittstelle beschrieben\), damit sie später bei Bedarf wiederhergestellt werden kann, müssen Sie die <xref:System.Transactions.Transaction.EnlistDurable%2A>\-Methode aufrufen.Darüber hinaus müssen Sie die <xref:System.Transactions.Transaction.EnlistDurable%2A>\-Methode mit einem Ressourcen\-Manager\-Bezeichner ausstatten \(<xref:System.Guid>\), der dazu verwendet wird, den Teilnehmer an einer Transaktion im Falle eines Ressourcenfehlers eindeutig zu kennzeichnen.Aus diesem Grund muss die <xref:System.Guid>, die dem anfänglichen Eintragungsaufruf bekannt gegeben wird, mit dem *resourceManagerIdentifier*\-Parameter im <xref:System.Transactions.TransactionManager.Reenlist%2A>\-Aufruf während der Wiederherstellung identisch sein.Andernfalls wird eine <xref:System.Transactions.TransactionException>\-Ausnahme ausgelöst.Weitere Informationen zu permanenten Eintragungen finden Sie unter [Eintragen von Ressourcen als Teilnehmer an einer Transaktion ](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md).  
  
 Wenn der von Ihnen implementierte dauerhafte Ressourcen\-Manager in der Vorbereitungsphase \(Phase 1\) des 2PC\-Protokolls die <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>\-Benachrichtigung erhält, muss er seinen Vorbereitungsdatensatz während dieser Phase protokollieren.Der Datensatz muss alle notwendigen Informationen enthalten, um den Commit der Transaktion auszuführen.Auf den Vorbereitungsdatensatz kann später während der Wiederherstellung durch Abrufen der <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>\-Eigenschaft des *preparingEnlistment*\-Rückrufs zugegriffen werden.Die Datensatzprotokollierung muss nicht innerhalb der <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>\-Methode durchgeführt werden, da der RM dies mit einem Arbeitsthread erledigen kann.  
  
 Der Wiederherstellungsprozess läuft in zwei Schritten ab:  
  
### Schritt \- Erneute Eintragung  
 Der Ressourcen\-Manager untersucht den Vorbereitungsdatensatz jeder Eintragung, die zweifelhaft ist.Dies geschieht durch Überprüfung der <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>\-Eigenschaft des <xref:System.Transactions.PreparingEnlistment>\-Aufrufs, der in der <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>\-Benachrichtigung während Phase 1 an den Ressourcen\-Manager übergeben wird.  
  
 Für jede Eintragung, die es untersucht, ruft er <xref:System.Transactions.TransactionManager.Reenlist%2A> für den Transaktions\-Manager auf.Diese Methode gibt eine eindeutige <xref:System.Guid> weiter, die den Ressourcen\-Manager und die Informationen der Eintragung in einem Bytearray identifiziert.Es wird ein neues <xref:System.Transactions.Enlistment>\-Objekt zurückgegeben.Schlägt die erneute Eintragung mit einer Ausnahme fehl, muss der Ressourcen\-Manager zu einem späteren Zeitpunkt einen neuen Versuch unternehmen.  
  
 Rufen Sie die <xref:System.Transactions.TransactionManager.Reenlist%2A>\-Methode nur auf, wenn ein Ressourcen\-Manager nach einem Fehler neu gestartet wird.Tragen Sie außerdem nur nicht aufgelöste Transaktionen erneut ein, die von einem Ressourcen\-Manager während der anfänglichen Vorbereitungsphase eines Zweiphasencommits protokolliert wurden.Bei jedem Versuch, diese Methode zu unzulässigen Zeitpunkten aufzurufen, können falsche Ergebnisse erzeugt werden.  
  
 Wenn ein Teilnehmer mit dieser Methode neu eingetragen wird, werden die <xref:System.Transactions.IEnlistmentNotification>\-Methoden aus Phase 2, die dem Transaktionsergebnis entsprechen \(d. h. <xref:System.Transactions.IEnlistmentNotification.Commit%2A>, <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> oder <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A>\), aufgerufen.  
  
### Schritt \- Durchführen der Wiederherstellung  
 Wenn alle Neueintragungen erfolgt sind, ruft der Ressourcen\-Manager die <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>\-Methode auf.Diese Methode führt die Wiederherstellung zu Ende und informiert den Transaktions\-Manager darüber, dass der Ressourcen\-Manager über keine weiteren zweifelhaften Transaktionen verfügt.Dadurch garantiert der Ressourcen\-Manager, dass er die <xref:System.Transactions.TransactionManager.Reenlist%2A>\-Methode nicht noch einmal aufruft.  
  
 Ein Ressourcen\-Manager braucht nicht alle zweifelhaften Transaktionen aufzulösen, bevor er Eintragungen in neue Transaktionen vornimmt.Der erste Schritt kann jederzeit ausgeführt werden, nachdem der Ressourcen\-Manager die Verbindung zum Transaktions\-Manager hergestellt hat. Nach Aufrufen von <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> \(Schritt 2\) kann Schritt 1 jedoch nicht erneut ausgeführt werden.Schritt 2 kann mehrmals wiederholt werden, ohne das Ergebnis von Transaktionen zu beeinflussen.