---
title: Transaktionsunterstützung
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: 1449f4d10d0feeec47ac17ffda91acb3e0da17ea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202200"
---
# <a name="transaction-support"></a>Transaktionsunterstützung

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt drei verschiedene Transaktions Modelle. Nachfolgend werden diese Modelle in der Reihenfolge der durchgeführten Prüfungen aufgelistet.  
  
## <a name="explicit-local-transaction"></a>Explizite lokale Transaktion  

 Wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen und ist die <xref:System.Data.Linq.DataContext.Transaction%2A>-Eigenschaft auf eine (`IDbTransaction`-) Transaktion festgelegt, erfolgt der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>-Aufruf im Kontext der gleichen Transaktion.  
  
 Es ist Ihre Aufgabe, die Transaktion nach erfolgreicher Ausführung der Transaktion zu bestätigen oder rückgängig zu machen. Die Verbindung, die der Transaktion entspricht, muss zur Verbindung passen, die zum Erstellen des <xref:System.Data.Linq.DataContext> verwendet wurde. Eine Ausnahme wird ausgelöst, wenn eine andere Verbindung verwendet wird.  
  
## <a name="explicit-distributable-transaction"></a>Explizit verteilbare Transaktion  

 Sie können im Gültigkeits [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Bereich einer aktiven APIs (einschließlich, aber nicht beschränkt auf) aufzurufen <xref:System.Data.Linq.DataContext.SubmitChanges%2A> <xref:System.Transactions.Transaction> . [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erkennt, dass der-Befehl im Gültigkeitsbereich einer Transaktion liegt, und erstellt keine neue Transaktion. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verhindert auch das Schließen der Verbindung in diesem Fall. Sie können Abfragen und <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im Kontext einer solchen Transaktion ausführen.  
  
## <a name="implicit-transaction"></a>Implizite Transaktion  

 Wenn Sie aufzurufen <xref:System.Data.Linq.DataContext.SubmitChanges%2A> , wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] von überprüft, ob der-Befehl im Gültigkeitsbereich einer liegt <xref:System.Transactions.Transaction> oder ob die `Transaction` -Eigenschaft ( `IDbTransaction` ) auf eine vom Benutzer gestartete lokale Transaktion festgelegt ist. Wenn keine Transaktion gefunden wird, wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] von eine lokale Transaktion ( `IDbTransaction` ) gestartet und zum Ausführen der generierten SQL-Befehle verwendet. Wenn alle SQL-Befehle erfolgreich abgeschlossen wurden, führt einen Commit für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die lokale Transaktion aus und gibt zurück.  
  
## <a name="see-also"></a>Weitere Informationen

- [Hintergrundinformationen](background-information.md)
- [Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen](how-to-bracket-data-submissions-by-using-transactions.md)
