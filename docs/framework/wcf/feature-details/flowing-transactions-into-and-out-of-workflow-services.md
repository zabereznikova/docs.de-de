---
title: Transaktionsfluss in Workflowdienste und aus Workflowdiensten
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: a74a2a82e63ddd6c331dd90f9eb894ed5069da3d
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675717"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="3264f-102">Transaktionsfluss in Workflowdienste und aus Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="3264f-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="3264f-103">Workflowdienste und Clients können an Transaktionen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="3264f-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="3264f-104">Damit ein Dienstvorgang Teil einer Ambient-Transaktion wird, fügen Sie eine <xref:System.ServiceModel.Activities.Receive>-Aktivität in eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität ein.</span><span class="sxs-lookup"><span data-stu-id="3264f-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="3264f-105">Alle Aufrufe, die von einer <xref:System.ServiceModel.Activities.Send>-Aktivität oder einer <xref:System.ServiceModel.Activities.SendReply>-Aktivität in <xref:System.ServiceModel.Activities.TransactedReceiveScope> durchgeführt werden, werden auch in der Ambient-Transaktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="3264f-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="3264f-106">Eine Workflowclientanwendung kann mit der <xref:System.Activities.Statements.TransactionScope>-Aktivität eine Ambient-Transaktion erstellen und Dienstvorgänge mithilfe der Ambient-Transaktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3264f-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="3264f-107">In diesem Thema wird die Erstellung eines Workflowdiensts und Workflowclients, die an Transaktionen teilnehmen, erläutert.</span><span class="sxs-lookup"><span data-stu-id="3264f-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3264f-108">Wenn eine Workflowdienstinstanz innerhalb einer Transaktion geladen wird und der Workflow eine <xref:System.Activities.Statements.Persist>-Aktivität enthält, bleibt die Workflowinstanz bis zum Timeout der Transaktion hängen.</span><span class="sxs-lookup"><span data-stu-id="3264f-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will hang until the transaction times out.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3264f-109">Es wird empfohlen, bei Verwendung von <xref:System.ServiceModel.Activities.TransactedReceiveScope> alle empfangenen Nachrichten im Workflow in <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivitäten zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="3264f-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3264f-110">Wenn Sie <xref:System.ServiceModel.Activities.TransactedReceiveScope> verwenden und Nachrichten in der falschen Reihenfolge eintreffen, wird beim Versuch, die erste der Nachrichten außerhalb der normalen Reihenfolge zu übermitteln, der Workflow abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="3264f-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="3264f-111">Sie müssen sicherstellen, dass der Workflow im Leerlauf stets einen konsistenten Haltepunkt aufweist.</span><span class="sxs-lookup"><span data-stu-id="3264f-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="3264f-112">Falls der Workflow abgebrochen wird, können Sie ihn auf diese Weise anhand eines früheren Persistenzpunkts erneut starten.</span><span class="sxs-lookup"><span data-stu-id="3264f-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="3264f-113">Erstellen einer freigegebenen Bibliothek</span><span class="sxs-lookup"><span data-stu-id="3264f-113">Create a shared library</span></span>  
  
1.  <span data-ttu-id="3264f-114">Erstellen Sie eine neue leere Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="3264f-114">Create a new empty Visual Studio Solution.</span></span>  
  
2.  <span data-ttu-id="3264f-115">Fügen Sie ein neues Klassenbibliotheksprojekt mit dem Namen `Common` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3264f-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="3264f-116">Fügen Sie Verweise auf die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="3264f-116">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="3264f-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="3264f-117">System.Activities.dll</span></span>  
  
    -   <span data-ttu-id="3264f-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="3264f-118">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="3264f-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="3264f-119">System.ServiceModel.Activities.dll</span></span>  
  
    -   <span data-ttu-id="3264f-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="3264f-120">System.Transactions.dll</span></span>  
  
3.  <span data-ttu-id="3264f-121">Fügen Sie dem `PrintTransactionInfo`-Projekt eine neue Klasse mit dem Namen `Common` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3264f-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="3264f-122">Diese Klasse wird von <xref:System.Activities.NativeActivity> abgeleitet und überlädt die <xref:System.Activities.NativeActivity.Execute%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="3264f-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
    ```  
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     <span data-ttu-id="3264f-123">Diese native Aktivität, in der Informationen zur Ambient-Transaktion angezeigt werden, wird in den in diesem Thema verwendeten Dienst- und Clientworkflows eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="3264f-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="3264f-124">Erstellen Sie die Projektmappe, um diese Aktivität in verfügbar zu machen die **allgemeine** Teil der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="3264f-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="3264f-125">Implementieren des Workflowdiensts</span><span class="sxs-lookup"><span data-stu-id="3264f-125">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="3264f-126">Fügen Sie eine neue WCF-Workflowdienst aufgerufen `WorkflowService` auf die `Common` Projekt.</span><span class="sxs-lookup"><span data-stu-id="3264f-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="3264f-127">Rechts klicken Sie hierzu die `Common` -Projekt, wählen **hinzufügen**, **neues Element...** Option **Workflow** unter **installierte Vorlagen** , und wählen Sie **WCF-Workflowdienst**.</span><span class="sxs-lookup"><span data-stu-id="3264f-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     ![Hinzufügen eines Workflowdiensts](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2.  <span data-ttu-id="3264f-129">Löschen Sie die `ReceiveRequest`-Standardaktivität und `SendResponse`-Standardaktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3.  <span data-ttu-id="3264f-130">Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die `Sequential Service`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="3264f-131">Legen Sie die Texteigenschaft auf `"Workflow Service starting ..."` fest, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3264f-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="3264f-132">! [Hinzufügen einer WriteLine-Aktivität, die activity(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg) sequenzieller Dienst</span><span class="sxs-lookup"><span data-stu-id="3264f-132">![Adding a WriteLine activity to the Sequential Service activity(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span></span>  
  
4.  <span data-ttu-id="3264f-133">Verschieben Sie eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="3264f-134">Die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität finden Sie in der **Messaging** Teil der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="3264f-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="3264f-135">Die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität besteht aus zwei Abschnitten **anfordern** und **Text**.</span><span class="sxs-lookup"><span data-stu-id="3264f-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="3264f-136">Die **anfordern** Abschnitt enthält die <xref:System.ServiceModel.Activities.Receive> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="3264f-137">Die **Text** Abschnitt enthält die Aktivitäten, die innerhalb einer Transaktion ausgeführt werden soll, nachdem eine Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="3264f-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     ![Hinzufügen einer TransactedReceiveScope-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5.  <span data-ttu-id="3264f-139">Wählen Sie die <xref:System.ServiceModel.Activities.TransactedReceiveScope> -Aktivität, und klicken Sie auf die **Variablen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="3264f-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="3264f-140">Fügen Sie die folgenden Variablen hinzu:</span><span class="sxs-lookup"><span data-stu-id="3264f-140">Add the following variables.</span></span>  
  
     ![Hinzufügen von Variablen zum TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    >  <span data-ttu-id="3264f-142">Sie können die standardmäßig vorhandene Datenvariable löschen.</span><span class="sxs-lookup"><span data-stu-id="3264f-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="3264f-143">Sie können auch die vorhandene Handlevariable verwenden.</span><span class="sxs-lookup"><span data-stu-id="3264f-143">You can also use the existing handle variable.</span></span>  
  
6.  <span data-ttu-id="3264f-144">Drag & drop eine <xref:System.ServiceModel.Activities.Receive> Aktivität innerhalb der **anfordern** Teil der <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="3264f-145">Legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="3264f-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="3264f-146">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3264f-146">Property</span></span>|<span data-ttu-id="3264f-147">Wert</span><span class="sxs-lookup"><span data-stu-id="3264f-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="3264f-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="3264f-148">CanCreateInstance</span></span>|<span data-ttu-id="3264f-149">Wahr (aktivieren Sie das Kontrollkästchen)</span><span class="sxs-lookup"><span data-stu-id="3264f-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="3264f-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="3264f-150">OperationName</span></span>|<span data-ttu-id="3264f-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="3264f-151">StartSample</span></span>|  
    |<span data-ttu-id="3264f-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="3264f-152">ServiceContractName</span></span>|<span data-ttu-id="3264f-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="3264f-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="3264f-154">Der Workflow müsste wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="3264f-154">The workflow should look like this:</span></span>  
  
     ![Hinzufügen einer Receive-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7.  <span data-ttu-id="3264f-156">Klicken Sie auf die **definieren...**  -link in der <xref:System.ServiceModel.Activities.Receive> Aktivität, und stellen Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3264f-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     ![Festlegen von meldungseinstellungen für die Receive-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8.  <span data-ttu-id="3264f-158">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag &amp; Drop in den Textabschnitt vom <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="3264f-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="3264f-159">Verschieben Sie innerhalb der <xref:System.Activities.Statements.Sequence>-Aktivität zwei <xref:System.Activities.Statements.WriteLine>-Aktivitäten per Drag &amp; Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaften wie in der folgenden Tabelle gezeigt fest.</span><span class="sxs-lookup"><span data-stu-id="3264f-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="3264f-160">Aktivität</span><span class="sxs-lookup"><span data-stu-id="3264f-160">Activity</span></span>|<span data-ttu-id="3264f-161">Wert</span><span class="sxs-lookup"><span data-stu-id="3264f-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="3264f-162">1. WriteLine</span><span class="sxs-lookup"><span data-stu-id="3264f-162">1st WriteLine</span></span>|<span data-ttu-id="3264f-163">"Service: Erhalten Sie abgeschlossene"</span><span class="sxs-lookup"><span data-stu-id="3264f-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="3264f-164">2. WriteLine</span><span class="sxs-lookup"><span data-stu-id="3264f-164">2nd WriteLine</span></span>|<span data-ttu-id="3264f-165">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="3264f-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="3264f-166">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="3264f-166">The workflow should now look like this:</span></span>  
  
     ![Sequenzieren Sie nach dem Hinzufügen von WriteLine-Aktivitäten](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. <span data-ttu-id="3264f-168">Drag & drop die `PrintTransactionInfo` Aktivität nach der zweiten <xref:System.Activities.Statements.WriteLine> -Aktivität in der **Text** in die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     ![Sequenzieren Sie nach dem Hinzufügen von PrintTransactionInfo](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. <span data-ttu-id="3264f-170">Ziehen Sie eine <xref:System.Activities.Statements.Assign>-Aktivität per Drag &amp; Drop an die Stelle nach der `PrintTransactionInfo`-Aktivität, und legen Sie die Eigenschaften entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="3264f-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="3264f-171">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3264f-171">Property</span></span>|<span data-ttu-id="3264f-172">Wert</span><span class="sxs-lookup"><span data-stu-id="3264f-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="3264f-173">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3264f-173">To</span></span>|<span data-ttu-id="3264f-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="3264f-174">replyMessage</span></span>|  
    |<span data-ttu-id="3264f-175">Wert</span><span class="sxs-lookup"><span data-stu-id="3264f-175">Value</span></span>|<span data-ttu-id="3264f-176">"Service: Senden von Antworten."</span><span class="sxs-lookup"><span data-stu-id="3264f-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="3264f-177">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität nach dem die <xref:System.Activities.Statements.Assign> Aktivität, und legen dessen <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft auf "Service: Beginnen Sie Antwort."</span><span class="sxs-lookup"><span data-stu-id="3264f-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="3264f-178">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="3264f-178">The workflow should now look like this:</span></span>  
  
     ![Nach dem Hinzufügen von Assign und WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. <span data-ttu-id="3264f-180">Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Receive> Aktivität, und wählen **SendReply erstellen** und fügen Sie ihn nach dem letzten <xref:System.Activities.Statements.WriteLine> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="3264f-181">Klicken Sie auf die **definieren...**  -link in der `SendReplyToReceive` Aktivität, und stellen Sie die folgenden Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3264f-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     ![Einstellungen der Antwortmeldung](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. <span data-ttu-id="3264f-183">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität nach dem die `SendReplyToReceive` Aktivität, und legen sie verfügt über <xref:System.Activities.Statements.WriteLine.Text%2A> -Eigenschaft auf "Service: Antwort gesendet."</span><span class="sxs-lookup"><span data-stu-id="3264f-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="3264f-184">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität am unteren Rand der Workflow, und legen dessen <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft auf "Service: Workflow ends, press ENTER um zu beenden. "</span><span class="sxs-lookup"><span data-stu-id="3264f-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="3264f-185">Der abgeschlossene Dienstworkflow müsste wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="3264f-185">The completed service workflow should look like this:</span></span>  
  
     ![Vollständiger Serviceworkflow](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="3264f-187">Implementieren des Workflowclients</span><span class="sxs-lookup"><span data-stu-id="3264f-187">Implement the workflow client</span></span>  
  
1.  <span data-ttu-id="3264f-188">Fügen Sie eine neue WCF-Workflowanwendung mit dem Namen `WorkflowClient` zum `Common`-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="3264f-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="3264f-189">Rechts klicken Sie hierzu die `Common` -Projekt, wählen **hinzufügen**, **neues Element...** Option **Workflow** unter **installierte Vorlagen** , und wählen Sie **Aktivität**.</span><span class="sxs-lookup"><span data-stu-id="3264f-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     ![Aktivitätsprojekt hinzufügen](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2.  <span data-ttu-id="3264f-191">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag &amp; Drop auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="3264f-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3.  <span data-ttu-id="3264f-192">Verschieben Sie in der <xref:System.Activities.Statements.Sequence>-Aktivität eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf `"Client: Workflow starting"` fest.</span><span class="sxs-lookup"><span data-stu-id="3264f-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="3264f-193">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="3264f-193">The workflow should now look like this:</span></span>  
  
     ![Eine WriteLine-Aktivität hinzufügen](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4.  <span data-ttu-id="3264f-195">Verschieben Sie eine <xref:System.Activities.Statements.TransactionScope>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="3264f-196">Wählen Sie die <xref:System.Activities.Statements.TransactionScope>-Aktivität aus, klicken Sie auf die Schaltfläche Variablen, und fügen Sie die folgenden Variablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="3264f-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     ![Variablen zu TransactionScope hinzufügen](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5.  <span data-ttu-id="3264f-198">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag &amp; Drop in den Text der <xref:System.Activities.Statements.TransactionScope>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6.  <span data-ttu-id="3264f-199">Verschieben Sie eine `PrintTransactionInfo`-Aktivität per Drag &amp; Drop innerhalb der <xref:System.Activities.Statements.Sequence>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7.  <span data-ttu-id="3264f-200">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität nach dem die `PrintTransactionInfo` Aktivität, und legen dessen <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft auf "Client: Beginnen senden".</span><span class="sxs-lookup"><span data-stu-id="3264f-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="3264f-201">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="3264f-201">The workflow should now look like this:</span></span>  
  
     ![Hinzufügen des Clients: Beginn der Send-Aktivitäten](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8.  <span data-ttu-id="3264f-203">Ziehen Sie eine <xref:System.ServiceModel.Activities.Send>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.Assign>-Aktivität, und legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="3264f-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="3264f-204">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3264f-204">Property</span></span>|<span data-ttu-id="3264f-205">Wert</span><span class="sxs-lookup"><span data-stu-id="3264f-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="3264f-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="3264f-206">EndpointConfigurationName</span></span>|<span data-ttu-id="3264f-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="3264f-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="3264f-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="3264f-208">OperationName</span></span>|<span data-ttu-id="3264f-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="3264f-209">StartSample</span></span>|  
    |<span data-ttu-id="3264f-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="3264f-210">ServiceContractName</span></span>|<span data-ttu-id="3264f-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="3264f-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="3264f-212">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="3264f-212">The workflow should now look like this:</span></span>  
  
     ![Festlegen der Send-Aktivitätseigenschaften](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. <span data-ttu-id="3264f-214">Klicken Sie auf die **definieren...**  verknüpfen, und legen Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3264f-214">Click the **Define...** link and make the following settings:</span></span>  
  
     ![Meldungseinstellungen für die Send-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. <span data-ttu-id="3264f-216">Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Send> Aktivität, und wählen **ReceiveReply erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3264f-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="3264f-217">Die <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität wird automatisch nach der <xref:System.ServiceModel.Activities.Send>-Aktivität platziert.</span><span class="sxs-lookup"><span data-stu-id="3264f-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="3264f-218">Klicken Sie in der ReceiveReplyForSend-Aktivität auf den Link Definieren..., und legen Sie die folgenden Einstellungen fest:</span><span class="sxs-lookup"><span data-stu-id="3264f-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     ![Festlegen der ReceiveForSend-Meldungseinstellungen](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. <span data-ttu-id="3264f-220">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität zwischen der <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.ReceiveReply> Aktivitäten und legen seine <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft auf "Client: Senden Sie abgeschlossen".</span><span class="sxs-lookup"><span data-stu-id="3264f-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="3264f-221">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität nach dem die <xref:System.ServiceModel.Activities.ReceiveReply> Aktivität, und legen dessen <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft "Clientseite: Empfangene Antwort = "+ replymessage fest</span><span class="sxs-lookup"><span data-stu-id="3264f-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="3264f-222">Verschieben Sie eine `PrintTransactionInfo`-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3264f-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="3264f-223">Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop an das Ende des Workflows, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client workflow ends" fest.</span><span class="sxs-lookup"><span data-stu-id="3264f-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="3264f-224">Der abgeschlossene Clientworkflow sollte wie das folgende Diagramm aussehen.</span><span class="sxs-lookup"><span data-stu-id="3264f-224">The completed client workflow should look like the following diagram.</span></span>  
  
     ![Der abgeschlossene clientworkflow](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. <span data-ttu-id="3264f-226">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="3264f-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="3264f-227">Erstellen der Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="3264f-227">Create the Service application</span></span>  
  
1.  <span data-ttu-id="3264f-228">Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Service` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3264f-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="3264f-229">Fügen Sie Verweise auf die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="3264f-229">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="3264f-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="3264f-230">System.Activities.dll</span></span>  
  
    2.  <span data-ttu-id="3264f-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="3264f-231">System.ServiceModel.dll</span></span>  
  
    3.  <span data-ttu-id="3264f-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="3264f-232">System.ServiceModel.Activities.dll</span></span>  
  
2.  <span data-ttu-id="3264f-233">Öffnen Sie die generierte Datei Program.cs und den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="3264f-233">Open the generated Program.cs file and the following code:</span></span>  
  
    ```  
    static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3.  <span data-ttu-id="3264f-234">Fügen Sie dem Projekt die folgende app.config-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="3264f-234">Add the following app.config file to the project.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a><span data-ttu-id="3264f-235">Erstellen der Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="3264f-235">Create the client application</span></span>  
  
1.  <span data-ttu-id="3264f-236">Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Client` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3264f-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="3264f-237">Fügen Sie einen Verweis auf System.Activities.dll hinzu.</span><span class="sxs-lookup"><span data-stu-id="3264f-237">Add a reference to System.Activities.dll.</span></span>  
  
2.  <span data-ttu-id="3264f-238">Öffnen Sie die Datei program.cs, und fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="3264f-238">Open the program.cs file and add the following code.</span></span>  
  
    ```  
    class Program  
        {  
  
            private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
            static void Main(string[] args)  
            {  
                //Build client  
                Console.WriteLine("Building the client.");  
                WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
                client.Completed = Program.Completed;  
                client.Aborted = Program.Aborted;  
                client.OnUnhandledException = Program.OnUnhandledException;  
  
                //Wait for service to start  
                Console.WriteLine("Press ENTER once service is started.");  
                Console.ReadLine();  
  
                //Start the client              
                Console.WriteLine("Starting the client.");  
                client.Run();  
                syncEvent.WaitOne();  
  
                //Sample complete  
                Console.WriteLine();  
                Console.WriteLine("Client complete. Press ENTER to exit.");  
                Console.ReadLine();  
            }  
  
            private static void Completed(WorkflowApplicationCompletedEventArgs e)  
            {  
                Program.syncEvent.Set();  
            }  
  
            private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
            {  
                Console.WriteLine("Client Aborted: {0}", e.Reason);  
                Program.syncEvent.Set();  
            }  
  
            private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
            {  
                Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
                return UnhandledExceptionAction.Cancel;  
            }  
        }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3264f-239">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3264f-239">See also</span></span>

- [<span data-ttu-id="3264f-240">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="3264f-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="3264f-241">Übersicht über Windows Communication Foundation-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="3264f-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
