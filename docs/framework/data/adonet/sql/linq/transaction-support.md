---
title: Transaktionsunterstützung
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: 9c7128ef432fa609b8d628bc74caebe790058ede
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792276"
---
# <a name="transaction-support"></a>Transaktionsunterstützung
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]unterstützt drei verschiedene Transaktions Modelle. Nachfolgend werden diese Modelle in der Reihenfolge der durchgeführten Prüfungen aufgelistet.  
  
## <a name="explicit-local-transaction"></a>Explizite lokale Transaktion  
 Wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen und ist die <xref:System.Data.Linq.DataContext.Transaction%2A>-Eigenschaft auf eine (`IDbTransaction`-) Transaktion festgelegt, erfolgt der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>-Aufruf im Kontext der gleichen Transaktion.  
  
 Es ist Ihre Aufgabe, die Transaktion nach erfolgreicher Ausführung der Transaktion zu bestätigen oder rückgängig zu machen. Die Verbindung, die der Transaktion entspricht, muss zur Verbindung passen, die zum Erstellen des <xref:System.Data.Linq.DataContext> verwendet wurde. Eine Ausnahme wird ausgelöst, wenn eine andere Verbindung verwendet wird.  
  
## <a name="explicit-distributable-transaction"></a>Explizit verteilbare Transaktion  
 Sie können im [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Gültigkeitsbereich einer aktiven <xref:System.Transactions.Transaction>APIs ( <xref:System.Data.Linq.DataContext.SubmitChanges%2A>einschließlich, aber nicht beschränkt auf) aufzurufen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]erkennt, dass der-Befehl im Gültigkeitsbereich einer Transaktion liegt, und erstellt keine neue Transaktion. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]verhindert auch das Schließen der Verbindung in diesem Fall. Sie können Abfragen und <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im Kontext einer solchen Transaktion ausführen.  
  
## <a name="implicit-transaction"></a>Implizite Transaktion  
 Wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A>aufzurufen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , wird von überprüft, ob der-Befehl im Gültigkeits <xref:System.Transactions.Transaction> Bereich einer liegt `Transaction` oder ob`IDbTransaction`die-Eigenschaft () auf eine vom Benutzer gestartete lokale Transaktion festgelegt ist. Wenn keine Transaktion gefunden wird, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird von eine lokale Transaktion`IDbTransaction`() gestartet und zum Ausführen der generierten SQL-Befehle verwendet. Wenn alle SQL-Befehle erfolgreich abgeschlossen wurden, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] führt einen Commit für die lokale Transaktion aus und gibt zurück.  
  
## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](background-information.md)
- [Vorgehensweise: Übermittlungen von Daten mithilfe von Transaktionen](how-to-bracket-data-submissions-by-using-transactions.md)
