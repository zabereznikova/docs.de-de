---
title: "Transaktionsunterstützung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7c1d438a83f090795a158ade1dfdbb7d2b2df863
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="transaction-support"></a>Transaktionsunterstützung
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]unterstützt drei unterschiedliche Transaktionsmodelle. Nachfolgend werden diese Modelle in der Reihenfolge der durchgeführten Prüfungen aufgelistet.  
  
## <a name="explicit-local-transaction"></a>Explizite lokale Transaktion  
 Wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen und ist die <xref:System.Data.Linq.DataContext.Transaction%2A>-Eigenschaft auf eine (`IDbTransaction`-) Transaktion festgelegt, erfolgt der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>-Aufruf im Kontext der gleichen Transaktion.  
  
 Es ist Ihre Aufgabe, die Transaktion nach erfolgreicher Ausführung zu bestätigen oder rückgängig zu machen. Die Verbindung, die der Transaktion entspricht, muss zur Verbindung passen, die zum Erstellen des <xref:System.Data.Linq.DataContext> verwendet wurde. Eine Ausnahme wird ausgelöst, wenn eine andere Verbindung verwendet wird.  
  
## <a name="explicit-distributable-transaction"></a>Explizit verteilbare Transaktion  
 Sie können Aufrufen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] APIs (einschließlich aber nicht beschränkt auf <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) im Rahmen einer aktiven <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]erkennt, dass der Aufruf im Rahmen einer Transaktion und eine neue Transaktion nicht erstellt. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]vermeidet auch, die Verbindung in diesem Fall zu schließen. Sie können Abfragen und <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im Kontext einer solchen Transaktion ausführen.  
  
## <a name="implicit-transaction"></a>Implizite Transaktion  
 Beim Aufruf <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] geprüft, ob der Aufruf im Rahmen einer <xref:System.Transactions.Transaction> oder, wenn die `Transaction` Eigenschaft (`IDbTransaction`) auf eine vom Benutzer gestartete lokale Transaktion festgelegt ist. Wenn es keine Transaktion gefunden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] startet eine lokale Transaktion (`IDbTransaction`) und verwendet, um die Ausführung der erzeugten SQL-Befehle. Wurden alle SQL-Befehle erfolgreich abgeschlossen, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] führt einen Commit für die lokale Transaktion und gibt zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Vorgehensweise: Einklammern von Datenübergaben durch das Verwenden von Transaktionen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
