---
title: 'Vorgehensweise: Übergeben von Änderungen an die Datenbank'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
ms.openlocfilehash: 5952cce5469d7a7e13e8b896f91ea1279fd62d8b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197039"
---
# <a name="how-to-submit-changes-to-the-database"></a><span data-ttu-id="a3615-102">Vorgehensweise: Übergeben von Änderungen an die Datenbank</span><span class="sxs-lookup"><span data-stu-id="a3615-102">How to: Submit Changes to the Database</span></span>

<span data-ttu-id="a3615-103">Unabhängig von der Anzahl der Änderungen an Ihren Objekten erfolgen diese Änderungen nur an den Replikaten im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="a3615-103">Regardless of how many changes you make to your objects, changes are made only to in-memory replicas.</span></span> <span data-ttu-id="a3615-104">Sie haben die eigentlichen Daten in der Datenbank nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="a3615-104">You have made no changes to the actual data in the database.</span></span> <span data-ttu-id="a3615-105">Ihre Änderungen werden erst dann zum Server gesendet, wenn Sie explizit <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im <xref:System.Data.Linq.DataContext> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a3615-105">Your changes are not transmitted to the server until you explicitly call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="a3615-106">Bei diesem Aufruf versucht der <xref:System.Data.Linq.DataContext>, die Änderungen in entsprechende SQL-Befehle zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="a3615-106">When you make this call, the <xref:System.Data.Linq.DataContext> tries to translate your changes into equivalent SQL commands.</span></span> <span data-ttu-id="a3615-107">Sie können Ihre eigene benutzerdefinierte Logik verwenden, um diese Aktionen außer Kraft zu setzen, aber die Reihenfolge der Übermittlung wird von einem Dienst des, der <xref:System.Data.Linq.DataContext> als *Änderungs Prozessor*bezeichnet wird, orchestriert.</span><span class="sxs-lookup"><span data-stu-id="a3615-107">You can use your own custom logic to override these actions, but the order of submission is orchestrated by a service of the <xref:System.Data.Linq.DataContext> known as the *change processor*.</span></span> <span data-ttu-id="a3615-108">Die Ereignisse finden in der folgenden Reihenfolge statt:</span><span class="sxs-lookup"><span data-stu-id="a3615-108">The sequence of events is as follows:</span></span>  
  
1. <span data-ttu-id="a3615-109">Wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen, prüft [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] den Satz unbekannter Objekte, um zu ermitteln, ob diesen neue Instanzen hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="a3615-109">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examines the set of known objects to determine whether new instances have been attached to them.</span></span> <span data-ttu-id="a3615-110">Ist dies der Fall, werden diese Instanzen dem Satz verfolgter Objekte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a3615-110">If they have, these new instances are added to the set of tracked objects.</span></span>  
  
2. <span data-ttu-id="a3615-111">Alle Objekte mit ausstehenden Änderungen werden in eine Objektsequenz gegliedert, die auf den Abhängigkeiten zwischen den Objekten basiert.</span><span class="sxs-lookup"><span data-stu-id="a3615-111">All objects that have pending changes are ordered into a sequence of objects based on the dependencies between them.</span></span> <span data-ttu-id="a3615-112">Objekte, deren Änderungen von anderen Objekten abhängen, werden nach ihren Abhängigkeiten eingeordnet.</span><span class="sxs-lookup"><span data-stu-id="a3615-112">Objects whose changes depend on other objects are sequenced after their dependencies.</span></span>  
  
3. <span data-ttu-id="a3615-113">Direkt vor der Übergabe der eigentlichen Änderungen startet [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine Transaktion, um die Reihe einzelner Befehle zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="a3615-113">Immediately before any actual changes are transmitted, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a transaction to encapsulate the series of individual commands.</span></span>  
  
4. <span data-ttu-id="a3615-114">Die Änderungen an den Objekten werden nacheinander in SQL-Befehle übersetzt und an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="a3615-114">The changes to the objects are translated one by one to SQL commands and sent to the server.</span></span>  
  
 <span data-ttu-id="a3615-115">Zu diesem Zeitpunkt führen Fehler, die von der Datenbank erkannt werden, zum Stoppen der Übergabe, und eine Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a3615-115">At this point, any errors detected by the database cause the submission process to stop, and an exception is raised.</span></span> <span data-ttu-id="a3615-116">Alle Änderungen an der Datenbank werden rückgängig gemacht, als ob keine Übergabe stattgefunden hätte.</span><span class="sxs-lookup"><span data-stu-id="a3615-116">All changes to the database are rolled back as if no submissions ever occurred.</span></span> <span data-ttu-id="a3615-117">Der <xref:System.Data.Linq.DataContext> verfügt weiterhin über eine vollständige Aufzeichnung aller Änderungen.</span><span class="sxs-lookup"><span data-stu-id="a3615-117">The <xref:System.Data.Linq.DataContext> still has a full recording of all changes.</span></span> <span data-ttu-id="a3615-118">Daher können Sie versuchen, das Problem zu beheben und <xref:System.Data.Linq.DataContext.SubmitChanges%2A> wie im folgenden Codebeispiel erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a3615-118">You can therefore try to correct the problem and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> again, as in the code example that follows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3615-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3615-119">Example</span></span>  

 <span data-ttu-id="a3615-120">Wird die Transaktion rund um die Übergabe erfolgreich abgeschlossen, akzeptiert der <xref:System.Data.Linq.DataContext> die Änderungen an den Objekten, indem er die Informationen zur Änderungsverfolgung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a3615-120">When the transaction around the submission is completed successfully, the <xref:System.Data.Linq.DataContext> accepts the changes to the objects by ignoring the change-tracking information.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a3615-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3615-121">See also</span></span>

- [<span data-ttu-id="a3615-122">Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten</span><span class="sxs-lookup"><span data-stu-id="a3615-122">How to: Detect and Resolve Conflicting Submissions</span></span>](how-to-detect-and-resolve-conflicting-submissions.md)
- [<span data-ttu-id="a3615-123">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="a3615-123">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="a3615-124">Herunterladen von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="a3615-124">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="a3615-125">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="a3615-125">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
