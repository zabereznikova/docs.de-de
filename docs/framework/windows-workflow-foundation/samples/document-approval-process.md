---
title: Dokumentgenehmigungsprozess
description: In diesem Beispiel werden viele Windows Workflow Foundation und Windows Communication Foundation Funktionen in einem Dokument Genehmigungsprozess-Szenario veranschaulicht.
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: 18b4f978e9234daf22395f0d2f6f0889d0edf966
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421409"
---
# <a name="document-approval-process"></a><span data-ttu-id="b4de9-103">Dokumentgenehmigungsprozess</span><span class="sxs-lookup"><span data-stu-id="b4de9-103">Document Approval Process</span></span>

<span data-ttu-id="b4de9-104">Dieses Beispiel veranschaulicht die Verwendung von vielen Windows Workflow Foundation (WF) und Windows Communication Foundation (WCF)-Features.</span><span class="sxs-lookup"><span data-stu-id="b4de9-104">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="b4de9-105">Zusammen implementieren sie ein Szenario für einen Dokumentgenehmigungsprozess.</span><span class="sxs-lookup"><span data-stu-id="b4de9-105">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="b4de9-106">Eine Clientanwendung kann Dokumente zur Genehmigung senden und Dokumente genehmigen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-106">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="b4de9-107">Es ist eine Genehmigungs-Manager-Anwendung vorhanden, um die Kommunikation zwischen Clients zu unterstützen und die Regeln für den Genehmigungsprozess umzusetzen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-107">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="b4de9-108">Der Genehmigungsprozess ist ein Workflow, der mehrere Genehmigungsarten ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="b4de9-108">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="b4de9-109">Es sind Aktivitäten vorhanden, mit denen ein Einzelgenehmigungsprozess, ein Quorumgenehmigungsprozess (Prozentsatz aller Genehmiger) und ein komplexer Genehmigungsprozess, der aus einer Abfolge einer Quorumgenehmigung und einer Einzelgenehmigung besteht, abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b4de9-109">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4de9-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b4de9-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b4de9-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b4de9-111">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="b4de9-112">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4de9-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b4de9-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b4de9-113">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`

## <a name="sample-details"></a><span data-ttu-id="b4de9-114">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="b4de9-114">Sample Details</span></span>

<span data-ttu-id="b4de9-115">In der folgenden Abbildung wird der Workflow für den Dokument Genehmigungsprozess veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b4de9-115">The following graphic demonstrates the document approval process workflow:</span></span>

![Workflow für den Prozess zur Genehmigung von Dokumenten](./media/document-approval-process/document-approval-process.jpg)

<span data-ttu-id="b4de9-117">Aus Sicht des Clients funktioniert der Genehmigungsprozess wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b4de9-117">From the client's perspective, the approval process functions as follows:</span></span>

1. <span data-ttu-id="b4de9-118">Ein Client wird ein Benutzer im Genehmigungsprozesssystem.</span><span class="sxs-lookup"><span data-stu-id="b4de9-118">A client subscribes to be a user in the approval process system.</span></span>

2. <span data-ttu-id="b4de9-119">Ein WCF-Client sendet an einen WCF-Dienst, der von der Genehmigungs-Manager-Anwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="b4de9-119">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>

3. <span data-ttu-id="b4de9-120">Dem Client wird eine eindeutige Benutzer-ID zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4de9-120">A unique user ID is returned to the client.</span></span> <span data-ttu-id="b4de9-121">Der Client kann jetzt an Genehmigungsprozessen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-121">The client can now participate in approval processes.</span></span>

4. <span data-ttu-id="b4de9-122">Sobald der Client teilnimmt, kann er ein Dokument zur Genehmigung durch den Einzelgenehmigungs-, Quorumgenehmigungs- oder komplexen Genehmigungsprozess senden.</span><span class="sxs-lookup"><span data-stu-id="b4de9-122">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>

5. <span data-ttu-id="b4de9-123">Durch Klicken auf eine Schaltfläche in der Clientoberfläche wird eine Workflowinstanz in einem Workflowdiensthost gestartet.</span><span class="sxs-lookup"><span data-stu-id="b4de9-123">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>

6. <span data-ttu-id="b4de9-124">Der Workflow sendet eine Genehmigungsanforderung an die Genehmigungs-Manager-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b4de9-124">The workflow sends an approval request to the approval manager application.</span></span>

7. <span data-ttu-id="b4de9-125">Der Workflow-Manager startet seinerseits einen Workflow, der einen Genehmigungsprozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="b4de9-125">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>

8. <span data-ttu-id="b4de9-126">Sobald der Manager-Genehmigungsworkflow ausgeführt wird, werden die Ergebnisse an den Client zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="b4de9-126">Once the manager approval workflow executes, the results are sent back to the client.</span></span>

9. <span data-ttu-id="b4de9-127">Der Client zeigt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="b4de9-127">The client displays the results.</span></span>

10. <span data-ttu-id="b4de9-128">Ein Client kann eine Genehmigungsanforderung empfangen und zu jedem Zeitpunkt auf die Anforderung antworten.</span><span class="sxs-lookup"><span data-stu-id="b4de9-128">A client may receive an approval request and respond to the request at any point in time.</span></span>

11. <span data-ttu-id="b4de9-129">Ein auf dem Client gehosteter WCF-Dienst kann eine Genehmigungs Anforderung von der Genehmigungs-Manager-Anwendung empfangen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-129">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>

12. <span data-ttu-id="b4de9-130">Die Dokumentinformationen werden zum Review auf dem Client dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4de9-130">The document information is presented on the client for review.</span></span>

13. <span data-ttu-id="b4de9-131">Der Benutzer kann das Dokument genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-131">The user can approve or reject the document.</span></span>

14. <span data-ttu-id="b4de9-132">Ein WCF-Client wird verwendet, um eine Genehmigungs Antwort an die Genehmigungs-Manager-Anwendung zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="b4de9-132">A WCF client is used to send an approval response back to the approval manager application.</span></span>

<span data-ttu-id="b4de9-133">Aus Sicht der Genehmigungs-Manager-Anwendung funktioniert der Genehmigungsprozess wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b4de9-133">From the approval manager application’s point of view, the approval process functions as follows:</span></span>

1. <span data-ttu-id="b4de9-134">Ein Client fordert an, am Genehmigungsprozesssystem teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-134">A client requests to participate to the approval process system.</span></span>

2. <span data-ttu-id="b4de9-135">Ein WCF-Dienst im Genehmigungs-Manager empfängt eine Anforderung, um Teil des Genehmigungsprozess Systems zu sein.</span><span class="sxs-lookup"><span data-stu-id="b4de9-135">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>

3. <span data-ttu-id="b4de9-136">Für den Client wird eine eindeutige ID generiert.</span><span class="sxs-lookup"><span data-stu-id="b4de9-136">A unique ID is generated for the client.</span></span> <span data-ttu-id="b4de9-137">Die Benutzerinformationen werden in einer Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b4de9-137">The user information is stored in a database.</span></span>

4. <span data-ttu-id="b4de9-138">Die eindeutige ID wird an den Benutzer zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="b4de9-138">The unique ID is sent back to the user.</span></span>

5. <span data-ttu-id="b4de9-139">Es wird eine Genehmigungsanforderung empfangen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-139">An approval request is receive.</span></span> <span data-ttu-id="b4de9-140">Der Genehmigungs-Manager führt einen Genehmigungsprozess aus.</span><span class="sxs-lookup"><span data-stu-id="b4de9-140">The approval manager executes an approval process.</span></span>

6. <span data-ttu-id="b4de9-141">Der Genehmigungs-Manager empfängt eine Genehmigungsanforderung, wodurch ein neuer Workflow gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b4de9-141">An approval request is received by the approval manager, starting a new workflow.</span></span>

7. <span data-ttu-id="b4de9-142">Abhängig vom Typ der Anforderung (einfach, Quorum oder komplex) wird eine andere Aktivität ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4de9-142">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>

8. <span data-ttu-id="b4de9-143">Zum Senden der Genehmigungsanforderung an den Client zum Review und zum Empfangen der Antwort werden Sende- und Empfangsaktivitäten mit Korrelation verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4de9-143">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>

9. <span data-ttu-id="b4de9-144">Das Ergebnis des Genehmigungsprozessworkflows wird an den Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="b4de9-144">The result of the approval process workflow is sent to the client.</span></span>

## <a name="using-the-sample"></a><span data-ttu-id="b4de9-145">Verwenden des Beispiels</span><span class="sxs-lookup"><span data-stu-id="b4de9-145">Using the Sample</span></span>

##### <a name="to-set-up-the-database"></a><span data-ttu-id="b4de9-146">So richten Sie die Datenbank ein</span><span class="sxs-lookup"><span data-stu-id="b4de9-146">To set up the database</span></span>

1. <span data-ttu-id="b4de9-147">Navigieren Sie in einer Visual Studio 2010-Eingabeaufforderung mit Administrator Rechten zu diesem Ordner documentapprovalprocess, und führen Sie Setup. cmd aus.</span><span class="sxs-lookup"><span data-stu-id="b4de9-147">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>

##### <a name="to-set-up-the-application"></a><span data-ttu-id="b4de9-148">So richten Sie die Anwendung ein</span><span class="sxs-lookup"><span data-stu-id="b4de9-148">To set up the application</span></span>

1. <span data-ttu-id="b4de9-149">Öffnen Sie mit Visual Studio 2010 die Projektmappendatei "documentapprovalprocess. sln".</span><span class="sxs-lookup"><span data-stu-id="b4de9-149">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>

2. <span data-ttu-id="b4de9-150">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-150">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="b4de9-151">Um die Lösung auszuführen, starten Sie die Genehmigungs-Manager-Anwendung, indem Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt approvalmanager klicken und dann im Kontextmenü auf **Debuggen** -> neue Instanz**starten** klicken.</span><span class="sxs-lookup"><span data-stu-id="b4de9-151">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>

    <span data-ttu-id="b4de9-152">Warten Sie auf die Bestätigung des Managers, dass dieser bereit ist.</span><span class="sxs-lookup"><span data-stu-id="b4de9-152">Wait for the manager’s output to let you know that it is ready.</span></span>

##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="b4de9-153">So führen Sie das Einzelgenehmigungsszenario aus</span><span class="sxs-lookup"><span data-stu-id="b4de9-153">To run the single approval scenario</span></span>

1. <span data-ttu-id="b4de9-154">Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-154">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="b4de9-155">Navigieren Sie zum Verzeichnis, das die Projektmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="b4de9-155">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="b4de9-156">Navigieren Sie zum Ordner ApprovalClient\Bin\Debug, und führen Sie zwei Instanzen von ApprovalClient.exe aus.</span><span class="sxs-lookup"><span data-stu-id="b4de9-156">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="b4de9-157">Klicken Sie auf **ermitteln**, warten Sie, bis die Schaltfläche **abonnieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b4de9-157">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="b4de9-158">Geben Sie einen Benutzernamen ein, und klicken Sie auf **abonnieren**</span><span class="sxs-lookup"><span data-stu-id="b4de9-158">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="b4de9-159">Verwenden Sie für einen Client `UserType1` und für den anderen den Typ `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="b4de9-159">For one client, use `UserType1` and the other type `UserType2`.</span></span>

6. <span data-ttu-id="b4de9-160">Wählen Sie im `UserType1`-Client den Einzelgenehmigungstyp im Dropdownmenü aus, und geben Sie einen Dokumentnamen und -inhalt ein.</span><span class="sxs-lookup"><span data-stu-id="b4de9-160">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="b4de9-161">Klicken Sie auf **Genehmigung anfordern**.</span><span class="sxs-lookup"><span data-stu-id="b4de9-161">Click **Request Approval**.</span></span>

7. <span data-ttu-id="b4de9-162">Im `UserType2`-Client wird ein Dokument, das auf Genehmigung wartet, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4de9-162">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="b4de9-163">Wählen Sie es aus, und drücken Sie **genehmigen** oder **ablehnen**.</span><span class="sxs-lookup"><span data-stu-id="b4de9-163">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="b4de9-164">Die Ergebnisse werden im `UserType1`-Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4de9-164">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="b4de9-165">So führen Sie das Quorumgenehmigungsszenario aus</span><span class="sxs-lookup"><span data-stu-id="b4de9-165">To run the quorum approval scenario</span></span>

1. <span data-ttu-id="b4de9-166">Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-166">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="b4de9-167">Navigieren Sie zum Verzeichnis, das die Projektmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="b4de9-167">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="b4de9-168">Navigieren Sie zum Ordner ApprovalClient\Bin\Debug, und führen Sie drei Instanzen von ApprovalClient.exe aus.</span><span class="sxs-lookup"><span data-stu-id="b4de9-168">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="b4de9-169">Klicken Sie auf **ermitteln**, warten Sie, bis die Schaltfläche **abonnieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b4de9-169">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="b4de9-170">Geben Sie einen Benutzernamen ein, und klicken Sie auf **abonnieren**</span><span class="sxs-lookup"><span data-stu-id="b4de9-170">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="b4de9-171">Verwenden Sie für einen Client `UserType1` und für die anderen den Typ `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="b4de9-171">For one client use `UserType1` and the other two type `UserType2`.</span></span>

6. <span data-ttu-id="b4de9-172">Wählen Sie im `UserType1`-Client den Quorumgenehmigungstyp im Dropdownmenü aus, und geben Sie einen Dokumentnamen und -inhalt ein.</span><span class="sxs-lookup"><span data-stu-id="b4de9-172">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="b4de9-173">Klicken Sie auf **Genehmigung anfordern**.</span><span class="sxs-lookup"><span data-stu-id="b4de9-173">Click **Request Approval**.</span></span> <span data-ttu-id="b4de9-174">Hierdurch wird angefordert, dass die beiden `UserType2`-Clients das Dokument genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-174">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="b4de9-175">Während beide `UserType2`-Clients antworten müssen, muss nur ein Client das Dokument genehmigen, damit es genehmigt wird.</span><span class="sxs-lookup"><span data-stu-id="b4de9-175">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>

7. <span data-ttu-id="b4de9-176">In den `UserType2`-Clients wird ein Dokument, das auf Genehmigung wartet, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4de9-176">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="b4de9-177">Wählen Sie es aus, und drücken Sie **genehmigen** oder **ablehnen**.</span><span class="sxs-lookup"><span data-stu-id="b4de9-177">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="b4de9-178">Die Ergebnisse werden im `UserType1`-Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4de9-178">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="b4de9-179">So führen Sie das komplexe Genehmigungsszenario aus</span><span class="sxs-lookup"><span data-stu-id="b4de9-179">To run the complex approval scenario</span></span>

1. <span data-ttu-id="b4de9-180">Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b4de9-180">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="b4de9-181">Navigieren Sie zum Verzeichnis, das die Projektmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="b4de9-181">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="b4de9-182">Navigieren Sie zum Ordner ApprovalClient\Bin\Debug, und führen Sie vier Instanzen von ApprovalClient.exe aus.</span><span class="sxs-lookup"><span data-stu-id="b4de9-182">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="b4de9-183">Klicken Sie auf **ermitteln**, warten Sie, bis die Schaltfläche **abonnieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b4de9-183">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="b4de9-184">Geben Sie einen Benutzernamen ein, und klicken Sie auf **abonnieren**</span><span class="sxs-lookup"><span data-stu-id="b4de9-184">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="b4de9-185">Verwenden Sie für einen Client `UserType1`, für zwei Clients `UserType2` und für den vierten Client `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="b4de9-185">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>

6. <span data-ttu-id="b4de9-186">Wählen Sie im `UserType1`-Client den Einzelgenehmigungstyp im Dropdownmenü aus, und geben Sie einen Dokumentnamen und -inhalt ein.</span><span class="sxs-lookup"><span data-stu-id="b4de9-186">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="b4de9-187">Klicken Sie auf **Genehmigung anfordern**.</span><span class="sxs-lookup"><span data-stu-id="b4de9-187">Click **Request Approval**.</span></span>

7. <span data-ttu-id="b4de9-188">In den `UserType2`-Clients wird ein Dokument, das auf Genehmigung wartet, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4de9-188">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="b4de9-189">Wählen Sie diese Option aus, und drücken Sie **genehmigen**, das Dokument wird an den Client weitergegeben `UserType3` .</span><span class="sxs-lookup"><span data-stu-id="b4de9-189">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>

    <span data-ttu-id="b4de9-190">Wenn das Dokument vom ersten `UserType2`-Quorum genehmigt wird, wird das Dokument an den `UserType3`-Client übergeben.</span><span class="sxs-lookup"><span data-stu-id="b4de9-190">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>

8. <span data-ttu-id="b4de9-191">Genehmigen Sie das Dokument im `UserType3`-Client, oder lehnen Sie es ab.</span><span class="sxs-lookup"><span data-stu-id="b4de9-191">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="b4de9-192">Die Ergebnisse werden im `UserType1`-Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4de9-192">The results should show in the `UserType1` client.</span></span>

##### <a name="to-clean-up"></a><span data-ttu-id="b4de9-193">So führen Sie eine Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="b4de9-193">To clean up</span></span>

1. <span data-ttu-id="b4de9-194">Navigieren Sie an einer Visual Studio 2010-Eingabeaufforderung zum Ordner documentapprovalprocess, und führen Sie Cleanup. cmd aus.</span><span class="sxs-lookup"><span data-stu-id="b4de9-194">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
