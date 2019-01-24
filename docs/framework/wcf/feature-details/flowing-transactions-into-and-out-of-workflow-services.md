---
title: Transaktionsfluss in Workflowdienste und aus Workflowdiensten
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: 4a5cde045c6c676c2efc694c67fd049b6eb611b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708635"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="75aa8-102">Transaktionsfluss in Workflowdienste und aus Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="75aa8-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="75aa8-103">Workflowdienste und Clients können an Transaktionen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="75aa8-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="75aa8-104">Damit ein Dienstvorgang Teil einer Ambient-Transaktion wird, fügen Sie eine <xref:System.ServiceModel.Activities.Receive>-Aktivität in eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität ein.</span><span class="sxs-lookup"><span data-stu-id="75aa8-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="75aa8-105">Alle Aufrufe, die von einer <xref:System.ServiceModel.Activities.Send>-Aktivität oder einer <xref:System.ServiceModel.Activities.SendReply>-Aktivität in <xref:System.ServiceModel.Activities.TransactedReceiveScope> durchgeführt werden, werden auch in der Ambient-Transaktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="75aa8-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="75aa8-106">Eine Workflowclientanwendung kann mit der <xref:System.Activities.Statements.TransactionScope>-Aktivität eine Ambient-Transaktion erstellen und Dienstvorgänge mithilfe der Ambient-Transaktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="75aa8-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="75aa8-107">In diesem Thema wird die Erstellung eines Workflowdiensts und Workflowclients, die an Transaktionen teilnehmen, erläutert.</span><span class="sxs-lookup"><span data-stu-id="75aa8-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="75aa8-108">Wenn eine Workflowdienstinstanz innerhalb einer Transaktion geladen wird und der Workflow eine <xref:System.Activities.Statements.Persist>-Aktivität enthält, bleibt die Workflowinstanz bis zum Timeout der Transaktion hängen.</span><span class="sxs-lookup"><span data-stu-id="75aa8-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will hang until the transaction times out.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="75aa8-109">Es wird empfohlen, bei Verwendung von <xref:System.ServiceModel.Activities.TransactedReceiveScope> alle empfangenen Nachrichten im Workflow in <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivitäten zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="75aa8-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="75aa8-110">Wenn Sie <xref:System.ServiceModel.Activities.TransactedReceiveScope> verwenden und Nachrichten in der falschen Reihenfolge eintreffen, wird beim Versuch, die erste der Nachrichten außerhalb der normalen Reihenfolge zu übermitteln, der Workflow abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="75aa8-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="75aa8-111">Sie müssen sicherstellen, dass der Workflow im Leerlauf stets einen konsistenten Haltepunkt aufweist.</span><span class="sxs-lookup"><span data-stu-id="75aa8-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="75aa8-112">Falls der Workflow abgebrochen wird, können Sie ihn auf diese Weise anhand eines früheren Persistenzpunkts erneut starten.</span><span class="sxs-lookup"><span data-stu-id="75aa8-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="75aa8-113">Erstellen einer freigegebenen Bibliothek</span><span class="sxs-lookup"><span data-stu-id="75aa8-113">Create a shared library</span></span>  
  
1.  <span data-ttu-id="75aa8-114">Erstellen Sie eine neue leere Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="75aa8-114">Create a new empty Visual Studio Solution.</span></span>  
  
2.  <span data-ttu-id="75aa8-115">Fügen Sie ein neues Klassenbibliotheksprojekt mit dem Namen `Common` hinzu.</span><span class="sxs-lookup"><span data-stu-id="75aa8-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="75aa8-116">Fügen Sie Verweise auf die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="75aa8-116">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="75aa8-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="75aa8-117">System.Activities.dll</span></span>  
  
    -   <span data-ttu-id="75aa8-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="75aa8-118">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="75aa8-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="75aa8-119">System.ServiceModel.Activities.dll</span></span>  
  
    -   <span data-ttu-id="75aa8-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="75aa8-120">System.Transactions.dll</span></span>  
  
3.  <span data-ttu-id="75aa8-121">Fügen Sie dem `PrintTransactionInfo`-Projekt eine neue Klasse mit dem Namen `Common` hinzu.</span><span class="sxs-lookup"><span data-stu-id="75aa8-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="75aa8-122">Diese Klasse wird von <xref:System.Activities.NativeActivity> abgeleitet und überlädt die <xref:System.Activities.NativeActivity.Execute%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="75aa8-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="75aa8-123">Diese native Aktivität, in der Informationen zur Ambient-Transaktion angezeigt werden, wird in den in diesem Thema verwendeten Dienst- und Clientworkflows eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="75aa8-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="75aa8-124">Erstellen Sie die Projektmappe, um diese Aktivität in verfügbar zu machen die **allgemeine** Teil der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="75aa8-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="75aa8-125">Implementieren des Workflowdiensts</span><span class="sxs-lookup"><span data-stu-id="75aa8-125">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="75aa8-126">Fügen Sie eine neue WCF-Workflowdienst aufgerufen `WorkflowService` auf die `Common` Projekt.</span><span class="sxs-lookup"><span data-stu-id="75aa8-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="75aa8-127">Rechts klicken Sie hierzu die `Common` -Projekt, wählen **hinzufügen**, **neues Element...** Option **Workflow** unter **installierte Vorlagen** , und wählen Sie **WCF-Workflowdienst**.</span><span class="sxs-lookup"><span data-stu-id="75aa8-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     <span data-ttu-id="75aa8-128">![Hinzufügen eines Workflowdiensts](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span><span class="sxs-lookup"><span data-stu-id="75aa8-128">![Adding a Workflow Service](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span></span>  
  
2.  <span data-ttu-id="75aa8-129">Löschen Sie die `ReceiveRequest`-Standardaktivität und `SendResponse`-Standardaktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3.  <span data-ttu-id="75aa8-130">Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die `Sequential Service`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="75aa8-131">Legen Sie die Texteigenschaft auf `"Workflow Service starting ..."` fest, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="75aa8-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="75aa8-132">![Hinzufügen einer WriteLine-Aktivität](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="75aa8-132">![Adding a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span></span>  
  
4.  <span data-ttu-id="75aa8-133">Verschieben Sie eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität per Drag & Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="75aa8-134">Die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität finden Sie in der **Messaging** Teil der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="75aa8-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="75aa8-135">Die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität besteht aus zwei Abschnitten **anfordern** und **Text**.</span><span class="sxs-lookup"><span data-stu-id="75aa8-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="75aa8-136">Die **anfordern** Abschnitt enthält die <xref:System.ServiceModel.Activities.Receive> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="75aa8-137">Die **Text** Abschnitt enthält die Aktivitäten, die innerhalb einer Transaktion ausgeführt werden soll, nachdem eine Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="75aa8-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     <span data-ttu-id="75aa8-138">![Hinzufügen einer TransactedReceiveScope-Aktivität](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span><span class="sxs-lookup"><span data-stu-id="75aa8-138">![Adding a TransactedReceiveScope activity](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span></span>  
  
5.  <span data-ttu-id="75aa8-139">Wählen Sie die <xref:System.ServiceModel.Activities.TransactedReceiveScope> -Aktivität, und klicken Sie auf die **Variablen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="75aa8-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="75aa8-140">Fügen Sie die folgenden Variablen hinzu:</span><span class="sxs-lookup"><span data-stu-id="75aa8-140">Add the following variables.</span></span>  
  
     <span data-ttu-id="75aa8-141">![Hinzufügen von Variablen zum TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span><span class="sxs-lookup"><span data-stu-id="75aa8-141">![Adding Variables to the TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="75aa8-142">Sie können die standardmäßig vorhandene Datenvariable löschen.</span><span class="sxs-lookup"><span data-stu-id="75aa8-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="75aa8-143">Sie können auch die vorhandene Handlevariable verwenden.</span><span class="sxs-lookup"><span data-stu-id="75aa8-143">You can also use the existing handle variable.</span></span>  
  
6.  <span data-ttu-id="75aa8-144">Drag & drop eine <xref:System.ServiceModel.Activities.Receive> Aktivität innerhalb der **anfordern** Teil der <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="75aa8-145">Legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="75aa8-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="75aa8-146">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="75aa8-146">Property</span></span>|<span data-ttu-id="75aa8-147">Wert</span><span class="sxs-lookup"><span data-stu-id="75aa8-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="75aa8-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="75aa8-148">CanCreateInstance</span></span>|<span data-ttu-id="75aa8-149">Wahr (aktivieren Sie das Kontrollkästchen)</span><span class="sxs-lookup"><span data-stu-id="75aa8-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="75aa8-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="75aa8-150">OperationName</span></span>|<span data-ttu-id="75aa8-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="75aa8-151">StartSample</span></span>|  
    |<span data-ttu-id="75aa8-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="75aa8-152">ServiceContractName</span></span>|<span data-ttu-id="75aa8-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="75aa8-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="75aa8-154">Der Workflow müsste wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="75aa8-154">The workflow should look like this:</span></span>  
  
     <span data-ttu-id="75aa8-155">![Hinzufügen einer Receive-Aktivität](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span><span class="sxs-lookup"><span data-stu-id="75aa8-155">![Adding a Receive activity](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span></span>  
  
7.  <span data-ttu-id="75aa8-156">Klicken Sie auf die **definieren...**  -link in der <xref:System.ServiceModel.Activities.Receive> Aktivität, und stellen Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="75aa8-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     <span data-ttu-id="75aa8-157">![Festlegen von meldungseinstellungen für die empfangen-Aktivität](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="75aa8-157">![Setting message settings for the Recieve activity](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span></span>  
  
8.  <span data-ttu-id="75aa8-158">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag & Drop in den Textabschnitt vom <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="75aa8-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="75aa8-159">Verschieben Sie innerhalb der <xref:System.Activities.Statements.Sequence>-Aktivität zwei <xref:System.Activities.Statements.WriteLine>-Aktivitäten per Drag & Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaften wie in der folgenden Tabelle gezeigt fest.</span><span class="sxs-lookup"><span data-stu-id="75aa8-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="75aa8-160">Aktivität</span><span class="sxs-lookup"><span data-stu-id="75aa8-160">Activity</span></span>|<span data-ttu-id="75aa8-161">Wert</span><span class="sxs-lookup"><span data-stu-id="75aa8-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="75aa8-162">1. WriteLine</span><span class="sxs-lookup"><span data-stu-id="75aa8-162">1st WriteLine</span></span>|<span data-ttu-id="75aa8-163">"Service: Erhalten Sie abgeschlossene"</span><span class="sxs-lookup"><span data-stu-id="75aa8-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="75aa8-164">2. WriteLine</span><span class="sxs-lookup"><span data-stu-id="75aa8-164">2nd WriteLine</span></span>|<span data-ttu-id="75aa8-165">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="75aa8-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="75aa8-166">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="75aa8-166">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="75aa8-167">![Hinzufügen von WriteLine-Aktivitäten](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span><span class="sxs-lookup"><span data-stu-id="75aa8-167">![Adding WriteLine activities](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span></span>  
  
9. <span data-ttu-id="75aa8-168">Drag & drop die `PrintTransactionInfo` Aktivität nach der zweiten <xref:System.Activities.Statements.WriteLine> -Aktivität in der **Text** in die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     <span data-ttu-id="75aa8-169">![Nach dem Hinzufügen von PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span><span class="sxs-lookup"><span data-stu-id="75aa8-169">![After adding PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span></span>  
  
10. <span data-ttu-id="75aa8-170">Ziehen Sie eine <xref:System.Activities.Statements.Assign>-Aktivität per Drag & Drop an die Stelle nach der `PrintTransactionInfo`-Aktivität, und legen Sie die Eigenschaften entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="75aa8-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="75aa8-171">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="75aa8-171">Property</span></span>|<span data-ttu-id="75aa8-172">Wert</span><span class="sxs-lookup"><span data-stu-id="75aa8-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="75aa8-173">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75aa8-173">To</span></span>|<span data-ttu-id="75aa8-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="75aa8-174">replyMessage</span></span>|  
    |<span data-ttu-id="75aa8-175">Wert</span><span class="sxs-lookup"><span data-stu-id="75aa8-175">Value</span></span>|<span data-ttu-id="75aa8-176">"Service: Senden von Antworten."</span><span class="sxs-lookup"><span data-stu-id="75aa8-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="75aa8-177">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität nach dem die <xref:System.Activities.Statements.Assign> Aktivität, und legen dessen <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft auf "Service: Beginnen Sie Antwort."</span><span class="sxs-lookup"><span data-stu-id="75aa8-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="75aa8-178">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="75aa8-178">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="75aa8-179">![Nach dem Hinzufügen von Assign und WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span><span class="sxs-lookup"><span data-stu-id="75aa8-179">![After adding Assign and WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span></span>  
  
12. <span data-ttu-id="75aa8-180">Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Receive> Aktivität, und wählen **SendReply erstellen** und fügen Sie ihn nach dem letzten <xref:System.Activities.Statements.WriteLine> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="75aa8-181">Klicken Sie auf die **definieren...**  -link in der `SendReplyToReceive` Aktivität, und stellen Sie die folgenden Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="75aa8-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     <span data-ttu-id="75aa8-182">![Antwort-meldungseinstellungen](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="75aa8-182">![Reply message settings](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span></span>  
  
13. <span data-ttu-id="75aa8-183">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität nach dem die `SendReplyToReceive` Aktivität, und legen sie verfügt über <xref:System.Activities.Statements.WriteLine.Text%2A> -Eigenschaft auf "Service: Antwort gesendet."</span><span class="sxs-lookup"><span data-stu-id="75aa8-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="75aa8-184">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität am unteren Rand der Workflow, und legen dessen <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft auf "Service: Workflow ends, press ENTER um zu beenden. "</span><span class="sxs-lookup"><span data-stu-id="75aa8-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="75aa8-185">Der abgeschlossene Dienstworkflow müsste wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="75aa8-185">The completed service workflow should look like this:</span></span>  
  
     <span data-ttu-id="75aa8-186">![Vollständiger Serviceworkflow](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span><span class="sxs-lookup"><span data-stu-id="75aa8-186">![Complete Service Workflow](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span></span>  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="75aa8-187">Implementieren des Workflowclients</span><span class="sxs-lookup"><span data-stu-id="75aa8-187">Implement the workflow client</span></span>  
  
1.  <span data-ttu-id="75aa8-188">Fügen Sie eine neue WCF-Workflowanwendung mit dem Namen `WorkflowClient` zum `Common`-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="75aa8-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="75aa8-189">Rechts klicken Sie hierzu die `Common` -Projekt, wählen **hinzufügen**, **neues Element...** Option **Workflow** unter **installierte Vorlagen** , und wählen Sie **Aktivität**.</span><span class="sxs-lookup"><span data-stu-id="75aa8-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     <span data-ttu-id="75aa8-190">![Hinzufügen eines Aktivitätsprojekts](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span><span class="sxs-lookup"><span data-stu-id="75aa8-190">![Add an Activity project](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span></span>  
  
2.  <span data-ttu-id="75aa8-191">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag & Drop auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="75aa8-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3.  <span data-ttu-id="75aa8-192">Verschieben Sie in der <xref:System.Activities.Statements.Sequence>-Aktivität eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag & Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf `"Client: Workflow starting"` fest.</span><span class="sxs-lookup"><span data-stu-id="75aa8-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="75aa8-193">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="75aa8-193">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="75aa8-194">![Hinzufügen eine WriteLine-Aktivität](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="75aa8-194">![Add a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span></span>  
  
4.  <span data-ttu-id="75aa8-195">Verschieben Sie eine <xref:System.Activities.Statements.TransactionScope>-Aktivität per Drag & Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="75aa8-196">Wählen Sie die <xref:System.Activities.Statements.TransactionScope>-Aktivität aus, klicken Sie auf die Schaltfläche Variablen, und fügen Sie die folgenden Variablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="75aa8-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     <span data-ttu-id="75aa8-197">![Hinzufügen von Variablen zu TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "\"tsvariables\"")</span><span class="sxs-lookup"><span data-stu-id="75aa8-197">![Add variables to the TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span></span>  
  
5.  <span data-ttu-id="75aa8-198">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag & Drop in den Text der <xref:System.Activities.Statements.TransactionScope>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6.  <span data-ttu-id="75aa8-199">Verschieben Sie eine `PrintTransactionInfo`-Aktivität per Drag & Drop innerhalb der <xref:System.Activities.Statements.Sequence>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7.  <span data-ttu-id="75aa8-200">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität nach dem die `PrintTransactionInfo` Aktivität, und legen dessen <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft auf "Client: Beginnen senden".</span><span class="sxs-lookup"><span data-stu-id="75aa8-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="75aa8-201">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="75aa8-201">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="75aa8-202">![Hinzufügen von Aktivitäten](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span><span class="sxs-lookup"><span data-stu-id="75aa8-202">![Adding activities](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span></span>  
  
8.  <span data-ttu-id="75aa8-203">Ziehen Sie eine <xref:System.ServiceModel.Activities.Send>-Aktivität per Drag & Drop an die Stelle nach der <xref:System.Activities.Statements.Assign>-Aktivität, und legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="75aa8-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="75aa8-204">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="75aa8-204">Property</span></span>|<span data-ttu-id="75aa8-205">Wert</span><span class="sxs-lookup"><span data-stu-id="75aa8-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="75aa8-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="75aa8-206">EndpointConfigurationName</span></span>|<span data-ttu-id="75aa8-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="75aa8-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="75aa8-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="75aa8-208">OperationName</span></span>|<span data-ttu-id="75aa8-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="75aa8-209">StartSample</span></span>|  
    |<span data-ttu-id="75aa8-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="75aa8-210">ServiceContractName</span></span>|<span data-ttu-id="75aa8-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="75aa8-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="75aa8-212">Der Workflow müsste jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="75aa8-212">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="75aa8-213">![Festlegen der Send-Aktivitätseigenschaften](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span><span class="sxs-lookup"><span data-stu-id="75aa8-213">![Setting the Send activity properties](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span></span>  
  
9. <span data-ttu-id="75aa8-214">Klicken Sie auf die **definieren...**  verknüpfen, und legen Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="75aa8-214">Click the **Define...** link and make the following settings:</span></span>  
  
     <span data-ttu-id="75aa8-215">![Send-aktivitätsmeldungseinstellungen](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="75aa8-215">![Send activity message settings](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span></span>  
  
10. <span data-ttu-id="75aa8-216">Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Send> Aktivität, und wählen **ReceiveReply erstellen**.</span><span class="sxs-lookup"><span data-stu-id="75aa8-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="75aa8-217">Die <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität wird automatisch nach der <xref:System.ServiceModel.Activities.Send>-Aktivität platziert.</span><span class="sxs-lookup"><span data-stu-id="75aa8-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="75aa8-218">Klicken Sie in der ReceiveReplyForSend-Aktivität auf den Link Definieren..., und legen Sie die folgenden Einstellungen fest:</span><span class="sxs-lookup"><span data-stu-id="75aa8-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     <span data-ttu-id="75aa8-219">![Festlegen der ReceiveForSend-meldungseinstellungen](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="75aa8-219">![Setting the ReceiveForSend message settings](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span></span>  
  
12. <span data-ttu-id="75aa8-220">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität zwischen der <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.ReceiveReply> Aktivitäten und legen seine <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft auf "Client: Senden Sie abgeschlossen".</span><span class="sxs-lookup"><span data-stu-id="75aa8-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="75aa8-221">Drag & drop eine <xref:System.Activities.Statements.WriteLine> Aktivität nach dem die <xref:System.ServiceModel.Activities.ReceiveReply> Aktivität, und legen dessen <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft "Clientseite: Empfangene Antwort = "+ replymessage fest</span><span class="sxs-lookup"><span data-stu-id="75aa8-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="75aa8-222">Verschieben Sie eine `PrintTransactionInfo`-Aktivität per Drag & Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="75aa8-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="75aa8-223">Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag & Drop an das Ende des Workflows, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client workflow ends" fest.</span><span class="sxs-lookup"><span data-stu-id="75aa8-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="75aa8-224">Der abgeschlossene Clientworkflow sollte wie das folgende Diagramm aussehen.</span><span class="sxs-lookup"><span data-stu-id="75aa8-224">The completed client workflow should look like the following diagram.</span></span>  
  
     <span data-ttu-id="75aa8-225">![Der vollständige clientworkflow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span><span class="sxs-lookup"><span data-stu-id="75aa8-225">![The completed client workfliow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span></span>  
  
16. <span data-ttu-id="75aa8-226">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="75aa8-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="75aa8-227">Erstellen der Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="75aa8-227">Create the Service application</span></span>  
  
1.  <span data-ttu-id="75aa8-228">Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Service` hinzu.</span><span class="sxs-lookup"><span data-stu-id="75aa8-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="75aa8-229">Fügen Sie Verweise auf die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="75aa8-229">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="75aa8-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="75aa8-230">System.Activities.dll</span></span>  
  
    2.  <span data-ttu-id="75aa8-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="75aa8-231">System.ServiceModel.dll</span></span>  
  
    3.  <span data-ttu-id="75aa8-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="75aa8-232">System.ServiceModel.Activities.dll</span></span>  
  
2.  <span data-ttu-id="75aa8-233">Öffnen Sie die generierte Datei Program.cs und den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="75aa8-233">Open the generated Program.cs file and the following code:</span></span>  
  
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
  
3.  <span data-ttu-id="75aa8-234">Fügen Sie dem Projekt die folgende app.config-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="75aa8-234">Add the following app.config file to the project.</span></span>  
  
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
  
### <a name="create-the-client-application"></a><span data-ttu-id="75aa8-235">Erstellen der Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="75aa8-235">Create the client application</span></span>  
  
1.  <span data-ttu-id="75aa8-236">Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Client` hinzu.</span><span class="sxs-lookup"><span data-stu-id="75aa8-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="75aa8-237">Fügen Sie einen Verweis auf System.Activities.dll hinzu.</span><span class="sxs-lookup"><span data-stu-id="75aa8-237">Add a reference to System.Activities.dll.</span></span>  
  
2.  <span data-ttu-id="75aa8-238">Öffnen Sie die Datei program.cs, und fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="75aa8-238">Open the program.cs file and add the following code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75aa8-239">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75aa8-239">See also</span></span>

- [<span data-ttu-id="75aa8-240">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="75aa8-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="75aa8-241">Übersicht über Windows Communication Foundation-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="75aa8-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
