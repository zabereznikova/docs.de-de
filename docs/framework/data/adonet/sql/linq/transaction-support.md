---
title: Transaktionsunterstützung
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: f53a6081102991c73543b4cd76365f7e2c0faf89
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517200"
---
# <a name="transaction-support"></a>Transaktionsunterstützung
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt drei unterschiedliche Transaktionsmodelle. Nachfolgend werden diese Modelle in der Reihenfolge der durchgeführten Prüfungen aufgelistet.  
  
## <a name="explicit-local-transaction"></a>Explizite lokale Transaktion  
 Wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen und ist die <xref:System.Data.Linq.DataContext.Transaction%2A>-Eigenschaft auf eine (`IDbTransaction`-) Transaktion festgelegt, erfolgt der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>-Aufruf im Kontext der gleichen Transaktion.  
  
 Es ist Ihre Aufgabe, die Transaktion nach erfolgreicher Ausführung zu bestätigen oder rückgängig zu machen. Die Verbindung, die der Transaktion entspricht, muss zur Verbindung passen, die zum Erstellen des <xref:System.Data.Linq.DataContext> verwendet wurde. Eine Ausnahme wird ausgelöst, wenn eine andere Verbindung verwendet wird.  
  
## <a name="explicit-distributable-transaction"></a>Explizit verteilbare Transaktion  
 Rufen Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] APIs (einschließlich aber nicht beschränkt auf <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) im Rahmen einer aktiven <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erkennt, dass der Aufruf im Rahmen einer Transaktion und eine neue Transaktion keine erstellt. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vermeiden auch in diesem Fall das Schließen der Verbindung ein. Sie können Abfragen und <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im Kontext einer solchen Transaktion ausführen.  
  
## <a name="implicit-transaction"></a>Implizite Transaktion  
 Beim Aufruf <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] überprüft, ob der Aufruf, im Rahmen ist einer <xref:System.Transactions.Transaction> oder, wenn die `Transaction` Eigenschaft (`IDbTransaction`) zu einem Benutzer gestartete lokale Transaktion festgelegt ist. Wenn sie keine Transaktion gefunden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] startet eine lokale Transaktion (`IDbTransaction`) und wird verwendet, um die generierten SQL-Befehle ausführen. Wenn alle SQL-Befehle erfolgreich abgeschlossen haben, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] führt einen Commit für die lokale Transaktion und gibt zurück.  
  
## <a name="see-also"></a>Siehe auch
- [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
