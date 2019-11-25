---
title: Transaktionsfluss in Workflowdienste und aus Workflowdiensten
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: ea14bc651258684fd31940aa6b88f9731348dcd1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978283"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="b21eb-102">Transaktionsfluss in Workflowdienste und aus Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="b21eb-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="b21eb-103">Workflowdienste und Clients können an Transaktionen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="b21eb-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="b21eb-104">Damit ein Dienstvorgang Teil einer Ambient-Transaktion wird, fügen Sie eine <xref:System.ServiceModel.Activities.Receive>-Aktivität in eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität ein.</span><span class="sxs-lookup"><span data-stu-id="b21eb-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="b21eb-105">Alle Aufrufe, die von einer <xref:System.ServiceModel.Activities.Send>-Aktivität oder einer <xref:System.ServiceModel.Activities.SendReply>-Aktivität in <xref:System.ServiceModel.Activities.TransactedReceiveScope> durchgeführt werden, werden auch in der Ambient-Transaktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="b21eb-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="b21eb-106">Eine Workflowclientanwendung kann mit der <xref:System.Activities.Statements.TransactionScope>-Aktivität eine Ambient-Transaktion erstellen und Dienstvorgänge mithilfe der Ambient-Transaktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b21eb-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="b21eb-107">In diesem Thema wird die Erstellung eines Workflowdiensts und Workflowclients, die an Transaktionen teilnehmen, erläutert.</span><span class="sxs-lookup"><span data-stu-id="b21eb-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="b21eb-108">Wenn eine Workflow Dienst Instanz innerhalb einer Transaktion geladen wird und der Workflow eine <xref:System.Activities.Statements.Persist> Aktivität enthält, wird die Workflow Instanz bis zum Timeout der Transaktion blockiert.</span><span class="sxs-lookup"><span data-stu-id="b21eb-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will block until the transaction times out.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b21eb-109">Es wird empfohlen, bei Verwendung von <xref:System.ServiceModel.Activities.TransactedReceiveScope> alle empfangenen Nachrichten im Workflow in <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivitäten zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="b21eb-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b21eb-110">Wenn Sie <xref:System.ServiceModel.Activities.TransactedReceiveScope> verwenden und Nachrichten in der falschen Reihenfolge eintreffen, wird beim Versuch, die erste der Nachrichten außerhalb der normalen Reihenfolge zu übermitteln, der Workflow abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="b21eb-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="b21eb-111">Sie müssen sicherstellen, dass der Workflow im Leerlauf stets einen konsistenten Haltepunkt aufweist.</span><span class="sxs-lookup"><span data-stu-id="b21eb-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="b21eb-112">Falls der Workflow abgebrochen wird, können Sie ihn auf diese Weise anhand eines früheren Persistenzpunkts erneut starten.</span><span class="sxs-lookup"><span data-stu-id="b21eb-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="b21eb-113">Erstellen einer freigegebenen Bibliothek</span><span class="sxs-lookup"><span data-stu-id="b21eb-113">Create a shared library</span></span>  
  
1. <span data-ttu-id="b21eb-114">Erstellen Sie eine neue leere Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="b21eb-114">Create a new empty Visual Studio Solution.</span></span>  
  
2. <span data-ttu-id="b21eb-115">Fügen Sie ein neues Klassenbibliotheksprojekt mit dem Namen `Common` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="b21eb-116">Fügen Sie Verweise auf die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="b21eb-116">Add references to the following assemblies:</span></span>  
  
    - <span data-ttu-id="b21eb-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="b21eb-117">System.Activities.dll</span></span>  
  
    - <span data-ttu-id="b21eb-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="b21eb-118">System.ServiceModel.dll</span></span>  
  
    - <span data-ttu-id="b21eb-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="b21eb-119">System.ServiceModel.Activities.dll</span></span>  
  
    - <span data-ttu-id="b21eb-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="b21eb-120">System.Transactions.dll</span></span>  
  
3. <span data-ttu-id="b21eb-121">Fügen Sie dem `PrintTransactionInfo`-Projekt eine neue Klasse mit dem Namen `Common` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="b21eb-122">Diese Klasse wird von <xref:System.Activities.NativeActivity> abgeleitet und überlädt die <xref:System.Activities.NativeActivity.Execute%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="b21eb-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
    ```csharp
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
  
     <span data-ttu-id="b21eb-123">Diese native Aktivität, in der Informationen zur Ambient-Transaktion angezeigt werden, wird in den in diesem Thema verwendeten Dienst- und Clientworkflows eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="b21eb-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="b21eb-124">Erstellen Sie die Projekt Mappe, um diese Aktivität im **allgemeinen** Abschnitt der **Toolbox**verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="b21eb-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="b21eb-125">Implementieren des Workflowdiensts</span><span class="sxs-lookup"><span data-stu-id="b21eb-125">Implement the workflow service</span></span>  
  
1. <span data-ttu-id="b21eb-126">Fügen Sie dem `Common` Projekt einen neuen WCF-Workflow Dienst namens "`WorkflowService`" hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="b21eb-127">Klicken Sie dazu mit der rechten Maustaste auf das Projekt `Common`, wählen Sie **Hinzufügen**, **Neues Element**aus, wählen Sie unter **installierte Vorlagen** die Option **Workflow** , und wählen Sie **WCF-Workflow Dienst**aus.</span><span class="sxs-lookup"><span data-stu-id="b21eb-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     ![Hinzufügen eines Workflowdiensts](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2. <span data-ttu-id="b21eb-129">Löschen Sie die `ReceiveRequest`-Standardaktivität und `SendResponse`-Standardaktivität.</span><span class="sxs-lookup"><span data-stu-id="b21eb-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3. <span data-ttu-id="b21eb-130">Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die `Sequential Service`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b21eb-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="b21eb-131">Legen Sie die Texteigenschaft auf `"Workflow Service starting ..."` fest, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b21eb-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="b21eb-132">! [Hinzufügen einer "Write teline"-Aktivität zur Aktivität "sequenzieller Dienst" (./Media/Flowing-Transactions-into-and-out-of-Workflow-Services/Add-WriteLine-Sequential-Service.jpg)</span><span class="sxs-lookup"><span data-stu-id="b21eb-132">![Adding a WriteLine activity to the Sequential Service activity(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span></span>  
  
4. <span data-ttu-id="b21eb-133">Verschieben Sie eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b21eb-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="b21eb-134">Die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität befindet sich im Abschnitt **Messaging** der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="b21eb-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="b21eb-135">Die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität besteht aus zwei Abschnitten: **Anforderung** und **Text**.</span><span class="sxs-lookup"><span data-stu-id="b21eb-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="b21eb-136">Der **Anforderungs** Abschnitt enthält die <xref:System.ServiceModel.Activities.Receive> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b21eb-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="b21eb-137">Der **Text** Abschnitt enthält die Aktivitäten, die innerhalb einer Transaktion ausgeführt werden sollen, nachdem eine Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b21eb-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     ![Hinzufügen einer TransactedReceiveScope-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5. <span data-ttu-id="b21eb-139">Wählen Sie <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität aus, und klicken Sie auf die Schaltfläche **Variablen** .</span><span class="sxs-lookup"><span data-stu-id="b21eb-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="b21eb-140">Fügen Sie die folgenden Variablen hinzu:</span><span class="sxs-lookup"><span data-stu-id="b21eb-140">Add the following variables.</span></span>  
  
     ![Hinzufügen von Variablen zu transactedreceivescope](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    > <span data-ttu-id="b21eb-142">Sie können die standardmäßig vorhandene Datenvariable löschen.</span><span class="sxs-lookup"><span data-stu-id="b21eb-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="b21eb-143">Sie können auch die vorhandene Handlevariable verwenden.</span><span class="sxs-lookup"><span data-stu-id="b21eb-143">You can also use the existing handle variable.</span></span>  
  
6. <span data-ttu-id="b21eb-144">Ziehen Sie eine <xref:System.ServiceModel.Activities.Receive>-Aktivität per Drag & Drop im **Anforderungs** Abschnitt der Aktivität <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="b21eb-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="b21eb-145">Legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="b21eb-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="b21eb-146">property</span><span class="sxs-lookup"><span data-stu-id="b21eb-146">Property</span></span>|<span data-ttu-id="b21eb-147">Wert</span><span class="sxs-lookup"><span data-stu-id="b21eb-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="b21eb-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="b21eb-148">CanCreateInstance</span></span>|<span data-ttu-id="b21eb-149">Wahr (aktivieren Sie das Kontrollkästchen)</span><span class="sxs-lookup"><span data-stu-id="b21eb-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="b21eb-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="b21eb-150">OperationName</span></span>|<span data-ttu-id="b21eb-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="b21eb-151">StartSample</span></span>|  
    |<span data-ttu-id="b21eb-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="b21eb-152">ServiceContractName</span></span>|<span data-ttu-id="b21eb-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="b21eb-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="b21eb-154">Der Workflow müsste wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b21eb-154">The workflow should look like this:</span></span>  
  
     ![Hinzufügen einer Receive-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7. <span data-ttu-id="b21eb-156">Klicken Sie in der <xref:System.ServiceModel.Activities.Receive> Aktivität auf den Link **definieren...** , und legen Sie die folgenden Einstellungen fest:</span><span class="sxs-lookup"><span data-stu-id="b21eb-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     ![Festlegen von Meldungs Einstellungen für die Receive-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8. <span data-ttu-id="b21eb-158">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag &amp; Drop in den Textabschnitt vom <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="b21eb-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="b21eb-159">Verschieben Sie innerhalb der <xref:System.Activities.Statements.Sequence>-Aktivität zwei <xref:System.Activities.Statements.WriteLine>-Aktivitäten per Drag &amp; Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaften wie in der folgenden Tabelle gezeigt fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="b21eb-160">Aktivität</span><span class="sxs-lookup"><span data-stu-id="b21eb-160">Activity</span></span>|<span data-ttu-id="b21eb-161">Wert</span><span class="sxs-lookup"><span data-stu-id="b21eb-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="b21eb-162">1\. WriteLine</span><span class="sxs-lookup"><span data-stu-id="b21eb-162">1st WriteLine</span></span>|<span data-ttu-id="b21eb-163">"Dienst: empfangen abgeschlossen"</span><span class="sxs-lookup"><span data-stu-id="b21eb-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="b21eb-164">2\. WriteLine</span><span class="sxs-lookup"><span data-stu-id="b21eb-164">2nd WriteLine</span></span>|<span data-ttu-id="b21eb-165">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="b21eb-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="b21eb-166">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b21eb-166">The workflow should now look like this:</span></span>  
  
     ![Sequenz nach dem Hinzufügen von Write-in-Aktivitäten](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. <span data-ttu-id="b21eb-168">Ziehen Sie die `PrintTransactionInfo` Aktivität nach der zweiten <xref:System.Activities.Statements.WriteLine> Aktivität im **Text** in der <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität, und legen Sie Sie dort ab.</span><span class="sxs-lookup"><span data-stu-id="b21eb-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     ![Nach dem Hinzufügen von printtransaktioninfo Sequenzieren](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. <span data-ttu-id="b21eb-170">Ziehen Sie eine <xref:System.Activities.Statements.Assign>-Aktivität per Drag &amp; Drop an die Stelle nach der `PrintTransactionInfo`-Aktivität, und legen Sie die Eigenschaften entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="b21eb-171">property</span><span class="sxs-lookup"><span data-stu-id="b21eb-171">Property</span></span>|<span data-ttu-id="b21eb-172">Wert</span><span class="sxs-lookup"><span data-stu-id="b21eb-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="b21eb-173">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b21eb-173">To</span></span>|<span data-ttu-id="b21eb-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="b21eb-174">replyMessage</span></span>|  
    |<span data-ttu-id="b21eb-175">Wert</span><span class="sxs-lookup"><span data-stu-id="b21eb-175">Value</span></span>|<span data-ttu-id="b21eb-176">"Service: Sending reply."</span><span class="sxs-lookup"><span data-stu-id="b21eb-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="b21eb-177">Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.Assign>-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf „Service: Begin reply“ fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="b21eb-178">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b21eb-178">The workflow should now look like this:</span></span>  
  
     ![Nach dem Hinzufügen von Assign und WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. <span data-ttu-id="b21eb-180">Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Receive> Aktivität, und wählen Sie **SendReply erstellen** aus, und fügen Sie Sie nach dem letzten <xref:System.Activities.Statements.WriteLine></span><span class="sxs-lookup"><span data-stu-id="b21eb-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="b21eb-181">Klicken Sie in der `SendReplyToReceive` Aktivität auf den Link **definieren...** , und legen Sie die folgenden Einstellungen fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     ![Einstellungen der Antwortmeldung](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. <span data-ttu-id="b21eb-183">Ziehen Sie nach der `SendReplyToReceive` <xref:System.Activities.Statements.WriteLine.Text%2A>-Aktivität eine <xref:System.Activities.Statements.WriteLine> Aktivität, und legen Sie Sie auf "Service: Reply sent" fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="b21eb-184">Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop an das Ende des Workflows, und legen Sie die Eigenschaft <xref:System.Activities.Statements.WriteLine.Text%2A> auf "Service: Workflow ends, press ENTER to exit" fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="b21eb-185">Der abgeschlossene Dienstworkflow müsste wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b21eb-185">The completed service workflow should look like this:</span></span>  
  
     ![Vollständiger Serviceworkflow](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="b21eb-187">Implementieren des Workflowclients</span><span class="sxs-lookup"><span data-stu-id="b21eb-187">Implement the workflow client</span></span>  
  
1. <span data-ttu-id="b21eb-188">Fügen Sie eine neue WCF-Workflowanwendung mit dem Namen `WorkflowClient` zum `Common`-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="b21eb-189">Klicken Sie dazu mit der rechten Maustaste auf das Projekt `Common`, wählen Sie **Hinzufügen**, **Neues Element...** , wählen Sie unter **installierte Vorlagen** die Option **Workflow** und dann **Aktivität**aus.</span><span class="sxs-lookup"><span data-stu-id="b21eb-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     ![Aktivitätsprojekt hinzufügen](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2. <span data-ttu-id="b21eb-191">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag &amp; Drop auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="b21eb-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3. <span data-ttu-id="b21eb-192">Verschieben Sie in der <xref:System.Activities.Statements.Sequence>-Aktivität eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf `"Client: Workflow starting"` fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="b21eb-193">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b21eb-193">The workflow should now look like this:</span></span>  
  
     ![Eine WriteLine-Aktivität hinzufügen](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4. <span data-ttu-id="b21eb-195">Verschieben Sie eine <xref:System.Activities.Statements.TransactionScope>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b21eb-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="b21eb-196">Wählen Sie die <xref:System.Activities.Statements.TransactionScope>-Aktivität aus, klicken Sie auf die Schaltfläche Variablen, und fügen Sie die folgenden Variablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     ![Variablen zu TransactionScope hinzufügen](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5. <span data-ttu-id="b21eb-198">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag &amp; Drop in den Text der <xref:System.Activities.Statements.TransactionScope>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b21eb-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6. <span data-ttu-id="b21eb-199">Verschieben Sie eine `PrintTransactionInfo`-Aktivität per Drag &amp; Drop innerhalb der <xref:System.Activities.Statements.Sequence>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b21eb-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7. <span data-ttu-id="b21eb-200">Ziehen Sie eine <xref:System.Activities.Statements.WriteLine> Aktivität nach der `PrintTransactionInfo`-Aktivität, und legen Sie deren <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client: Start Send" fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="b21eb-201">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b21eb-201">The workflow should now look like this:</span></span>  
  
     ![Client wird hinzugefügt: Sendeaktivitäten werden gestartet.](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8. <span data-ttu-id="b21eb-203">Ziehen Sie eine <xref:System.ServiceModel.Activities.Send>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.Assign>-Aktivität, und legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="b21eb-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="b21eb-204">property</span><span class="sxs-lookup"><span data-stu-id="b21eb-204">Property</span></span>|<span data-ttu-id="b21eb-205">Wert</span><span class="sxs-lookup"><span data-stu-id="b21eb-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="b21eb-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="b21eb-206">EndpointConfigurationName</span></span>|<span data-ttu-id="b21eb-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="b21eb-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="b21eb-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="b21eb-208">OperationName</span></span>|<span data-ttu-id="b21eb-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="b21eb-209">StartSample</span></span>|  
    |<span data-ttu-id="b21eb-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="b21eb-210">ServiceContractName</span></span>|<span data-ttu-id="b21eb-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="b21eb-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="b21eb-212">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b21eb-212">The workflow should now look like this:</span></span>  
  
     ![Festlegen der Send-Aktivitätseigenschaften](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. <span data-ttu-id="b21eb-214">Klicken Sie auf den Link **definieren...** , und legen Sie die folgenden Einstellungen fest:</span><span class="sxs-lookup"><span data-stu-id="b21eb-214">Click the **Define...** link and make the following settings:</span></span>  
  
     ![Meldungseinstellungen für die Send-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. <span data-ttu-id="b21eb-216">Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Send> Aktivität, und wählen Sie **receivereply erstellen**</span><span class="sxs-lookup"><span data-stu-id="b21eb-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="b21eb-217">Die <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität wird automatisch nach der <xref:System.ServiceModel.Activities.Send>-Aktivität platziert.</span><span class="sxs-lookup"><span data-stu-id="b21eb-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="b21eb-218">Klicken Sie in der ReceiveReplyForSend-Aktivität auf den Link Definieren..., und legen Sie die folgenden Einstellungen fest:</span><span class="sxs-lookup"><span data-stu-id="b21eb-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     ![Festlegen der ReceiveForSend-Meldungseinstellungen](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. <span data-ttu-id="b21eb-220">Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop zwischen der <xref:System.ServiceModel.Activities.Send>-Aktivität und der <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client: Send complete" fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="b21eb-221">Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client side: Reply received = " + replyMessage fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="b21eb-222">Verschieben Sie eine `PrintTransactionInfo`-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b21eb-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="b21eb-223">Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop an das Ende des Workflows, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client workflow ends" fest.</span><span class="sxs-lookup"><span data-stu-id="b21eb-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="b21eb-224">Der abgeschlossene Clientworkflow sollte wie das folgende Diagramm aussehen.</span><span class="sxs-lookup"><span data-stu-id="b21eb-224">The completed client workflow should look like the following diagram.</span></span>  
  
     ![Der abgeschlossene Client Workflow](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. <span data-ttu-id="b21eb-226">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="b21eb-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="b21eb-227">Erstellen der Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="b21eb-227">Create the Service application</span></span>  
  
1. <span data-ttu-id="b21eb-228">Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Service` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="b21eb-229">Fügen Sie Verweise auf die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="b21eb-229">Add references to the following assemblies:</span></span>  
  
    1. <span data-ttu-id="b21eb-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="b21eb-230">System.Activities.dll</span></span>  
  
    2. <span data-ttu-id="b21eb-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="b21eb-231">System.ServiceModel.dll</span></span>  
  
    3. <span data-ttu-id="b21eb-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="b21eb-232">System.ServiceModel.Activities.dll</span></span>  
  
2. <span data-ttu-id="b21eb-233">Öffnen Sie die generierte Datei Program.cs und den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="b21eb-233">Open the generated Program.cs file and the following code:</span></span>  
  
    ```csharp
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
  
3. <span data-ttu-id="b21eb-234">Fügen Sie dem Projekt die folgende app.config-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-234">Add the following app.config file to the project.</span></span>  
  
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
  
### <a name="create-the-client-application"></a><span data-ttu-id="b21eb-235">Erstellen der Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="b21eb-235">Create the client application</span></span>  
  
1. <span data-ttu-id="b21eb-236">Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Client` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="b21eb-237">Fügen Sie einen Verweis auf System.Activities.dll hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-237">Add a reference to System.Activities.dll.</span></span>  
  
2. <span data-ttu-id="b21eb-238">Öffnen Sie die Datei program.cs, und fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21eb-238">Open the program.cs file and add the following code.</span></span>  
  
    ```csharp
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
  
## <a name="see-also"></a><span data-ttu-id="b21eb-239">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b21eb-239">See also</span></span>

- [<span data-ttu-id="b21eb-240">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="b21eb-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="b21eb-241">Übersicht über Windows Communication Foundation-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="b21eb-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
