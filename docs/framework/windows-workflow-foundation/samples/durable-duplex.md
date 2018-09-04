---
title: Permanenter Duplex
ms.date: 03/30/2017
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
ms.openlocfilehash: 107c617fa4a8ee0279dcaa07e495587c617b866e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513352"
---
# <a name="durable-duplex"></a><span data-ttu-id="fb826-102">Permanenter Duplex</span><span class="sxs-lookup"><span data-stu-id="fb826-102">Durable Duplex</span></span>
<span data-ttu-id="fb826-103">Dieses Beispiel veranschaulicht das Einrichten und Konfigurieren von permanenter duplexnachrichtenaustausch mithilfe der messagingaktivitäten in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="fb826-103">This sample demonstrates how to set up and configure durable duplex message exchange using the messaging activities in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="fb826-104">Ein permanenter Duplexnachrichtenaustausch ist ein bidirektionaler Nachrichtenaustausch, der im Verlauf eines langen Zeitraums stattfindet.</span><span class="sxs-lookup"><span data-stu-id="fb826-104">A durable duplex message exchange is a two-way message exchange that takes place over a long period of time.</span></span> <span data-ttu-id="fb826-105">Die Lebensdauer des Nachrichtenaustauschs ist möglicherweise länger als die Lebensdauer des Kommunikationskanals und die Lebensdauer der Dienstinstanzen im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="fb826-105">The lifetime of the message exchange may be longer than the lifetime of the communication channel and the in-memory lifetime of the service instances.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="fb826-106">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="fb826-106">Sample Details</span></span>  
 <span data-ttu-id="fb826-107">In diesem Beispiel werden zwei Windows Communication Foundation (WCF)-Dienste, die mithilfe von Windows Workflow Foundation implementiert einen permanenten duplexnachrichtenaustausch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="fb826-107">In this sample, two Windows Communication Foundation (WCF) services implemented using Windows Workflow Foundation are configured to have a durable duplex message exchange.</span></span> <span data-ttu-id="fb826-108">Der permanente duplexnachrichtenaustausch besteht aus zwei unidirektionalen Nachrichten über MSMQ gesendet und korreliert mit [.NET Context Exchange](https://go.microsoft.com/fwlink/?LinkID=166059).</span><span class="sxs-lookup"><span data-stu-id="fb826-108">The durable duplex message exchange is composed from two one-way messages sent over MSMQ and correlated using [.NET Context Exchange](https://go.microsoft.com/fwlink/?LinkID=166059).</span></span> <span data-ttu-id="fb826-109">Die Nachrichten werden mit den Messagingaktivitäten <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.Receive> gesendet.</span><span class="sxs-lookup"><span data-stu-id="fb826-109">The messages are sent using the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.Receive> messaging activities.</span></span> <span data-ttu-id="fb826-110">Der .NET-Kontextaustausch wird verwendet, um die Rückrufadresse in den gesendeten Nachrichten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb826-110">.NET Context Exchange is use to specify the callback address on the sent messages.</span></span> <span data-ttu-id="fb826-111">Beide Dienste werden mit WAS (Windows Process Activation Services) gehostet und sind konfiguriert, um Persistenz der Dienstinstanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fb826-111">Both services are hosted using Windows Process Activation Services (WAS) and are configured to enable persistence of the services instances.</span></span>  
  
 <span data-ttu-id="fb826-112">Der erste Dienst (Service1.xamlx) sendet eine Anforderung an den zweiten Dienst (Service2.xamlx), einige Arbeiten zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="fb826-112">The first service (Service1.xamlx) sends a request to the send service (Service2.xamlx) to do some work.</span></span> <span data-ttu-id="fb826-113">Sobald die Arbeit abgeschlossen ist, sendet Service2.xamlx eine Benachrichtigung an Service1.xamlx zurück, um anzugeben, dass die Arbeit abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="fb826-113">Once the work is completed, Service2.xamlx sends a notification back to Service1.xamlx to indicate that the work has been completed.</span></span> <span data-ttu-id="fb826-114">Eine Konsolenanwendung für Workflows richtet die Warteschlangen ein, die die Dienste überwachen, und sendet die ursprüngliche Startnachricht, um Service1.xamlx zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb826-114">A workflow console application sets up the queues that the services are listening on and sends the initial Start message to activate Service1.xamlx.</span></span> <span data-ttu-id="fb826-115">Sobald Service1.xamlx die Benachrichtigung von Service2.xamlx empfangen hat, dass die angeforderte Arbeit abgeschlossen ist, speichert Service1.xamlx das Ergebnis in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="fb826-115">Once Service1.xamlx receives the notification from Service2.xamlx that the requested work has been completed, Service1.xamlx saves the result to an XML file.</span></span> <span data-ttu-id="fb826-116">Während des Wartens auf die Rückrufmeldung behält Service1.xamlx den Instanzzustand mit dem standardmäßigen <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> bei.</span><span class="sxs-lookup"><span data-stu-id="fb826-116">While waiting for the callback message, Service1.xamlx persists its instance state using the default <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>.</span></span> <span data-ttu-id="fb826-117">Service2.xamlx behält den Instanzzustand als Teil des Abschlusses der von Service1.xamlx angeforderten Arbeit bei.</span><span class="sxs-lookup"><span data-stu-id="fb826-117">Service2.xamlx persists its instance state as part of completing the work requested by Service1.xamlx.</span></span>  
  
 <span data-ttu-id="fb826-118">Um die Dienste zu konfigurieren, sodass der .NET-Kontextaustausch über MSMQ verwendet wird, werden beide Dienste zur Verwendung einer benutzerdefinierten Bindung konfiguriert, die aus <xref:System.ServiceModel.Channels.ContextBindingElement> und <xref:System.ServiceModel.Channels.MsmqTransportBindingElement> besteht.</span><span class="sxs-lookup"><span data-stu-id="fb826-118">To configure the services to use .NET Context Exchange over MSMQ, both services are configured to use a custom binding that consists of the <xref:System.ServiceModel.Channels.ContextBindingElement> and the <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.</span></span> <span data-ttu-id="fb826-119">Eine Rückrufadresse wird mit <xref:System.ServiceModel.Channels.ContextBindingElement> angegeben und ist in einem Rückrufkontextheader von allen Nachrichten enthalten, die mit einer benutzerdefinierten Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb826-119">A callback address is specified with the <xref:System.ServiceModel.Channels.ContextBindingElement> and is included in a callback context header with all messages sent using a custom binding.</span></span> <span data-ttu-id="fb826-120">Im folgenden Codebeispiel wird die benutzerdefinierte Bindung definiert.</span><span class="sxs-lookup"><span data-stu-id="fb826-120">The following code example defines the custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="fb826-121">Die von diesem Beispiel verwendete Bindung ist nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="fb826-121">The binding used by this sample is not secure.</span></span> <span data-ttu-id="fb826-122">Wenn Sie die Anwendung bereitstellen, sollten Sie die Bindung auf Grundlage der Sicherheitsanforderungen der Anwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fb826-122">When deploying your application you should configure your binding based on the security requirements of your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb826-123">Die in diesem Beispiel verwendeten Warteschlangen sind nicht transaktionsgebunden.</span><span class="sxs-lookup"><span data-stu-id="fb826-123">The queues used in this sample are not transactional.</span></span> <span data-ttu-id="fb826-124">Ein Beispiel, das zeigt, wie WCF-Nachrichtenaustausch mit Transaktionswarteschlangen eingerichtet wird, finden Sie unter den [MSMQ-Aktivierung](../../../../docs/framework/wcf/samples/msmq-activation.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fb826-124">For a sample that shows how to set up WCF message exchanges using transaction queues, see the [MSMQ Activation](../../../../docs/framework/wcf/samples/msmq-activation.md) sample.</span></span>  
  
 <span data-ttu-id="fb826-125">Die von Service1.xamlx an Service2.xamlx gesendete Nachricht wird mit einem Clientendpunkt gesendet, der mit der Adresse von Service2.xamlx und der benutzerdefinierten Bindung, die zuvor definiert wurden, konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="fb826-125">The message sent by Service1.xamlx to Service2.xamlx is sent using a client endpoint configured with the address of Service2.xamlx and the custom binding defined previously.</span></span> <span data-ttu-id="fb826-126">Der Rückruf von Service2.xamlx an Service1.xamlx wird mit einem Clientendpunkt ohne explizit konfigurierte Adresse gesendet, da die Adresse dem Rückrufkontext entnommen wird, der von Service1.xamlx gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fb826-126">The callback from Service2.xamlx to Service1.xamlx is sent using a client endpoint with no explicitly configured address because the address is taken from the callback context sent by Service1.xamlx.</span></span> <span data-ttu-id="fb826-127">Im folgenden Codebeispiel werden die Clientendpunkte definiert.</span><span class="sxs-lookup"><span data-stu-id="fb826-127">The following code example defines the client endpoints.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="fb826-128">Das folgende Codebeispiel macht Endpunkte verfügbar, die diese benutzerdefinierte Bindung verwenden, indem die Standardprotokollzuordnung für net.msmq-Basisadressen auf die Verwendung dieser benutzerdefinierten Bindung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="fb826-128">The following code example exposes endpoints using this custom binding by changing the default protocol mapping for net.msmq base addresses to use this custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="fb826-129">Im folgenden Codebeispiel wird Persistenz für beide Dienste ermöglicht, indem das <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>-Verhalten den Diensten hinzufügt und die Verbindungszeichenfolge für die Persistenzdatenbank angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fb826-129">The following code example enables persistence for both services by adding the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior to both services and specifying the connection string for the persistence database.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
```  
  
## <a name="system-requirements"></a><span data-ttu-id="fb826-130">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="fb826-130">System Requirements</span></span>  
 <span data-ttu-id="fb826-131">Folgende Komponenten sind für dieses Beispiel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb826-131">This sample requires the following components.</span></span>  
  
1.  <span data-ttu-id="fb826-132">Internetinformationsdienste.</span><span class="sxs-lookup"><span data-stu-id="fb826-132">Internet Information Services.</span></span>  
  
2.  <span data-ttu-id="fb826-133">Internetinformationsdienste -> IIS 6.0-Verwaltungskompatibilität -> IIS-Metabasis und IIS 6.0-Konfigurationskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="fb826-133">Internet Information Services -> IIS 6.0 Management Compatibility -> IIS Metabase and IIS 6.0 configuration compatibility.</span></span>  
  
3.  <span data-ttu-id="fb826-134">WWW-Dienste -> Anwendungsentwicklungsfunktionen -> ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fb826-134">World Wide Web Services -> Application Development Features -> ASP.NET.</span></span>  
  
4.  <span data-ttu-id="fb826-135">Microsoft-Server für Meldungswarteschlangen (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="fb826-135">Microsoft Message Queues (MSMQ) Server.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="fb826-136">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb826-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="fb826-137">Richten Sie die Persistenzdatenbank und das Ergebnisverzeichnis ein.</span><span class="sxs-lookup"><span data-stu-id="fb826-137">Set up the persistence database and the results directory.</span></span>  
  
    1.  <span data-ttu-id="fb826-138">Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="fb826-138">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="fb826-139">Navigieren Sie zum Ordner für dieses Beispiel, und führen "Setup.cmd" aus.</span><span class="sxs-lookup"><span data-stu-id="fb826-139">Navigate to the folder for this sample and run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="fb826-140">Richten Sie die virtuelle Anwendung ein.</span><span class="sxs-lookup"><span data-stu-id="fb826-140">Set up the virtual application.</span></span>  
  
    1.  <span data-ttu-id="fb826-141">Registrieren Sie an einer [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung ASP.NET, indem Sie den folgenden Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="fb826-141">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by running the following command.</span></span>  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  <span data-ttu-id="fb826-142">Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit Administratorberechtigungen, indem Sie mit der rechten Maustaste [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fb826-142">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator permissions by right-clicking [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and selecting **Run as administrator**.</span></span>  
  
    3.  <span data-ttu-id="fb826-143">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Datei "DurableDuplex.sln".</span><span class="sxs-lookup"><span data-stu-id="fb826-143">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DurableDuplex.sln file.</span></span>  
  
3.  <span data-ttu-id="fb826-144">Richten Sie die Dienstwarteschlangen ein.</span><span class="sxs-lookup"><span data-stu-id="fb826-144">Set up the service queues.</span></span>  
  
    1.  <span data-ttu-id="fb826-145">Um den DurableDuplex-Client auszuführen, drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="fb826-145">To run the DurableDuplex client, press F5.</span></span>  
  
    2.  <span data-ttu-id="fb826-146">Öffnen der **Computerverwaltung** Verwaltungskonsole, indem Sie Ausführung `Compmgmt.msc` über eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="fb826-146">Open the **Computer Management** console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    3.  <span data-ttu-id="fb826-147">Erweitern Sie **Dienste und Anwendungen**, **Message Queuing-**.</span><span class="sxs-lookup"><span data-stu-id="fb826-147">Expand **Service and Applications**, **Message Queuing**.</span></span> <span data-ttu-id="fb826-148">**Private Warteschlangen**.</span><span class="sxs-lookup"><span data-stu-id="fb826-148">**Private Queues**.</span></span>  
  
    4.  <span data-ttu-id="fb826-149">Mit der rechten Maustaste in der Warteschlangen durableduplex/service1.xamlx und durableduplex/Service2.xamlx, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="fb826-149">Right-click the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues and select **Properties**.</span></span>  
  
    5.  <span data-ttu-id="fb826-150">Wählen Sie die **Sicherheit** Registerkarte und ermöglichen **jeder Nachricht empfangen**, **Nachricht einsehen** und **Send Message** Berechtigungen für beide Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="fb826-150">Select the **Security** tab and allow **Everyone Receive Message**, **Peek Message** and **Send Message** permissions for both queues.</span></span>  
  
    6.  <span data-ttu-id="fb826-151">Öffnen Sie den IIS-Manager (Internet Information Services, Internetinformationsdienste).</span><span class="sxs-lookup"><span data-stu-id="fb826-151">Open Internet Information Services (IIS) Manager.</span></span>  
  
    7.  <span data-ttu-id="fb826-152">Navigieren Sie zu **Server**, **Websites**, **Standardwebsite**, **private**, **permanenter Duplex** , und wählen Sie **Erweiterte Optionen**.</span><span class="sxs-lookup"><span data-stu-id="fb826-152">Browse to **Server**, **Sites**, **Default Web site**, **private**, **Durable Duplex** and select **Advanced Options**.</span></span>  
  
    8.  <span data-ttu-id="fb826-153">Ändern der **aktivierte Protokolle** zu **HTTP, NET.MSMQ**.</span><span class="sxs-lookup"><span data-stu-id="fb826-153">Change the **Enabled Protocols** to **http,net.msmq**.</span></span>  
  
4.  <span data-ttu-id="fb826-154">Führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="fb826-154">Run the sample.</span></span>  
  
    1.  <span data-ttu-id="fb826-155">Navigieren Sie zu http://localhost/private/durableduplex/service1.xamlx und http://localhost/private/durableduplex/service2.xamlx um sicherzustellen, dass beide Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fb826-155">Browse to http://localhost/private/durableduplex/service1.xamlx and http://localhost/private/durableduplex/service2.xamlx to ensure that both services are running.</span></span>  
  
    2.  <span data-ttu-id="fb826-156">Drücken Sie F5, um DurableDuplexClient auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fb826-156">Press F5 to run DurableDuplexClient.</span></span>  
  
         <span data-ttu-id="fb826-157">Wenn der permanente Duplexnachrichtenaustausch abgeschlossen ist, wird eine result.xml-Datei im Ordner C:\Inbox gespeichert und enthält das Ergebnis des Nachrichtenaustauschs.</span><span class="sxs-lookup"><span data-stu-id="fb826-157">When the durable duplex message exchange completes a result.xml file is saved to the C:\Inbox folder and contains the result of the message exchange.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="fb826-158">So führen Sie eine (optionale) Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="fb826-158">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="fb826-159">Führen Sie die Datei "Cleanup.cmd" aus.</span><span class="sxs-lookup"><span data-stu-id="fb826-159">Run Cleanup.cmd.</span></span>  
  
    1.  <span data-ttu-id="fb826-160">Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="fb826-160">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="fb826-161">Navigieren Sie zum Ordner für dieses Beispiel, und führen "Cleanup.cmd" aus.</span><span class="sxs-lookup"><span data-stu-id="fb826-161">Navigate to the folder for this sample and run Cleanup.cmd.</span></span>  
  
2.  <span data-ttu-id="fb826-162">Entfernen Sie die virtuelle Anwendung für die Dienste.</span><span class="sxs-lookup"><span data-stu-id="fb826-162">Remove the virtual application for the services.</span></span>  
  
    1.  <span data-ttu-id="fb826-163">Öffnen Sie Internet Information Services (IIS) Manager mit `Inetmgr.exe` über eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="fb826-163">Open the Internet Information Services (IIS) Manager by running `Inetmgr.exe` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="fb826-164">Navigieren Sie zu der Standardwebsite, und entfernen Sie die **private** virtuelles Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fb826-164">Browse to the default Web site and remove the **private** virtual directory.</span></span>  
  
3.  <span data-ttu-id="fb826-165">Entfernen Sie die Warteschlangeneinrichtung für dieses Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fb826-165">Remove the queues set up for this sample.</span></span>  
  
    1.  <span data-ttu-id="fb826-166">Öffnen Sie die Konsole Computerverwaltung mit `Compmgmt.msc` über eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="fb826-166">Open the Computer Management console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="fb826-167">Erweitern Sie **Dienste und Anwendungen**, **Message Queuing-**, **Private Warteschlangen**.</span><span class="sxs-lookup"><span data-stu-id="fb826-167">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    3.  <span data-ttu-id="fb826-168">Löschen Sie die Warteschlangen durableduplex/service1.xamlx und durableduplex/service2.xamlx.</span><span class="sxs-lookup"><span data-stu-id="fb826-168">Delete the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues.</span></span>  
  
4.  <span data-ttu-id="fb826-169">Entfernen Sie das Verzeichnis C:\Inbox.</span><span class="sxs-lookup"><span data-stu-id="fb826-169">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fb826-170">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fb826-170">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fb826-171">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fb826-171">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fb826-172">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="fb826-172">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fb826-173">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fb826-173">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`