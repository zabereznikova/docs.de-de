---
title: Gepuffertes Empfangen
ms.date: 03/30/2017
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
ms.openlocfilehash: b95577c71493275f30703b4366fab32a51097bd2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526803"
---
# <a name="buffered-receive"></a><span data-ttu-id="b1ff9-102">Gepuffertes Empfangen</span><span class="sxs-lookup"><span data-stu-id="b1ff9-102">Buffered Receive</span></span>
<span data-ttu-id="b1ff9-103">Dieses Beispiel veranschaulicht das Einrichten und konfigurieren die gepufferte Empfangsfunktion in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="b1ff9-103">This sample demonstrates how to set up and configure the buffered receive feature in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="b1ff9-104">Die gepufferte Empfangsfunktion ermöglicht es dem Workflowautor, einen Workflow zu erstellen, ohne sich Gedanken über die Reihenfolge zu machen, in der Nachrichten empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-104">Buffered receive allows the workflow author to create a workflow without having to worry about the order in which messages are received.</span></span> <span data-ttu-id="b1ff9-105">Die gepufferte Empfangsfunktion puffert Nachrichten lokal und übermittelt sie, wenn der Workflow zum Empfang bereit ist.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-105">The buffered receive feature buffers messages locally and delivers them when the workflow is ready to receive them.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b1ff9-106">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="b1ff9-106">Demonstrates</span></span>  
 <span data-ttu-id="b1ff9-107">Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge unter Verwendung der gepufferten Empfangsfunktion mit Messagingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-107">Out-of-order message processing using buffered receive with messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b1ff9-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b1ff9-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b1ff9-110">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b1ff9-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a><span data-ttu-id="b1ff9-112">Diskussion</span><span class="sxs-lookup"><span data-stu-id="b1ff9-112">Discussion</span></span>  
 <span data-ttu-id="b1ff9-113">In diesem Beispiel wird ein Windows Communication Foundation (WCF)-Dienst implementiert, mit [!INCLUDE[wf1](../../../../includes/wf1-md.md)] und verfügt über eine Sequenz von <xref:System.ServiceModel.Activities.Receive> Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-113">In this sample, a Windows Communication Foundation (WCF) service is implemented using [!INCLUDE[wf1](../../../../includes/wf1-md.md)] and has a sequence of <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="b1ff9-114">Dieser Workflow modelliert einen einfachen Kreditgenehmigungsprozess, bei dem der Workflow drei Benachrichtigungen erwartet, bevor ein Kredit genehmigt wird.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-114">This workflow models a simple loan approval process where the workflow expects three notifications for a loan to be approved.</span></span> <span data-ttu-id="b1ff9-115">Eine Windows Communication Foundation (WCF)-Clientanwendung sendet drei korrelierende Benachrichtigungen in umgekehrter Reihenfolge der wie erwartet, dass der Dienst an.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-115">A Windows Communication Foundation (WCF) client application sends three correlated notifications in the reverse order of what the service expects.</span></span> <span data-ttu-id="b1ff9-116">Da die gepufferte Empfangsfunktion für den Dienst aktiviert ist, wird jede Nachricht, die sich außerhalb der normalen Reihenfolge befindet, beim Dienst gepuffert und verarbeitet, wenn der Workflow für den Empfang bereit ist.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-116">Because the buffered receive feature is turned on at the service, each out-of-order message is buffered at the service and processed as the workflow becomes ready to receive it.</span></span>  
  
 <span data-ttu-id="b1ff9-117">Die gepufferte Empfangsfunktion erfordert <xref:System.ServiceModel.Activities.ReceiveContent>-Unterstützung durch die Bindung. Daher verwendet der Dienst <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-117">The buffered receive feature requires <xref:System.ServiceModel.Activities.ReceiveContent> support from the binding, therefore the service uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="b1ff9-118">Für die Bindung ist keine spezielle Konfiguration erforderlich, sodass die Standardwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-118">No special configuration is required for the binding, so the defaults are used.</span></span>  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 <span data-ttu-id="b1ff9-119">Der Dienst macht mithilfe von <xref:System.ServiceModel.Description.ServiceMetadataBehavior> außerdem Metadaten für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-119">The service also exposes metadata for the service using <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span></span>  
  
 <span data-ttu-id="b1ff9-120">Auf ähnliche Weise wird der Clientendpunkt mit <xref:System.ServiceModel.NetMsmqBinding> konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-120">Similarly, the client endpoint is configured using <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="b1ff9-121">Der Clientcode und-Konfiguration generiert, indem die **Hinzufügen eines Dienstverweises** Feature von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-121">The client code and configuration is generated by using the **Add Service Reference** feature of Visual Studio.</span></span> <span data-ttu-id="b1ff9-122">Das folgende Beispiel stellt den generierten Clientendpunkt in der Datei App.config dar.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-122">The following example is the generated client endpoint in the App.config file.</span></span>  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 <span data-ttu-id="b1ff9-123">Dieses Beispiel erfordert, dass die folgenden Windows-Komponenten aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="b1ff9-123">This sample requires that the following Windows components are enabled:</span></span>  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]<span data-ttu-id="b1ff9-124">-Verwaltungskompatibilität, -Metabasis und -Konfigurationskompatibilität</span><span class="sxs-lookup"><span data-stu-id="b1ff9-124"> Management Compatibility, Metabase, and Configuration Compatibility</span></span>  
  
3.  <span data-ttu-id="b1ff9-125">World Wide Web-Dienst, Anwendungsentwicklungsfunktionen und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b1ff9-125">World Wide Web Services, Application Development Features, and ASP.NET</span></span>  
  
4.  <span data-ttu-id="b1ff9-126">Microsoft Message Queues (MSMQ) Server</span><span class="sxs-lookup"><span data-stu-id="b1ff9-126">Microsoft Message Queues (MSMQ) Server</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="b1ff9-127">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="b1ff9-127">To set up, and build the sample</span></span>  
  
1.  <span data-ttu-id="b1ff9-128">Registrieren Sie an einer [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung ASP.NET, indem Sie `aspnet_regiis –I` eingeben, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-128">At a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by typing `aspnet_regiis –I` and press ENTER.</span></span>  
  
2.  <span data-ttu-id="b1ff9-129">Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-129">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an Administrator.</span></span>  
  
3.  <span data-ttu-id="b1ff9-130">Öffnen Sie LoanService.sln.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-130">Open LoanService.sln.</span></span>  
  
4.  <span data-ttu-id="b1ff9-131">Wenn Sie gefragt, wenn Sie die virtuellen Verzeichnisse für das LoanService-Projekt erstellen möchten, wählen Sie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-131">When asked if you would like to create the virtual directories for the LoanService project, select **Yes**.</span></span>  
  
#### <a name="to-set-up-the-service-queues"></a><span data-ttu-id="b1ff9-132">So richten Sie die Dienstwarteschlangen ein</span><span class="sxs-lookup"><span data-stu-id="b1ff9-132">To set up the service queues</span></span>  
  
1.  <span data-ttu-id="b1ff9-133">Drücken Sie F5, um die LoanClient-Anwendung, die die Warteschlangen erstellt und den in Service1.xaml definierten Dienst aktiviert, auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-133">Press F5 to run the LoanClient application that creates the queues and activates the service defined in Service1.xamlx.</span></span>  
  
2.  <span data-ttu-id="b1ff9-134">Öffnen der **Computerverwaltung** Verwaltungskonsole, indem Sie Compmgmt.msc an einer Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-134">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
3.  <span data-ttu-id="b1ff9-135">In der **Computerverwaltung** nacheinander **Service**, **Anwendungen**, **Message Queuing-**, **Private Warteschlangen** .</span><span class="sxs-lookup"><span data-stu-id="b1ff9-135">In the **Computer Management** console, expand **Service**, **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
4.  <span data-ttu-id="b1ff9-136">Mit der rechten Maustaste in die Warteschlange loanservice/Service1.xamlx, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-136">Right-click the loanservice/service1.xamlx queue and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="b1ff9-137">Wählen Sie die **Sicherheit** Registerkarte, und fügen Sie **Nachricht empfangen**, **Nachricht einsehen** und **Send Message** Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-137">Select the **Security** tab, and add **Everyone Receives Message**, **Peek Message** and **Send Message** permissions.</span></span>  
  
6.  <span data-ttu-id="b1ff9-138">Öffnen Sie den [!INCLUDE[iis60](../../../../includes/iis60-md.md)]-Manager.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-138">Open the [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Manager.</span></span>  
  
7.  <span data-ttu-id="b1ff9-139">Navigieren Sie zu **Server**, **Websites**, **Standardwebsite**, **Private**, **LoanService** , und wählen Sie  **Erweiterte Optionen**</span><span class="sxs-lookup"><span data-stu-id="b1ff9-139">Browse to **Server**, **Sites**, **Default Web site**, **Private**, **LoanService** and select **Advanced Options**</span></span>  
  
8.  <span data-ttu-id="b1ff9-140">Ändern der **aktivierte Protokolle** sein **http**, **net.msmq**.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-140">Change the **Enabled Protocols** to be **http**, **net.msmq**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="b1ff9-141">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="b1ff9-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="b1ff9-142">Navigieren Sie zu http://localhost/private/loanservice/service1.xamlx um sicherzustellen, dass der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-142">Browse to http://localhost/private/loanservice/service1.xamlx to ensure that the service is running.</span></span>  
  
2.  <span data-ttu-id="b1ff9-143">Drücken Sie F5, um die LoanClient-Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-143">Press F5 to run the LoanClient application.</span></span> <span data-ttu-id="b1ff9-144">Sobald der Workflow abgeschlossen ist, wird eine out.txt-Datei unter C:\Inbox gespeichert, die das Ergebnis des Nachrichtenaustauschs enthält.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-144">Once the workflow is complete, an out.txt file should be saved to C:\Inbox that contains the result of the message exchange.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="b1ff9-145">So führen Sie eine Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="b1ff9-145">To clean up</span></span>  
  
1.  <span data-ttu-id="b1ff9-146">Öffnen der **Computerverwaltung** Verwaltungskonsole, indem Sie Compmgmt.msc an einer Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-146">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
2.  <span data-ttu-id="b1ff9-147">Erweitern Sie **Service** und **Anwendungen**, **Message Queuing-**, **Private Warteschlangen**.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-147">Expand **Service** and **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="b1ff9-148">Löschen Sie die Warteschlange loanservice/service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-148">Delete the loanservice/service1.xamlx queue.</span></span>  
  
4.  <span data-ttu-id="b1ff9-149">Entfernen Sie das Verzeichnis C:\Inbox.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-149">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b1ff9-150">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b1ff9-151">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b1ff9-152">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b1ff9-153">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b1ff9-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
