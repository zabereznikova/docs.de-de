---
title: Dokumentgenehmigungsprozess
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: cee43aff991f9482de7b3172174eb0e786ec1fe6
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74710851"
---
# <a name="document-approval-process"></a><span data-ttu-id="28878-102">Dokumentgenehmigungsprozess</span><span class="sxs-lookup"><span data-stu-id="28878-102">Document Approval Process</span></span>

<span data-ttu-id="28878-103">Dieses Beispiel veranschaulicht die Verwendung von vielen Windows Workflow Foundation (WF) und Windows Communication Foundation (WCF)-Features.</span><span class="sxs-lookup"><span data-stu-id="28878-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="28878-104">Zusammen implementieren sie ein Szenario für einen Dokumentgenehmigungsprozess.</span><span class="sxs-lookup"><span data-stu-id="28878-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="28878-105">Eine Clientanwendung kann Dokumente zur Genehmigung senden und Dokumente genehmigen.</span><span class="sxs-lookup"><span data-stu-id="28878-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="28878-106">Es ist eine Genehmigungs-Manager-Anwendung vorhanden, um die Kommunikation zwischen Clients zu unterstützen und die Regeln für den Genehmigungsprozess umzusetzen.</span><span class="sxs-lookup"><span data-stu-id="28878-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="28878-107">Der Genehmigungsprozess ist ein Workflow, der mehrere Genehmigungsarten ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="28878-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="28878-108">Es sind Aktivitäten vorhanden, mit denen ein Einzelgenehmigungsprozess, ein Quorumgenehmigungsprozess (Prozentsatz aller Genehmiger) und ein komplexer Genehmigungsprozess, der aus einer Abfolge einer Quorumgenehmigung und einer Einzelgenehmigung besteht, abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="28878-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28878-109">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="28878-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="28878-110">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="28878-110">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="28878-111">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="28878-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="28878-112">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="28878-112">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`

## <a name="sample-details"></a><span data-ttu-id="28878-113">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="28878-113">Sample Details</span></span>

<span data-ttu-id="28878-114">In der folgenden Abbildung wird der Workflow für den Dokument Genehmigungsprozess veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="28878-114">The following graphic demonstrates the document approval process workflow:</span></span>

![Ein Workflow für den Prozess der Genehmigung von Dokumenten](./media/document-approval-process/document-approval-process.jpg)

<span data-ttu-id="28878-116">Aus Sicht des Clients funktioniert der Genehmigungsprozess wie folgt:</span><span class="sxs-lookup"><span data-stu-id="28878-116">From the client's perspective, the approval process functions as follows:</span></span>

1. <span data-ttu-id="28878-117">Ein Client wird ein Benutzer im Genehmigungsprozesssystem.</span><span class="sxs-lookup"><span data-stu-id="28878-117">A client subscribes to be a user in the approval process system.</span></span>

2. <span data-ttu-id="28878-118">Ein WCF-Client sendet an einen WCF-Dienst, der von der Genehmigungs-Manager-Anwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="28878-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>

3. <span data-ttu-id="28878-119">Dem Client wird eine eindeutige Benutzer-ID zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28878-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="28878-120">Der Client kann jetzt an Genehmigungsprozessen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="28878-120">The client can now participate in approval processes.</span></span>

4. <span data-ttu-id="28878-121">Sobald der Client teilnimmt, kann er ein Dokument zur Genehmigung durch den Einzelgenehmigungs-, Quorumgenehmigungs- oder komplexen Genehmigungsprozess senden.</span><span class="sxs-lookup"><span data-stu-id="28878-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>

5. <span data-ttu-id="28878-122">Durch Klicken auf eine Schaltfläche in der Clientoberfläche wird eine Workflowinstanz in einem Workflowdiensthost gestartet.</span><span class="sxs-lookup"><span data-stu-id="28878-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>

6. <span data-ttu-id="28878-123">Der Workflow sendet eine Genehmigungsanforderung an die Genehmigungs-Manager-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="28878-123">The workflow sends an approval request to the approval manager application.</span></span>

7. <span data-ttu-id="28878-124">Der Workflow-Manager startet seinerseits einen Workflow, der einen Genehmigungsprozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="28878-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>

8. <span data-ttu-id="28878-125">Sobald der Manager-Genehmigungsworkflow ausgeführt wird, werden die Ergebnisse an den Client zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="28878-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>

9. <span data-ttu-id="28878-126">Der Client zeigt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="28878-126">The client displays the results.</span></span>

10. <span data-ttu-id="28878-127">Ein Client kann eine Genehmigungsanforderung empfangen und zu jedem Zeitpunkt auf die Anforderung antworten.</span><span class="sxs-lookup"><span data-stu-id="28878-127">A client may receive an approval request and respond to the request at any point in time.</span></span>

11. <span data-ttu-id="28878-128">Ein auf dem Client gehosteter WCF-Dienst kann eine Genehmigungs Anforderung von der Genehmigungs-Manager-Anwendung empfangen.</span><span class="sxs-lookup"><span data-stu-id="28878-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>

12. <span data-ttu-id="28878-129">Die Dokumentinformationen werden zum Review auf dem Client dargestellt.</span><span class="sxs-lookup"><span data-stu-id="28878-129">The document information is presented on the client for review.</span></span>

13. <span data-ttu-id="28878-130">Der Benutzer kann das Dokument genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="28878-130">The user can approve or reject the document.</span></span>

14. <span data-ttu-id="28878-131">Ein WCF-Client wird verwendet, um eine Genehmigungs Antwort an die Genehmigungs-Manager-Anwendung zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="28878-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>

<span data-ttu-id="28878-132">Aus Sicht der Genehmigungs-Manager-Anwendung funktioniert der Genehmigungsprozess wie folgt:</span><span class="sxs-lookup"><span data-stu-id="28878-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>

1. <span data-ttu-id="28878-133">Ein Client fordert an, am Genehmigungsprozesssystem teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="28878-133">A client requests to participate to the approval process system.</span></span>

2. <span data-ttu-id="28878-134">Ein WCF-Dienst im Genehmigungs-Manager empfängt eine Anforderung, um Teil des Genehmigungsprozess Systems zu sein.</span><span class="sxs-lookup"><span data-stu-id="28878-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>

3. <span data-ttu-id="28878-135">Für den Client wird eine eindeutige ID generiert.</span><span class="sxs-lookup"><span data-stu-id="28878-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="28878-136">Die Benutzerinformationen werden in einer Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="28878-136">The user information is stored in a database.</span></span>

4. <span data-ttu-id="28878-137">Die eindeutige ID wird an den Benutzer zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="28878-137">The unique ID is sent back to the user.</span></span>

5. <span data-ttu-id="28878-138">Es wird eine Genehmigungsanforderung empfangen.</span><span class="sxs-lookup"><span data-stu-id="28878-138">An approval request is receive.</span></span> <span data-ttu-id="28878-139">Der Genehmigungs-Manager führt einen Genehmigungsprozess aus.</span><span class="sxs-lookup"><span data-stu-id="28878-139">The approval manager executes an approval process.</span></span>

6. <span data-ttu-id="28878-140">Der Genehmigungs-Manager empfängt eine Genehmigungsanforderung, wodurch ein neuer Workflow gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="28878-140">An approval request is received by the approval manager, starting a new workflow.</span></span>

7. <span data-ttu-id="28878-141">Abhängig vom Typ der Anforderung (einfach, Quorum oder komplex) wird eine andere Aktivität ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="28878-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>

8. <span data-ttu-id="28878-142">Zum Senden der Genehmigungsanforderung an den Client zum Review und zum Empfangen der Antwort werden Sende- und Empfangsaktivitäten mit Korrelation verwendet.</span><span class="sxs-lookup"><span data-stu-id="28878-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>

9. <span data-ttu-id="28878-143">Das Ergebnis des Genehmigungsprozessworkflows wird an den Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="28878-143">The result of the approval process workflow is sent to the client.</span></span>

## <a name="using-the-sample"></a><span data-ttu-id="28878-144">Verwenden des Beispiels</span><span class="sxs-lookup"><span data-stu-id="28878-144">Using the Sample</span></span>

##### <a name="to-set-up-the-database"></a><span data-ttu-id="28878-145">So richten Sie die Datenbank ein</span><span class="sxs-lookup"><span data-stu-id="28878-145">To set up the database</span></span>

1. <span data-ttu-id="28878-146">Navigieren Sie in einer Visual Studio 2010-Eingabeaufforderung mit Administrator Rechten zu diesem Ordner documentapprovalprocess, und führen Sie Setup. cmd aus.</span><span class="sxs-lookup"><span data-stu-id="28878-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>

##### <a name="to-set-up-the-application"></a><span data-ttu-id="28878-147">So richten Sie die Anwendung ein</span><span class="sxs-lookup"><span data-stu-id="28878-147">To set up the application</span></span>

1. <span data-ttu-id="28878-148">Öffnen Sie mit Visual Studio 2010 die Projektmappendatei "documentapprovalprocess. sln".</span><span class="sxs-lookup"><span data-stu-id="28878-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>

2. <span data-ttu-id="28878-149">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="28878-149">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="28878-150">Um die Lösung auszuführen, starten Sie die Genehmigungs-Manager-Anwendung, indem Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt approvalmanager klicken und dann im Kontextmenü auf **Debuggen**->neue Instanz **starten** klicken.</span><span class="sxs-lookup"><span data-stu-id="28878-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>

    <span data-ttu-id="28878-151">Warten Sie auf die Bestätigung des Managers, dass dieser bereit ist.</span><span class="sxs-lookup"><span data-stu-id="28878-151">Wait for the manager’s output to let you know that it is ready.</span></span>

##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="28878-152">So führen Sie das Einzelgenehmigungsszenario aus</span><span class="sxs-lookup"><span data-stu-id="28878-152">To run the single approval scenario</span></span>

1. <span data-ttu-id="28878-153">Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="28878-153">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="28878-154">Navigieren Sie zum Verzeichnis, das die Projektmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="28878-154">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="28878-155">Navigieren Sie zum Ordner ApprovalClient\Bin\Debug, und führen Sie zwei Instanzen von ApprovalClient.exe aus.</span><span class="sxs-lookup"><span data-stu-id="28878-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="28878-156">Klicken Sie auf **ermitteln**, warten Sie, bis die Schaltfläche **abonnieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="28878-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="28878-157">Geben Sie einen Benutzernamen ein, und klicken Sie auf **abonnieren**</span><span class="sxs-lookup"><span data-stu-id="28878-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="28878-158">Verwenden Sie für einen Client `UserType1` und für den anderen den Typ `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="28878-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>

6. <span data-ttu-id="28878-159">Wählen Sie im `UserType1`-Client den Einzelgenehmigungstyp im Dropdownmenü aus, und geben Sie einen Dokumentnamen und -inhalt ein.</span><span class="sxs-lookup"><span data-stu-id="28878-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="28878-160">Klicken Sie auf **Genehmigung anfordern**.</span><span class="sxs-lookup"><span data-stu-id="28878-160">Click **Request Approval**.</span></span>

7. <span data-ttu-id="28878-161">Im `UserType2`-Client wird ein Dokument, das auf Genehmigung wartet, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28878-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="28878-162">Wählen Sie es aus, und drücken Sie **genehmigen** oder **ablehnen**.</span><span class="sxs-lookup"><span data-stu-id="28878-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="28878-163">Die Ergebnisse werden im `UserType1`-Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28878-163">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="28878-164">So führen Sie das Quorumgenehmigungsszenario aus</span><span class="sxs-lookup"><span data-stu-id="28878-164">To run the quorum approval scenario</span></span>

1. <span data-ttu-id="28878-165">Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="28878-165">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="28878-166">Navigieren Sie zum Verzeichnis, das die Projektmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="28878-166">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="28878-167">Navigieren Sie zum Ordner ApprovalClient\Bin\Debug, und führen Sie drei Instanzen von ApprovalClient.exe aus.</span><span class="sxs-lookup"><span data-stu-id="28878-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="28878-168">Klicken Sie auf **ermitteln**, warten Sie, bis die Schaltfläche **abonnieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="28878-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="28878-169">Geben Sie einen Benutzernamen ein, und klicken Sie auf **abonnieren**</span><span class="sxs-lookup"><span data-stu-id="28878-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="28878-170">Verwenden Sie für einen Client `UserType1` und für die anderen den Typ `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="28878-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>

6. <span data-ttu-id="28878-171">Wählen Sie im `UserType1`-Client den Quorumgenehmigungstyp im Dropdownmenü aus, und geben Sie einen Dokumentnamen und -inhalt ein.</span><span class="sxs-lookup"><span data-stu-id="28878-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="28878-172">Klicken Sie auf **Genehmigung anfordern**.</span><span class="sxs-lookup"><span data-stu-id="28878-172">Click **Request Approval**.</span></span> <span data-ttu-id="28878-173">Hierdurch wird angefordert, dass die beiden `UserType2`-Clients das Dokument genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="28878-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="28878-174">Während beide `UserType2`-Clients antworten müssen, muss nur ein Client das Dokument genehmigen, damit es genehmigt wird.</span><span class="sxs-lookup"><span data-stu-id="28878-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>

7. <span data-ttu-id="28878-175">In den `UserType2`-Clients wird ein Dokument, das auf Genehmigung wartet, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28878-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="28878-176">Wählen Sie es aus, und drücken Sie **genehmigen** oder **ablehnen**.</span><span class="sxs-lookup"><span data-stu-id="28878-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="28878-177">Die Ergebnisse werden im `UserType1`-Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28878-177">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="28878-178">So führen Sie das komplexe Genehmigungsszenario aus</span><span class="sxs-lookup"><span data-stu-id="28878-178">To run the complex approval scenario</span></span>

1. <span data-ttu-id="28878-179">Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="28878-179">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="28878-180">Navigieren Sie zum Verzeichnis, das die Projektmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="28878-180">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="28878-181">Navigieren Sie zum Ordner ApprovalClient\Bin\Debug, und führen Sie vier Instanzen von ApprovalClient.exe aus.</span><span class="sxs-lookup"><span data-stu-id="28878-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="28878-182">Klicken Sie auf **ermitteln**, warten Sie, bis die Schaltfläche **abonnieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="28878-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="28878-183">Geben Sie einen Benutzernamen ein, und klicken Sie auf **abonnieren**</span><span class="sxs-lookup"><span data-stu-id="28878-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="28878-184">Verwenden Sie für einen Client `UserType1`, für zwei Clients `UserType2` und für den vierten Client `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="28878-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>

6. <span data-ttu-id="28878-185">Wählen Sie im `UserType1`-Client den Einzelgenehmigungstyp im Dropdownmenü aus, und geben Sie einen Dokumentnamen und -inhalt ein.</span><span class="sxs-lookup"><span data-stu-id="28878-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="28878-186">Klicken Sie auf **Genehmigung anfordern**.</span><span class="sxs-lookup"><span data-stu-id="28878-186">Click **Request Approval**.</span></span>

7. <span data-ttu-id="28878-187">In den `UserType2`-Clients wird ein Dokument, das auf Genehmigung wartet, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28878-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="28878-188">Wählen Sie diese Option aus, und klicken Sie auf **genehmigen**. das Dokument wird an den `UserType3` Client weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="28878-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>

    <span data-ttu-id="28878-189">Wenn das Dokument vom ersten `UserType2`-Quorum genehmigt wird, wird das Dokument an den `UserType3`-Client übergeben.</span><span class="sxs-lookup"><span data-stu-id="28878-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>

8. <span data-ttu-id="28878-190">Genehmigen Sie das Dokument im `UserType3`-Client, oder lehnen Sie es ab.</span><span class="sxs-lookup"><span data-stu-id="28878-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="28878-191">Die Ergebnisse werden im `UserType1`-Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28878-191">The results should show in the `UserType1` client.</span></span>

##### <a name="to-clean-up"></a><span data-ttu-id="28878-192">So führen Sie eine Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="28878-192">To clean up</span></span>

1. <span data-ttu-id="28878-193">Navigieren Sie an einer Visual Studio 2010-Eingabeaufforderung zum Ordner documentapprovalprocess, und führen Sie Cleanup. cmd aus.</span><span class="sxs-lookup"><span data-stu-id="28878-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
