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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 543ea3d1a0f767a10b36e040155e7e9304aca5a9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="transaction-support"></a><span data-ttu-id="13246-102">Transaktionsunterstützung</span><span class="sxs-lookup"><span data-stu-id="13246-102">Transaction Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="13246-103">unterstützt drei unterschiedliche Transaktionsmodelle.</span><span class="sxs-lookup"><span data-stu-id="13246-103"> supports three distinct transaction models.</span></span> <span data-ttu-id="13246-104">Nachfolgend werden diese Modelle in der Reihenfolge der durchgeführten Prüfungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="13246-104">The following lists these models in the order of checks performed.</span></span>  
  
## <a name="explicit-local-transaction"></a><span data-ttu-id="13246-105">Explizite lokale Transaktion</span><span class="sxs-lookup"><span data-stu-id="13246-105">Explicit Local Transaction</span></span>  
 <span data-ttu-id="13246-106">Wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen und ist die <xref:System.Data.Linq.DataContext.Transaction%2A>-Eigenschaft auf eine (`IDbTransaction`-) Transaktion festgelegt, erfolgt der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>-Aufruf im Kontext der gleichen Transaktion.</span><span class="sxs-lookup"><span data-stu-id="13246-106">When <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called, if the <xref:System.Data.Linq.DataContext.Transaction%2A> property is set to a (`IDbTransaction`) transaction, the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> call is executed in the context of the same transaction.</span></span>  
  
 <span data-ttu-id="13246-107">Es ist Ihre Aufgabe, die Transaktion nach erfolgreicher Ausführung zu bestätigen oder rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="13246-107">It is your responsibility to commit or rollback the transaction after successful execution of the transaction.</span></span> <span data-ttu-id="13246-108">Die Verbindung, die der Transaktion entspricht, muss zur Verbindung passen, die zum Erstellen des <xref:System.Data.Linq.DataContext> verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="13246-108">The connection corresponding to the transaction must match the connection used for constructing the <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="13246-109">Eine Ausnahme wird ausgelöst, wenn eine andere Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13246-109">An exception is thrown if a different connection is used.</span></span>  
  
## <a name="explicit-distributable-transaction"></a><span data-ttu-id="13246-110">Explizit verteilbare Transaktion</span><span class="sxs-lookup"><span data-stu-id="13246-110">Explicit Distributable Transaction</span></span>  
 <span data-ttu-id="13246-111">Sie können Aufrufen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] APIs (einschließlich aber nicht beschränkt auf <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) im Rahmen einer aktiven <xref:System.Transactions.Transaction>.</span><span class="sxs-lookup"><span data-stu-id="13246-111">You can call [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] APIs (including but not limited to <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) in the scope of an active <xref:System.Transactions.Transaction>.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="13246-112">erkennt, dass der Aufruf im Rahmen einer Transaktion und eine neue Transaktion nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="13246-112"> detects that the call is in the scope of a transaction and does not create a new transaction.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="13246-113">vermeidet auch, die Verbindung in diesem Fall zu schließen.</span><span class="sxs-lookup"><span data-stu-id="13246-113"> also avoids closing the connection in this case.</span></span> <span data-ttu-id="13246-114">Sie können Abfragen und <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im Kontext einer solchen Transaktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="13246-114">You can perform query and <xref:System.Data.Linq.DataContext.SubmitChanges%2A> executions in the context of such a transaction.</span></span>  
  
## <a name="implicit-transaction"></a><span data-ttu-id="13246-115">Implizite Transaktion</span><span class="sxs-lookup"><span data-stu-id="13246-115">Implicit Transaction</span></span>  
 <span data-ttu-id="13246-116">Beim Aufruf <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] geprüft, ob der Aufruf im Rahmen einer <xref:System.Transactions.Transaction> oder, wenn die `Transaction` Eigenschaft (`IDbTransaction`) auf eine vom Benutzer gestartete lokale Transaktion festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="13246-116">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] checks to see whether the call is in the scope of a <xref:System.Transactions.Transaction> or if the `Transaction` property (`IDbTransaction`) is set to a user-started local transaction.</span></span> <span data-ttu-id="13246-117">Wenn es keine Transaktion gefunden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] startet eine lokale Transaktion (`IDbTransaction`) und verwendet, um die Ausführung der erzeugten SQL-Befehle.</span><span class="sxs-lookup"><span data-stu-id="13246-117">If it finds neither transaction, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a local transaction (`IDbTransaction`) and uses it to execute the generated SQL commands.</span></span> <span data-ttu-id="13246-118">Wurden alle SQL-Befehle erfolgreich abgeschlossen, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] führt einen Commit für die lokale Transaktion und gibt zurück.</span><span class="sxs-lookup"><span data-stu-id="13246-118">When all SQL commands have been successfully completed, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] commits the local transaction and returns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13246-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13246-119">See Also</span></span>  
 [<span data-ttu-id="13246-120">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="13246-120">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="13246-121">Vorgehensweise: Einklammern von Datenübergaben durch das Verwenden von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="13246-121">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
