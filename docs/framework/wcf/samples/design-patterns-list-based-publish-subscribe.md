---
title: 'Entwurfsmuster: Listenbasiertes Veröffentlichen-Abonnieren'
ms.date: 03/30/2017
ms.assetid: f4257abc-12df-4736-a03b-0731becf0fd4
ms.openlocfilehash: cd7cc6f68362c7a69256f0488e2fa00caffdabc7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978211"
---
# <a name="design-patterns-list-based-publish-subscribe"></a><span data-ttu-id="1357d-102">Entwurfsmuster: Listenbasiertes Veröffentlichen-Abonnieren</span><span class="sxs-lookup"><span data-stu-id="1357d-102">Design Patterns: List-Based Publish-Subscribe</span></span>
<span data-ttu-id="1357d-103">Dieses Beispiel veranschaulicht das Listen basierte Veröffentlichen-Abonnieren-Muster, das als Windows Communication Foundation (WCF)-Programm implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="1357d-103">This sample illustrates the List-based Publish-Subscribe pattern implemented as a Windows Communication Foundation (WCF) program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1357d-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="1357d-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="1357d-105">Das Listen basierte veröffentlichen-abonnieren-Entwurfsmuster wird in der Microsoft Patterns & Practices-Veröffentlichung, in den [Integrations Mustern](https://go.microsoft.com/fwlink/?LinkId=95894)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1357d-105">The List-based Publish-Subscribe design pattern is described in the Microsoft Patterns & Practices publication, [Integration Patterns](https://go.microsoft.com/fwlink/?LinkId=95894).</span></span> <span data-ttu-id="1357d-106">Das Veröffentlichen-Abonnieren-Muster übergibt Informationen an eine Auflistung von Empfängern, die ein Informationsthema abonniert haben.</span><span class="sxs-lookup"><span data-stu-id="1357d-106">The Publish-Subscribe pattern passes information to a collection of recipients who have subscribed to an information topic.</span></span> <span data-ttu-id="1357d-107">Listenbasiertes Veröffentlichen-Abonnieren verwaltet eine Liste von Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="1357d-107">List-based publish-subscribe maintains a list of subscribers.</span></span> <span data-ttu-id="1357d-108">Wenn für die Veröffentlichung bestimmte Informationen vorhanden sind, wird jedem Abonnenten auf der Liste ein Exemplar geschickt.</span><span class="sxs-lookup"><span data-stu-id="1357d-108">When there is information to share, a copy is sent to each subscriber on the list.</span></span> <span data-ttu-id="1357d-109">Dieses Beispiel veranschaulicht ein dynamisches listenbasiertes Veröffentlichen-Abonnieren-Muster, das von Kunden nach Bedarf abonniert und abbestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1357d-109">This sample demonstrates a dynamic list-based publish-subscribe pattern, where clients can subscribe or unsubscribe as often as required.</span></span>  
  
 <span data-ttu-id="1357d-110">Das Beispiel für listenbasiertes Veröffentlichen-Abonnieren besteht aus einem Client, einem Dienst und einem Datenquellenprogramm.</span><span class="sxs-lookup"><span data-stu-id="1357d-110">The List-based Publish-Subscribe sample consists of a client, a service, and a data source program.</span></span> <span data-ttu-id="1357d-111">Es können mehrere Clients und mehrere Datenquellenprogramme ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1357d-111">There can be more than one client and more than one data source program running.</span></span> <span data-ttu-id="1357d-112">Clients abonnieren den Dienst, empfangen Benachrichtigungen und bestellen den Dienst ab.</span><span class="sxs-lookup"><span data-stu-id="1357d-112">Clients subscribe to the service, receive notifications, and unsubscribe.</span></span> <span data-ttu-id="1357d-113">Datenquellprogramme senden Informationen an den Dienst, die für alle aktuellen Abonnenten veröffentlicht werden sollte.</span><span class="sxs-lookup"><span data-stu-id="1357d-113">Data source programs send information to the service to be shared with all current subscribers.</span></span>  
  
 <span data-ttu-id="1357d-114">In diesem Beispiel sind der Client und die Datenquelle Konsolenprogramme (.exe-Dateien), und der Dienst ist eine Bibliothek (.dll), die in Internet Information Services (IIS) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1357d-114">In this sample, the client and data source are console programs (.exe files) and the service is a library (.dll) hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="1357d-115">Client- und Datenquellenaktivität sind auf dem Desktop sichtbar.</span><span class="sxs-lookup"><span data-stu-id="1357d-115">Client and data source activity are visible on the desktop.</span></span>  
  
 <span data-ttu-id="1357d-116">Der Dienst verwendet Duplexkommunikation.</span><span class="sxs-lookup"><span data-stu-id="1357d-116">The service uses duplex communication.</span></span> <span data-ttu-id="1357d-117">Der `ISampleContract`-Dienstvertrag wird mit einem `ISampleClientCallback`-Rückrufvertrag zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="1357d-117">The `ISampleContract` service contract is paired up with an `ISampleClientCallback` callback contract.</span></span> <span data-ttu-id="1357d-118">Der Dienst implementiert Subscribe- und Unsubscribe-Dienstvorgänge, die von Clients verwendet werden, um der Liste der Abonnenten beizutreten oder diese zu verlassen.</span><span class="sxs-lookup"><span data-stu-id="1357d-118">The service implements Subscribe and Unsubscribe service operations, which clients use to join or leave the list of subscribers.</span></span> <span data-ttu-id="1357d-119">Der Dienst implementiert außerdem den `PublishPriceChange`-Dienstvorgang, der vom Datenquellenprogramm aufgerufen wird, um dem Dienst neue Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1357d-119">The service also implements the `PublishPriceChange` service operation, which the data source program calls to provide the service with new information.</span></span> <span data-ttu-id="1357d-120">Das Clientprogramm implementiert den `PriceChange`-Dienstvorgang, der vom Dienst aufgerufen wird, um alle Abonnenten über Preisänderungen zu informieren.</span><span class="sxs-lookup"><span data-stu-id="1357d-120">The client program implements the `PriceChange` service operation, which the service calls to notify all subscribers of a price change.</span></span>  
  
```csharp  
// Create a service contract and define the service operations.  
// NOTE: The service operations must be declared explicitly.  
[ServiceContract(SessionMode=SessionMode.Required,  
      CallbackContract=typeof(ISampleClientContract))]  
public interface ISampleContract  
{  
    [OperationContract(IsOneWay = false, IsInitiating=true)]  
    void Subscribe();  
    [OperationContract(IsOneWay = false, IsTerminating=true)]  
    void Unsubscribe();  
    [OperationContract(IsOneWay = true)]  
    void PublishPriceChange(string item, double price,   
                                     double change);  
}  
  
public interface ISampleClientContract  
{  
    [OperationContract(IsOneWay = true)]  
    void PriceChange(string item, double price, double change);  
}  
```  
  
 <span data-ttu-id="1357d-121">Der Dienst verwendet ein .NET Framework-Ereignis als Mechanismus, um alle Abonnenten über neue Informationen zu informieren.</span><span class="sxs-lookup"><span data-stu-id="1357d-121">The service uses a .NET Framework event as the mechanism to inform all subscribers about new information.</span></span> <span data-ttu-id="1357d-122">Wenn ein Client dem Dienst beitritt, indem er Subscribe aufruft, wird ein Ereignishandler bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1357d-122">When a client joins the service by calling Subscribe, it provides an event handler.</span></span> <span data-ttu-id="1357d-123">Wenn ein Client den Dienst verlässt, wird sein Ereignishandler von dem Ereignis entfernt.</span><span class="sxs-lookup"><span data-stu-id="1357d-123">When a client leaves, it unsubscribes its event handler from the event.</span></span> <span data-ttu-id="1357d-124">Wenn eine Datenquelle den Dienst aufruft, um eine Preisänderung mitzuteilen, löst der Dienst das Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="1357d-124">When a data source calls the service to report a price change, the service raises the event.</span></span> <span data-ttu-id="1357d-125">Daraufhin wird jede Instanz des Diensts aufgerufen, eine für jeden Client mit einem Abonnement, und die Ereignishandler werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1357d-125">This calls each instance of the service, one for each client that has subscribed, and causes their event handlers to execute.</span></span> <span data-ttu-id="1357d-126">Jeder Ereignishandler übermittelt die Informationen über seine Rückruffunktion an seinen Client.</span><span class="sxs-lookup"><span data-stu-id="1357d-126">Each event handler passes the information to its client through its callback function.</span></span>  
  
```csharp
public class PriceChangeEventArgs : EventArgs  
    {  
        public string Item;  
        public double Price;  
        public double Change;  
    }  
  
    // The Service implementation implements your service contract.  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    public class SampleService : ISampleContract  
    {  
        public static event PriceChangeEventHandler PriceChangeEvent;  
        public delegate void PriceChangeEventHandler(object sender, PriceChangeEventArgs e);  
  
        ISampleClientContract callback = null;  
  
        PriceChangeEventHandler priceChangeHandler = null;  
  
        //Clients call this service operation to subscribe.  
        //A price change event handler is registered for this client instance.  
  
        public void Subscribe()  
        {  
            callback = OperationContext.Current.GetCallbackChannel<ISampleClientContract>();  
            priceChangeHandler = new PriceChangeEventHandler(PriceChangeHandler);  
            PriceChangeEvent += priceChangeHandler;  
        }  
  
        //Clients call this service operation to unsubscribe.  
        //The previous price change event handler is unregistered.  
  
        public void Unsubscribe()  
        {  
            PriceChangeEvent -= priceChangeHandler;  
        }  
  
        //Information source clients call this service operation to report a price change.  
        //A price change event is raised. The price change event handlers for each subscriber will execute.  
  
        public void PublishPriceChange(string item, double price, double change)  
        {  
            PriceChangeEventArgs e = new PriceChangeEventArgs();  
            e.Item = item;  
            e.Price = price;  
            e.Change = change;  
            PriceChangeEvent(this, e);  
        }  
  
        //This event handler runs when a PriceChange event is raised.  
        //The client's PriceChange service operation is invoked to provide notification about the price change.  
  
        public void PriceChangeHandler(object sender, PriceChangeEventArgs e)  
        {  
            callback.PriceChange(e.Item, e.Price, e.Change);  
        }  
  
    }  
```  
  
 <span data-ttu-id="1357d-127">Wenn Sie das Beispiel ausführen, starten Sie mehrere Clients.</span><span class="sxs-lookup"><span data-stu-id="1357d-127">When you run the sample, launch several clients.</span></span> <span data-ttu-id="1357d-128">Die Clients abonnieren den Dienst.</span><span class="sxs-lookup"><span data-stu-id="1357d-128">The clients subscribe to the service.</span></span> <span data-ttu-id="1357d-129">Führen Sie anschließend das Datenquellenprogramm aus, das Informationen an den Dienst sendet.</span><span class="sxs-lookup"><span data-stu-id="1357d-129">Then run the data source program, which sends information to the service.</span></span> <span data-ttu-id="1357d-130">Der Dienst übergibt die Informationen an alle Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="1357d-130">The service passes on the information to all subscribers.</span></span> <span data-ttu-id="1357d-131">Sie können Aktivität auf jeder Clientkonsole sehen, sodass bestätigt wird, dass die Informationen empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="1357d-131">You can see activity on each client console confirming that the information has been received.</span></span> <span data-ttu-id="1357d-132">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1357d-132">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="1357d-133">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="1357d-133">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="1357d-134">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="1357d-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="1357d-135">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="1357d-135">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="1357d-136">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="1357d-136">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="1357d-137">Überprüfen Sie, ob Sie über einen Browser auf den Dienst zugreifen können, indem Sie die folgende Adresse eingeben: `http://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="1357d-137">Test that you can access the service using a browser by entering the following address: `http://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="1357d-138">Als Antwort sollte eine Bestätigungsseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1357d-138">A confirmation page should be displayed in response.</span></span>  
  
2. <span data-ttu-id="1357d-139">Führen Sie "Client. exe" aus dem Ordner "\client\bin\\" unter dem sprachspezifischen Ordner aus.</span><span class="sxs-lookup"><span data-stu-id="1357d-139">Run Client.exe from \client\bin\\, from under the language-specific folder.</span></span> <span data-ttu-id="1357d-140">Im Clientkonsolenfenster wird die Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1357d-140">Client activity is displayed on the client console window.</span></span> <span data-ttu-id="1357d-141">Starten Sie mehrere Clients.</span><span class="sxs-lookup"><span data-stu-id="1357d-141">Launch several clients.</span></span>  
  
3. <span data-ttu-id="1357d-142">Führen Sie "DataSource. exe" aus "\datasource\bin\\" unter dem sprachspezifischen Ordner aus.</span><span class="sxs-lookup"><span data-stu-id="1357d-142">Run Datasource.exe from \datasource\bin\\, from under the language-specific folder.</span></span> <span data-ttu-id="1357d-143">Die Datenquellenaktivität wird im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1357d-143">Data source activity is displayed on the console window.</span></span> <span data-ttu-id="1357d-144">Sobald die Datenquelle Informationen an den Dienst sendet, sollten diese an jeden Client übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1357d-144">Once the data source sends information to the service, it should be passed on to each client.</span></span>  
  
4. <span data-ttu-id="1357d-145">Wenn der Client, die Datenquelle und die Dienstprogramme nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="1357d-145">If the client, data source, and service programs are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="1357d-146">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="1357d-146">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="1357d-147">Einrichten des Dienstrechners:</span><span class="sxs-lookup"><span data-stu-id="1357d-147">Set up the service machine:</span></span>  
  
    1. <span data-ttu-id="1357d-148">Erstellen Sie auf dem Dienstcomputer ein virtuelles Verzeichnis namens "ServiceModelSamples".</span><span class="sxs-lookup"><span data-stu-id="1357d-148">On the service machine, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="1357d-149">Die Batchdatei Setupvroot. bat aus dem [einmaligen Setup Verfahren für die Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) kann zum Erstellen des Datenträger Verzeichnisses und des virtuellen Verzeichnisses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1357d-149">The batch file Setupvroot.bat from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) can be used to create the disk directory and virtual directory.</span></span>  
  
    2. <span data-ttu-id="1357d-150">Kopieren Sie die Dienstprogrammdateien aus %SystemDrive%\Inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis "ServiceModelSamples" auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="1357d-150">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service machine.</span></span> <span data-ttu-id="1357d-151">Stellen Sie sicher, dass Sie die Dateien in das Verzeichnis \bin einfügen.</span><span class="sxs-lookup"><span data-stu-id="1357d-151">Be sure to include the files in the \bin directory.</span></span>  
  
    3. <span data-ttu-id="1357d-152">Testen Sie, ob Sie mit einem Browser vom Clientcomputer auf den Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1357d-152">Test that you can access the service from the client machine using a browser.</span></span>  
  
2. <span data-ttu-id="1357d-153">Einrichten der Clientcomputer:</span><span class="sxs-lookup"><span data-stu-id="1357d-153">Set up the client machines:</span></span>  
  
    1. <span data-ttu-id="1357d-154">Kopieren Sie die Clientprogrammdateien aus dem Ordner "\client\bin\" (unterhalb des sprachspezifischen Ordners) auf die Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="1357d-154">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machines.</span></span>  
  
    2. <span data-ttu-id="1357d-155">Ändern Sie in jeder Clientkonfigurationsdatei den Wert für die Adresse der Endpunktdefinition so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="1357d-155">In each client configuration file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="1357d-156">Ersetzen Sie alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="1357d-156">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
3. <span data-ttu-id="1357d-157">Einrichten des Datenquellencomputers:</span><span class="sxs-lookup"><span data-stu-id="1357d-157">Set up the data source machine:</span></span>  
  
    1. <span data-ttu-id="1357d-158">Kopieren Sie die Datenquellen-Programmdateien aus dem Ordner "\datasource\bin\" (unterhalb des sprachspezifischen Ordners) auf den Datenquellencomputer.</span><span class="sxs-lookup"><span data-stu-id="1357d-158">Copy the data source program files from the \datasource\bin\ folder, under the language-specific folder, to the data source machine.</span></span>  
  
    2. <span data-ttu-id="1357d-159">Ändern Sie in der Datenquellen-Konfigurationsdatei den Wert für die Adresse der Endpunktdefinition so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="1357d-159">In the data source configuration file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="1357d-160">Ersetzen Sie alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="1357d-160">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
4. <span data-ttu-id="1357d-161">Starten Sie auf den Clientcomputern in einer Eingabeaufforderung die Datei "Client.exe".</span><span class="sxs-lookup"><span data-stu-id="1357d-161">On the client machines, launch Client.exe from a command prompt.</span></span>  
  
5. <span data-ttu-id="1357d-162">Starten Sie auf dem Datenquellencomputer in einer Eingabeaufforderung die Datei "Datasource.exe".</span><span class="sxs-lookup"><span data-stu-id="1357d-162">On the data source machine, launch Datasource.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1357d-163">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="1357d-163">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1357d-164">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="1357d-164">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="1357d-165">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1357d-165">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1357d-166">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1357d-166">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DesignPatterns/ListBasedPublishSubscribe`  
