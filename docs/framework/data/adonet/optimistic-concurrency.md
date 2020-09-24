---
title: Optimistische Nebenläufigkeit
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
ms.openlocfilehash: 681044a9d905f052516ba240e25ffff84928e58e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166637"
---
# <a name="optimistic-concurrency"></a><span data-ttu-id="a5275-102">Optimistische Nebenläufigkeit</span><span class="sxs-lookup"><span data-stu-id="a5275-102">Optimistic Concurrency</span></span>

<span data-ttu-id="a5275-103">In einer Umgebung mit mehreren Benutzern gibt es zwei Modelle für das Update von Daten in einer Datenbank: das Modell der vollständigen Parallelität und das Modell der eingeschränkten Parallelität.</span><span class="sxs-lookup"><span data-stu-id="a5275-103">In a multiuser environment, there are two models for updating data in a database: optimistic concurrency and pessimistic concurrency.</span></span> <span data-ttu-id="a5275-104">Das <xref:System.Data.DataSet>-Objekt unterstützt die Verwendung der vollständigen Parallelität für lange Aktivitäten, wie bei der Datenfernverarbeitung und der Interaktion mit Daten.</span><span class="sxs-lookup"><span data-stu-id="a5275-104">The <xref:System.Data.DataSet> object is designed to encourage the use of optimistic concurrency for long-running activities, such as remoting data and interacting with data.</span></span>  
  
 <span data-ttu-id="a5275-105">Die eingeschränkte Parallelität umfasst das Sperren von Zeilen an der Datenquelle, damit Benutzer Daten, die andere Benutzer betreffen, nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="a5275-105">Pessimistic concurrency involves locking rows at the data source to prevent other users from modifying data in a way that affects the current user.</span></span> <span data-ttu-id="a5275-106">Wenn ein Benutzer bei einem eingeschränkten Modell eine Aktion ausführt, durch die eine Sperre angewendet wird, können andere Benutzer so lange keine mit der Sperre in Konflikt stehenden Aktionen ausführen, bis der Eigentümer der Sperre diese aufgehoben hat.</span><span class="sxs-lookup"><span data-stu-id="a5275-106">In a pessimistic model, when a user performs an action that causes a lock to be applied, other users cannot perform actions that would conflict with the lock until the lock owner releases it.</span></span> <span data-ttu-id="a5275-107">Dieses Modell wird hauptsächlich in Umgebungen verwendet, in denen häufig Datenkonflikte auftreten, oder in denen der Aufwand von Datensperren geringer ist als der Aufwand für Rollbacks von Transaktionen, die aufgrund von Konflikten durch eine Parallelbearbeitung ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a5275-107">This model is primarily used in environments where there is heavy contention for data, so that the cost of protecting data with locks is less than the cost of rolling back transactions if concurrency conflicts occur.</span></span>  
  
 <span data-ttu-id="a5275-108">Daher erstellt ein Benutzer, der eine Zeile aktualisiert, bei einem Modell für pessimistische Parallelität eine Sperre.</span><span class="sxs-lookup"><span data-stu-id="a5275-108">Therefore, in a pessimistic concurrency model, a user who updates a row establishes a lock.</span></span> <span data-ttu-id="a5275-109">Die Zeile kann erst wieder von einem anderen Benutzer geändert werden, wenn der Benutzer den Updatevorgang für die Zeile abgeschlossen und die Sperre aufgehoben hat.</span><span class="sxs-lookup"><span data-stu-id="a5275-109">Until the user has finished the update and released the lock, no one else can change that row.</span></span> <span data-ttu-id="a5275-110">Aus diesem Grund eignet sich die eingeschränkte Parallelität am besten bei kurzen Sperrfristen wie bei der programmgesteuerten Verarbeitung von Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="a5275-110">For this reason, pessimistic concurrency is best implemented when lock times will be short, as in programmatic processing of records.</span></span> <span data-ttu-id="a5275-111">Die eingeschränkte Parallelität stellt keine flexible Option dar, wenn Benutzer mit Daten interagieren und Datensätze dadurch für einen relativ langen Zeitraum sperren.</span><span class="sxs-lookup"><span data-stu-id="a5275-111">Pessimistic concurrency is not a scalable option when users are interacting with data and causing records to be locked for relatively large periods of time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5275-112">Wenn Sie mehrere Zeilen auf einmal aktualisieren müssen, ermöglicht das Erstellen einer Transaktion ein höheres Maß an Skalierung als das Sperren bei eingeschränkter Parallelität.</span><span class="sxs-lookup"><span data-stu-id="a5275-112">If you need to update multiple rows in the same operation, then creating a transaction is a more scalable option than using pessimistic locking.</span></span>  
  
 <span data-ttu-id="a5275-113">Im Gegensatz dazu sperren Benutzer bei der vollständigen Parallelität keine Zeile, während sie sie lesen.</span><span class="sxs-lookup"><span data-stu-id="a5275-113">By contrast, users who use optimistic concurrency do not lock a row when reading it.</span></span> <span data-ttu-id="a5275-114">Wenn ein Benutzer eine Zeile aktualisieren möchte, muss durch die Anwendung festgestellt werden, ob ein anderer Benutzer die Zeile seit dem Abruf geändert hat.</span><span class="sxs-lookup"><span data-stu-id="a5275-114">When a user wants to update a row, the application must determine whether another user has changed the row since it was read.</span></span> <span data-ttu-id="a5275-115">Die vollständige Parallelität wird im Allgemeinen in Umgebungen mit wenigen Datenkonflikten verwendet.</span><span class="sxs-lookup"><span data-stu-id="a5275-115">Optimistic concurrency is generally used in environments with a low contention for data.</span></span> <span data-ttu-id="a5275-116">Vollständige Parallelität führt zu einer Leistungssteigerung, weil keine Datensätze gesperrt werden müssen, denn für das Sperren von Datensätzen sind zusätzliche Serverressourcen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a5275-116">Optimistic concurrency improves performance because no locking of records is required, and locking of records requires additional server resources.</span></span> <span data-ttu-id="a5275-117">Außerdem ist für die Verwaltung von Datensatzsperren eine ständige Verbindung zum Datenbankserver notwendig.</span><span class="sxs-lookup"><span data-stu-id="a5275-117">Also, in order to maintain record locks, a persistent connection to the database server is required.</span></span> <span data-ttu-id="a5275-118">Da dies beim Modell der vollständigen Parallelität nicht der Fall ist, können Verbindungen zum Server innerhalb eines kürzeren Zeitraums eine Vielzahl von Clients bedienen.</span><span class="sxs-lookup"><span data-stu-id="a5275-118">Because this is not the case in an optimistic concurrency model, connections to the server are free to serve a larger number of clients in less time.</span></span>  
  
 <span data-ttu-id="a5275-119">Beim Modell der vollständigen Parallelität wird dann von einer Verletzung ausgegangen, wenn, nachdem ein Benutzer einen Wert aus der Datenbank empfangen hat, ein anderer Benutzer den Wert ändert, bevor der erste Benutzer den Wert zu ändern versucht hat.</span><span class="sxs-lookup"><span data-stu-id="a5275-119">In an optimistic concurrency model, a violation is considered to have occurred if, after a user receives a value from the database, another user modifies the value before the first user has attempted to modify it.</span></span> <span data-ttu-id="a5275-120">Wie der Server eine Parallelitätsverletzung auflöst, kann am Besten anhand des folgenden Beispiels erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="a5275-120">How the server resolves a concurrency violation is best shown by first describing the following example.</span></span>  
  
 <span data-ttu-id="a5275-121">Die folgenden Tabellen stellen ein Beispiel für eine vollständige Parallelität dar.</span><span class="sxs-lookup"><span data-stu-id="a5275-121">The following tables follow an example of optimistic concurrency.</span></span>  
  
 <span data-ttu-id="a5275-122">Um 13:00 Uhr ruft User1 eine Zeile mit den folgenden Werten aus der Datenbank auf:</span><span class="sxs-lookup"><span data-stu-id="a5275-122">At 1:00 p.m., User1 reads a row from the database with the following values:</span></span>  
  
 <span data-ttu-id="a5275-123">**CustID     LastName     FirstName**</span><span class="sxs-lookup"><span data-stu-id="a5275-123">**CustID     LastName     FirstName**</span></span>  
  
 <span data-ttu-id="a5275-124">101          Smith             Bob</span><span class="sxs-lookup"><span data-stu-id="a5275-124">101          Smith             Bob</span></span>  
  
|<span data-ttu-id="a5275-125">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="a5275-125">Column name</span></span>|<span data-ttu-id="a5275-126">Ursprünglicher Wert</span><span class="sxs-lookup"><span data-stu-id="a5275-126">Original value</span></span>|<span data-ttu-id="a5275-127">Aktueller Wert</span><span class="sxs-lookup"><span data-stu-id="a5275-127">Current value</span></span>|<span data-ttu-id="a5275-128">Wert in Datenbank</span><span class="sxs-lookup"><span data-stu-id="a5275-128">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="a5275-129">CustID</span><span class="sxs-lookup"><span data-stu-id="a5275-129">CustID</span></span>|<span data-ttu-id="a5275-130">101</span><span class="sxs-lookup"><span data-stu-id="a5275-130">101</span></span>|<span data-ttu-id="a5275-131">101</span><span class="sxs-lookup"><span data-stu-id="a5275-131">101</span></span>|<span data-ttu-id="a5275-132">101</span><span class="sxs-lookup"><span data-stu-id="a5275-132">101</span></span>|  
|<span data-ttu-id="a5275-133">LastName</span><span class="sxs-lookup"><span data-stu-id="a5275-133">LastName</span></span>|<span data-ttu-id="a5275-134">Smith</span><span class="sxs-lookup"><span data-stu-id="a5275-134">Smith</span></span>|<span data-ttu-id="a5275-135">Smith</span><span class="sxs-lookup"><span data-stu-id="a5275-135">Smith</span></span>|<span data-ttu-id="a5275-136">Smith</span><span class="sxs-lookup"><span data-stu-id="a5275-136">Smith</span></span>|  
|<span data-ttu-id="a5275-137">FirstName</span><span class="sxs-lookup"><span data-stu-id="a5275-137">FirstName</span></span>|<span data-ttu-id="a5275-138">Bernd</span><span class="sxs-lookup"><span data-stu-id="a5275-138">Bob</span></span>|<span data-ttu-id="a5275-139">Bernd</span><span class="sxs-lookup"><span data-stu-id="a5275-139">Bob</span></span>|<span data-ttu-id="a5275-140">Bernd</span><span class="sxs-lookup"><span data-stu-id="a5275-140">Bob</span></span>|  
  
 <span data-ttu-id="a5275-141">Um 13:01 Uhr ruft User2 dieselbe Zeile ab.</span><span class="sxs-lookup"><span data-stu-id="a5275-141">At 1:01 p.m., User2 reads the same row.</span></span>  
  
 <span data-ttu-id="a5275-142">Um 1:03 Uhr ändert User2 **FirstName** von "Bob" in "Robert" und aktualisiert die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a5275-142">At 1:03 p.m., User2 changes **FirstName** from "Bob" to "Robert" and updates the database.</span></span>  
  
|<span data-ttu-id="a5275-143">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="a5275-143">Column name</span></span>|<span data-ttu-id="a5275-144">Ursprünglicher Wert</span><span class="sxs-lookup"><span data-stu-id="a5275-144">Original value</span></span>|<span data-ttu-id="a5275-145">Aktueller Wert</span><span class="sxs-lookup"><span data-stu-id="a5275-145">Current value</span></span>|<span data-ttu-id="a5275-146">Wert in Datenbank</span><span class="sxs-lookup"><span data-stu-id="a5275-146">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="a5275-147">CustID</span><span class="sxs-lookup"><span data-stu-id="a5275-147">CustID</span></span>|<span data-ttu-id="a5275-148">101</span><span class="sxs-lookup"><span data-stu-id="a5275-148">101</span></span>|<span data-ttu-id="a5275-149">101</span><span class="sxs-lookup"><span data-stu-id="a5275-149">101</span></span>|<span data-ttu-id="a5275-150">101</span><span class="sxs-lookup"><span data-stu-id="a5275-150">101</span></span>|  
|<span data-ttu-id="a5275-151">LastName</span><span class="sxs-lookup"><span data-stu-id="a5275-151">LastName</span></span>|<span data-ttu-id="a5275-152">Smith</span><span class="sxs-lookup"><span data-stu-id="a5275-152">Smith</span></span>|<span data-ttu-id="a5275-153">Smith</span><span class="sxs-lookup"><span data-stu-id="a5275-153">Smith</span></span>|<span data-ttu-id="a5275-154">Smith</span><span class="sxs-lookup"><span data-stu-id="a5275-154">Smith</span></span>|  
|<span data-ttu-id="a5275-155">FirstName</span><span class="sxs-lookup"><span data-stu-id="a5275-155">FirstName</span></span>|<span data-ttu-id="a5275-156">Bernd</span><span class="sxs-lookup"><span data-stu-id="a5275-156">Bob</span></span>|<span data-ttu-id="a5275-157">Robert</span><span class="sxs-lookup"><span data-stu-id="a5275-157">Robert</span></span>|<span data-ttu-id="a5275-158">Bernd</span><span class="sxs-lookup"><span data-stu-id="a5275-158">Bob</span></span>|  
  
 <span data-ttu-id="a5275-159">Das Update ist erfolgreich, weil die Werte in der Datenbank zur Zeit des Updates mit den ursprünglichen Werten übereinstimmen, die User2 vorliegen.</span><span class="sxs-lookup"><span data-stu-id="a5275-159">The update succeeds because the values in the database at the time of update match the original values that User2 has.</span></span>  
  
 <span data-ttu-id="a5275-160">Um 13:05 Uhr ändert User1 FirstName von Bob in James und versucht, die Zeile zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a5275-160">At 1:05 p.m., User1 changes "Bob"'s first name to "James" and tries to update the row.</span></span>  
  
|<span data-ttu-id="a5275-161">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="a5275-161">Column name</span></span>|<span data-ttu-id="a5275-162">Ursprünglicher Wert</span><span class="sxs-lookup"><span data-stu-id="a5275-162">Original value</span></span>|<span data-ttu-id="a5275-163">Aktueller Wert</span><span class="sxs-lookup"><span data-stu-id="a5275-163">Current value</span></span>|<span data-ttu-id="a5275-164">Wert in Datenbank</span><span class="sxs-lookup"><span data-stu-id="a5275-164">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="a5275-165">CustID</span><span class="sxs-lookup"><span data-stu-id="a5275-165">CustID</span></span>|<span data-ttu-id="a5275-166">101</span><span class="sxs-lookup"><span data-stu-id="a5275-166">101</span></span>|<span data-ttu-id="a5275-167">101</span><span class="sxs-lookup"><span data-stu-id="a5275-167">101</span></span>|<span data-ttu-id="a5275-168">101</span><span class="sxs-lookup"><span data-stu-id="a5275-168">101</span></span>|  
|<span data-ttu-id="a5275-169">LastName</span><span class="sxs-lookup"><span data-stu-id="a5275-169">LastName</span></span>|<span data-ttu-id="a5275-170">Smith</span><span class="sxs-lookup"><span data-stu-id="a5275-170">Smith</span></span>|<span data-ttu-id="a5275-171">Smith</span><span class="sxs-lookup"><span data-stu-id="a5275-171">Smith</span></span>|<span data-ttu-id="a5275-172">Smith</span><span class="sxs-lookup"><span data-stu-id="a5275-172">Smith</span></span>|  
|<span data-ttu-id="a5275-173">FirstName</span><span class="sxs-lookup"><span data-stu-id="a5275-173">FirstName</span></span>|<span data-ttu-id="a5275-174">Bernd</span><span class="sxs-lookup"><span data-stu-id="a5275-174">Bob</span></span>|<span data-ttu-id="a5275-175">James</span><span class="sxs-lookup"><span data-stu-id="a5275-175">James</span></span>|<span data-ttu-id="a5275-176">Robert</span><span class="sxs-lookup"><span data-stu-id="a5275-176">Robert</span></span>|  
  
 <span data-ttu-id="a5275-177">Zu diesem Zeitpunkt stellt User1 eine Verletzung der optimistischen Parallelität fest, weil der Wert in der Datenbank ("Robert") nicht mit dem ursprünglichen Wert übereinstimmt, den User1 erwartet hat ("Bob").</span><span class="sxs-lookup"><span data-stu-id="a5275-177">At this point, User1 encounters an optimistic concurrency violation because the value in the database ("Robert") no longer matches the original value that User1 was expecting ("Bob").</span></span> <span data-ttu-id="a5275-178">Die Parallelitätsverletzung sagt Ihnen einfach nur, dass das Update fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="a5275-178">The concurrency violation simply lets you know that the update failed.</span></span> <span data-ttu-id="a5275-179">Nun muss entschieden werden, ob die von User2 vorgenommenen Änderungen mit den Änderungen von User1 überschrieben oder die Änderungen von User1 verworfen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a5275-179">The decision now needs to be made whether to overwrite the changes supplied by User2 with the changes supplied by User1, or to cancel the changes by User1.</span></span>  
  
## <a name="testing-for-optimistic-concurrency-violations"></a><span data-ttu-id="a5275-180">Testen auf Verletzung der vollständigen Parallelität</span><span class="sxs-lookup"><span data-stu-id="a5275-180">Testing for Optimistic Concurrency Violations</span></span>  

 <span data-ttu-id="a5275-181">Es gibt mehrere Testverfahren, mit denen eine Verletzung der vollständigen Parallelität festgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a5275-181">There are several techniques for testing for an optimistic concurrency violation.</span></span> <span data-ttu-id="a5275-182">Eine Methode besteht im Einfügen einer Timestamp-Spalte in die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a5275-182">One involves including a timestamp column in the table.</span></span> <span data-ttu-id="a5275-183">Datenbanken stellen im Allgemeinen Timestamp-Funktionen zur Verfügung, mit denen der Updatezeitpunkt (Datum und Uhrzeit) des Datensatzes gekennzeichnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a5275-183">Databases commonly provide timestamp functionality that can be used to identify the date and time when the record was last updated.</span></span> <span data-ttu-id="a5275-184">Bei dieser Methode wird eine Timestamp-Spalte in die Tabellendefinition eingefügt.</span><span class="sxs-lookup"><span data-stu-id="a5275-184">Using this technique, a timestamp column is included in the table definition.</span></span> <span data-ttu-id="a5275-185">Bei jedem Update des Datensatzes wird der Timestamp aktualisiert, sodass er den aktuellen Zeitpunkt (Datum und Uhrzeit) angibt.</span><span class="sxs-lookup"><span data-stu-id="a5275-185">Whenever the record is updated, the timestamp is updated to reflect the current date and time.</span></span> <span data-ttu-id="a5275-186">Bei einem Test auf eine Verletzung der vollständigen Parallelität wird die Timestamp-Spalte bei jeder Abfrage des Tabelleninhalts zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a5275-186">In a test for optimistic concurrency violations, the timestamp column is returned with any query of the contents of the table.</span></span> <span data-ttu-id="a5275-187">Bei einem Updateversuch wird der Timestamp-Wert in der Datenbank mit dem ursprünglichen Timestamp-Wert verglichen, der in der geänderten Zeile enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a5275-187">When an update is attempted, the timestamp value in the database is compared to the original timestamp value contained in the modified row.</span></span> <span data-ttu-id="a5275-188">Wenn die Werte identisch sind, wird die Timestamp-Spalte mit der aktuellen Uhrzeit aktualisiert, um das Update zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="a5275-188">If they match, the update is performed and the timestamp column is updated with the current time to reflect the update.</span></span> <span data-ttu-id="a5275-189">Wenn die Werte nicht identisch sind, wurde die vollständige Parallelität verletzt.</span><span class="sxs-lookup"><span data-stu-id="a5275-189">If they do not match, an optimistic concurrency violation has occurred.</span></span>  
  
 <span data-ttu-id="a5275-190">Beim zweiten Testverfahren, mit dem eine Verletzung der vollständigen Parallelität festgestellt werden kann, wird überprüft, ob alle ursprünglichen Spaltenwerte einer Zeile mit denen in der Datenbank übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a5275-190">Another technique for testing for an optimistic concurrency violation is to verify that all the original column values in a row still match those found in the database.</span></span> <span data-ttu-id="a5275-191">Angenommen, beispielsweise liegt die folgende Abfrage vor:</span><span class="sxs-lookup"><span data-stu-id="a5275-191">For example, consider the following query:</span></span>  
  
```sql
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 <span data-ttu-id="a5275-192">Wenn Sie beim Aktualisieren einer Zeile in **Table1**auf eine Verletzung der vollständigen Parallelität testen möchten, geben Sie die folgende Update-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="a5275-192">To test for an optimistic concurrency violation when updating a row in **Table1**, you would issue the following UPDATE statement:</span></span>  
  
```sql
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 <span data-ttu-id="a5275-193">Wenn die ursprünglichen Werte mit den Werten in der Datenbank übereinstimmen, wird das Update durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5275-193">As long as the original values match the values in the database, the update is performed.</span></span> <span data-ttu-id="a5275-194">Wenn ein Wert geändert wurde, wird die Zeile von der UPDATE-Anweisung nicht aktualisiert, weil die WHERE-Klausel keine Übereinstimmung findet.</span><span class="sxs-lookup"><span data-stu-id="a5275-194">If a value has been modified, the update will not modify the row because the WHERE clause will not find a match.</span></span>  
  
 <span data-ttu-id="a5275-195">Es empfiehlt sich, in einer Abfrage stets einen eindeutigen Primärschlüsselwert zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="a5275-195">Note that it is recommended to always return a unique primary key value in your query.</span></span> <span data-ttu-id="a5275-196">Andernfalls könnte die vorhergehende UPDATE-Anweisung mehr als eine Zeile aktualisieren, was möglicherweise nicht von Ihnen beabsichtigt ist.</span><span class="sxs-lookup"><span data-stu-id="a5275-196">Otherwise, the preceding UPDATE statement may update more than one row, which might not be your intent.</span></span>  
  
 <span data-ttu-id="a5275-197">Wenn in einer Spalte Ihrer Datenquelle NULL-Werte zulässig sind, müssen Sie Ihre WHERE-Klausel erweitern, um nach einem entsprechenden NULL-Verweis in Ihrer lokalen Tabelle und in der Datenquelle zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a5275-197">If a column at your data source allows nulls, you may need to extend your WHERE clause to check for a matching null reference in your local table and at the data source.</span></span> <span data-ttu-id="a5275-198">Die folgende UPDATE-Anweisung prüft z. B., ob ein NULL-Verweis in der lokalen Zeile noch mit einem NULL-Verweis in der Datenquelle übereinstimmt oder ob der Wert in der lokalen Zeile noch mit dem Wert in der Datenquelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a5275-198">For example, the following UPDATE statement verifies that a null reference in the local row still matches a null reference at the data source, or that the value in the local row still matches the value at the data source.</span></span>  
  
```sql
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 <span data-ttu-id="a5275-199">Sie können bei einem Modell der vollständigen Parallelität auch weniger strenge Kriterien anwenden.</span><span class="sxs-lookup"><span data-stu-id="a5275-199">You may also choose to apply less restrictive criteria when using an optimistic concurrency model.</span></span> <span data-ttu-id="a5275-200">Wenn Sie z. B. nur die Primärschlüsselspalten in der WHERE-Klausel verwenden, werden die Daten unabhängig davon überschrieben, ob die anderen Spalten seit der letzten Abfrage aktualisiert wurden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="a5275-200">For example, using only the primary key columns in the WHERE clause causes the data to be overwritten regardless of whether the other columns have been updated since the last query.</span></span> <span data-ttu-id="a5275-201">Zudem besteht die Möglichkeit, eine WHERE-Klausel auf spezifische Spalten anzuwenden, sodass die Daten überschrieben werden, sofern nicht bestimmte Felder seit deren letzten Abfrage aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a5275-201">You can also apply a WHERE clause only to specific columns, resulting in data being overwritten unless particular fields have been updated since they were last queried.</span></span>  
  
### <a name="the-dataadapterrowupdated-event"></a><span data-ttu-id="a5275-202">Das "DataAdapter.RowUpdated"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a5275-202">The DataAdapter.RowUpdated Event</span></span>  

 <span data-ttu-id="a5275-203">Das **rowaktualisierte** -Ereignis des- <xref:System.Data.Common.DataAdapter> Objekts kann zusammen mit den oben beschriebenen Techniken verwendet werden, um die Anwendung von Verletzungen der vollständigen Parallelität zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="a5275-203">The **RowUpdated** event of the <xref:System.Data.Common.DataAdapter> object can be used in conjunction with the techniques described earlier, to provide notification to your application of optimistic concurrency violations.</span></span> <span data-ttu-id="a5275-204">**Rowupdate** erfolgt nach jedem Versuch, eine **geänderte** Zeile aus einem **DataSet**zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a5275-204">**RowUpdated** occurs after each attempt to update a **Modified** row from a **DataSet**.</span></span> <span data-ttu-id="a5275-205">Damit können Sie spezifischen Behandlungscode hinzufügen, einschließlich Verarbeitung bei Ausnahmen, Einfügen von benutzerdefinierten Fehlerinformationen, Hinzufügen einer Wiederholungslogik usw.</span><span class="sxs-lookup"><span data-stu-id="a5275-205">This enables you to add special handling code, including processing when an exception occurs, adding custom error information, adding retry logic, and so on.</span></span> <span data-ttu-id="a5275-206">Das- <xref:System.Data.Common.RowUpdatedEventArgs> Objekt gibt eine **recordsaffzierte** -Eigenschaft zurück, die die Anzahl der Zeilen enthält, die von einem bestimmten Update-Befehl für eine geänderte Zeile in einer Tabelle betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="a5275-206">The <xref:System.Data.Common.RowUpdatedEventArgs> object returns a **RecordsAffected** property containing the number of rows affected by a particular update command for a modified row in a table.</span></span> <span data-ttu-id="a5275-207">Wenn Sie den Update-Befehl so festlegen, dass die vollständige Parallelität getestet wird, gibt die **recordsaffzierte** -Eigenschaft als Ergebnis den Wert 0 zurück, wenn eine Verletzung der vollständigen Parallelität aufgetreten ist, da keine Datensätze aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a5275-207">By setting the update command to test for optimistic concurrency, the **RecordsAffected** property will, as a result, return a value of 0 when an optimistic concurrency violation has occurred, because no records were updated.</span></span> <span data-ttu-id="a5275-208">Wenn dies der Fall ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a5275-208">If this is the case, an exception is thrown.</span></span> <span data-ttu-id="a5275-209">Das Ereignis **rowaktualisierte** ermöglicht es Ihnen, dieses Vorkommen zu behandeln und die Ausnahme zu vermeiden, indem Sie einen entsprechenden **RowUpdatedEventArgs. Status** -Wert festlegen, z. b. **UpdateStatus. SkipCurrentRow**.</span><span class="sxs-lookup"><span data-stu-id="a5275-209">The **RowUpdated** event enables you to handle this occurrence and avoid the exception by setting an appropriate **RowUpdatedEventArgs.Status** value, such as **UpdateStatus.SkipCurrentRow**.</span></span> <span data-ttu-id="a5275-210">Weitere Informationen zum **rowaktualisierte** -Ereignis finden Sie unter [Handling DataAdapter-Ereignisse](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="a5275-210">For more information about the **RowUpdated** event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
 <span data-ttu-id="a5275-211">Optional können Sie **DataAdapter. ContinueUpdateOnError** auf **true**festlegen, bevor Sie **Update**aufrufen, und auf die Fehlerinformationen reagieren, die in der **RowError** -Eigenschaft einer bestimmten Zeile gespeichert sind, wenn das **Update** abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a5275-211">Optionally, you can set **DataAdapter.ContinueUpdateOnError** to **true**, before calling **Update**, and respond to the error information stored in the **RowError** property of a particular row when the **Update** is completed.</span></span> <span data-ttu-id="a5275-212">Weitere Informationen finden Sie unter [Zeilen Fehlerinformationen](./dataset-datatable-dataview/row-error-information.md).</span><span class="sxs-lookup"><span data-stu-id="a5275-212">For more information, see [Row Error Information](./dataset-datatable-dataview/row-error-information.md).</span></span>  
  
## <a name="optimistic-concurrency-example"></a><span data-ttu-id="a5275-213">Beispiel für eine vollständige Parallelität</span><span class="sxs-lookup"><span data-stu-id="a5275-213">Optimistic Concurrency Example</span></span>  

 <span data-ttu-id="a5275-214">Im folgenden finden Sie ein einfaches Beispiel, das den **UpdateCommand** eines **DataAdapter** zum Testen auf vollständige Parallelität festlegt und dann das **rowaktualisierte** -Ereignis verwendet, um auf Verletzungen der vollständigen Parallelität zu testen.</span><span class="sxs-lookup"><span data-stu-id="a5275-214">The following is a simple example that sets the **UpdateCommand** of a **DataAdapter** to test for optimistic concurrency, and then uses the **RowUpdated** event to test for optimistic concurrency violations.</span></span> <span data-ttu-id="a5275-215">Wenn eine Verletzung der vollständigen Parallelität auftritt, legt die Anwendung den **RowError** der Zeile fest, für die das Update ausgegeben wurde, um eine Verletzung der vollständigen Parallelität widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="a5275-215">When an optimistic concurrency violation is encountered, the application sets the **RowError** of the row that the update was issued for to reflect an optimistic concurrency violation.</span></span>  
  
 <span data-ttu-id="a5275-216">Beachten Sie, dass die an die WHERE-Klausel des Update-Befehls übergebenen Parameterwerte den **ursprünglichen** Werten ihrer jeweiligen Spalten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a5275-216">Note that the parameter values passed to the WHERE clause of the UPDATE command are mapped to the **Original** values of their respective columns.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName", connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5275-217">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5275-217">See also</span></span>

- [<span data-ttu-id="a5275-218">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a5275-218">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="a5275-219">Aktualisieren von Datenquellen mit "DataAdapters"</span><span class="sxs-lookup"><span data-stu-id="a5275-219">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="a5275-220">Zeilenfehlerinformationen</span><span class="sxs-lookup"><span data-stu-id="a5275-220">Row Error Information</span></span>](./dataset-datatable-dataview/row-error-information.md)
- [<span data-ttu-id="a5275-221">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="a5275-221">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="a5275-222">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a5275-222">ADO.NET Overview</span></span>](ado-net-overview.md)
