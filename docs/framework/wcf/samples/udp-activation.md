---
title: UDP-Aktivierung
ms.date: 03/30/2017
ms.assetid: 4b0ccd10-0dfb-4603-93f9-f0857c581cb7
ms.openlocfilehash: c0b351adb0b45f42404e94c74bdcff7785c2d0ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143719"
---
# <a name="udp-activation"></a><span data-ttu-id="e397e-102">UDP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="e397e-102">UDP Activation</span></span>
<span data-ttu-id="e397e-103">Dieses Beispiel basiert auf dem [Beispiel Transport: UDP.](../../../../docs/framework/wcf/samples/transport-udp.md)</span><span class="sxs-lookup"><span data-stu-id="e397e-103">This sample is based on the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="e397e-104">Es erweitert das [Transport: UDP-Beispiel](../../../../docs/framework/wcf/samples/transport-udp.md) zur Unterstützung der Prozessaktivierung mithilfe des Windows Process Activation Service (WAS).</span><span class="sxs-lookup"><span data-stu-id="e397e-104">It extends the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample to support process activation using the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="e397e-105">Das Beispiel besteht im Wesentlichen aus drei Teilen:</span><span class="sxs-lookup"><span data-stu-id="e397e-105">The sample consists of three major pieces:</span></span>  
  
- <span data-ttu-id="e397e-106">Einem UDP-Protokoll-Aktivierer, welcher ein eigenständiger Prozess ist, der für zu aktivierende Anwendungen UDP-Nachrichten empfängt.</span><span class="sxs-lookup"><span data-stu-id="e397e-106">A UDP Protocol Activator, a standalone process that receives UDP messages on behalf of applications that are to be activated.</span></span>  
  
- <span data-ttu-id="e397e-107">Einem Client, der mit dem benutzerdefinierten UDP-Transport Nachrichten sendet.</span><span class="sxs-lookup"><span data-stu-id="e397e-107">A client that uses the UDP custom transport to send messages.</span></span>  
  
- <span data-ttu-id="e397e-108">Einem Dienst, der in einem von WAS aktivierten Workerprozess gehostet wird und Nachrichten über den benutzerdefinierten UDP-Transport empfängt.</span><span class="sxs-lookup"><span data-stu-id="e397e-108">A service (hosted in a worker process activated by WAS) that receives messages over the UDP custom transport.</span></span>  
  
## <a name="udp-protocol-activator"></a><span data-ttu-id="e397e-109">UDP-Protokoll-Aktivierer</span><span class="sxs-lookup"><span data-stu-id="e397e-109">UDP Protocol Activator</span></span>  
 <span data-ttu-id="e397e-110">Der UDP-Protokollaktivator ist eine Brücke zwischen dem WCF-Client und dem WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="e397e-110">The UDP Protocol Activator is a bridge between the WCF client and the WCF service.</span></span> <span data-ttu-id="e397e-111">Er bietet Datenkommunikation über das UDP-Protokoll auf der Transportebene.</span><span class="sxs-lookup"><span data-stu-id="e397e-111">It provides data communication through the UDP protocol at the transport layer.</span></span> <span data-ttu-id="e397e-112">Seine zwei Hauptfunktionen sind:</span><span class="sxs-lookup"><span data-stu-id="e397e-112">It has two major functions:</span></span>  
  
- <span data-ttu-id="e397e-113">WAS-Listeneradapter (LA), der mit WAS zusammenarbeitet, um als Antwort auf eingehende Nachrichten Prozesse zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e397e-113">WAS Listener Adapter (LA), which collaborates with WAS to activate processes in response to incoming messages.</span></span>  
  
- <span data-ttu-id="e397e-114">UDP-Protokolllistener, der für zu aktivierende Anwendungen UDP-Nachrichten entgegennimmt.</span><span class="sxs-lookup"><span data-stu-id="e397e-114">UDP Protocol Listener, which accepts UDP messages on behalf of applications that are to be activated.</span></span>  
  
 <span data-ttu-id="e397e-115">Der Aktivierer muss auf dem Server als eigenständiges Programm ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e397e-115">The activator must be running as a standalone program on the server machine.</span></span> <span data-ttu-id="e397e-116">WAS-Listeneradapter (wie der NetTcpActivator und der NetPipeActivator) werden meist in Windows-Diensten mit langer Laufzeit implementiert.</span><span class="sxs-lookup"><span data-stu-id="e397e-116">Normally, WAS listener adapters (such as the NetTcpActivator and the NetPipeActivator) are implemented in long-running Windows services.</span></span> <span data-ttu-id="e397e-117">Im vorliegenden Beispiel wird der Protokollaktivierer aber aus Gründen der Einfachheit und Übersichtlichkeit als eigenständige Anwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="e397e-117">However, for simplicity and clarity, this sample implements the protocol activator as a standalone application.</span></span>  
  
### <a name="was-listener-adapter"></a><span data-ttu-id="e397e-118">WAS-Listeneradapter</span><span class="sxs-lookup"><span data-stu-id="e397e-118">WAS Listener Adapter</span></span>  
 <span data-ttu-id="e397e-119">Der WAS-Listeneradapter für UDP ist in der `UdpListenerAdapter`-Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="e397e-119">The WAS Listener Adapter for UDP is implemented in the `UdpListenerAdapter` class.</span></span> <span data-ttu-id="e397e-120">Das ist das Modul, das mit WAS interagiert, um Anwendungen für das UDP-Protokoll zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e397e-120">It is the module that interacts with WAS to perform application activation for the UDP protocol.</span></span> <span data-ttu-id="e397e-121">Dies erfolgt durch Aufrufen der folgenden Webhost-APIs:</span><span class="sxs-lookup"><span data-stu-id="e397e-121">This is achieved by calling the following Webhost APIs:</span></span>  
  
- `WebhostRegisterProtocol`  
  
- `WebhostUnregisterProtocol`  
  
- `WebhostOpenListenerChannelInstance`  
  
- `WebhostCloseAllListenerChannelInstances`  
  
 <span data-ttu-id="e397e-122">Nach dem ersten Aufrufen von `WebhostRegisterProtocol` empfängt der Listeneradapter den `ApplicationCreated`-Rückruf von WAS für alle in applicationHost.config (die sich unter %windir%\system32\inetsrv befindet) registrierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e397e-122">After initially calling `WebhostRegisterProtocol`, the listener adapter receives the callback `ApplicationCreated` from WAS for all of the applications registered in applicationHost.config (located in %windir%\system32\inetsrv).</span></span> <span data-ttu-id="e397e-123">In diesem Beispiel werden nur die Anwendungen mit aktiviertem UDP-Protokoll verarbeitet (mit der Protokoll-ID als "net.udp").</span><span class="sxs-lookup"><span data-stu-id="e397e-123">In this sample, we only handle the applications with the UDP protocol (with the protocol id as "net.udp") enabled.</span></span> <span data-ttu-id="e397e-124">In anderen Implementierungen kann dies anders gehalten werden, wenn diese Implementierungen auf dynamische Konfigurationsänderungen bei der Anwendung reagieren (wie zum Beispiel der Übergang einer Anwendung von aktiviert zu deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="e397e-124">Other implementations may handle this differently if such implementations respond to dynamic configuration changes to the application (for example, an application transition from disabled to enabled).</span></span>  
  
 <span data-ttu-id="e397e-125">Wenn der `ConfigManagerInitializationCompleted`-Rückruf empfangen wird, zeigt dies an, dass WAS sämtliche Benachrichtigungen für die Initialisierung des Protokolls abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="e397e-125">When the callback `ConfigManagerInitializationCompleted` is received, it indicates that WAS has finished all of the notifications for the initialization of the protocol.</span></span> <span data-ttu-id="e397e-126">Ab diesem Zeitpunkt ist der Listeneradapter bereit, Aktivierungsanforderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e397e-126">At this time, the listener adapter is ready to process activation requests.</span></span>  
  
 <span data-ttu-id="e397e-127">Wenn eine neue Anforderung für eine Anwendung zum ersten Mal eingeht, ruft der Listeneradapter `WebhostOpenListenerChannelInstance` in WAS auf, wodurch der Workerprozess gestartet wird (wenn er nicht bereits gestartet ist).</span><span class="sxs-lookup"><span data-stu-id="e397e-127">When a new request comes in the first time for an application, the listener adapter calls `WebhostOpenListenerChannelInstance` into WAS, which starts the worker process if it is not started yet.</span></span> <span data-ttu-id="e397e-128">Anschließend werden die Protokollhandler geladen, und die Kommunikation zwischen dem Listeneradapter und der virtuellen Anwendung kann beginnen.</span><span class="sxs-lookup"><span data-stu-id="e397e-128">Then the protocol handlers are loaded and the communication between the listener adapter and the virtual application can start.</span></span>  
  
 <span data-ttu-id="e397e-129">Der Listeneradapter ist im Abschnitt "%SystemRoot%" (> <`listenerAdapters` Systemroot) registriert.</span><span class="sxs-lookup"><span data-stu-id="e397e-129">The listener adapter is registered in the %SystemRoot%\System32\inetsrv\ApplicationHost.config in the <`listenerAdapters`> section as following:</span></span>  
  
```xml  
<add name="net.udp" identity="S-1-5-21-2127521184-1604012920-1887927527-387045" />  
```  
  
### <a name="protocol-listener"></a><span data-ttu-id="e397e-130">Protokolllistener</span><span class="sxs-lookup"><span data-stu-id="e397e-130">Protocol Listener</span></span>  
 <span data-ttu-id="e397e-131">Der UDP-Protokolllistener ist ein Modul innerhalb des Protokollaktivierers, der für die virtuelle Anwendung einen UDP-Endpunkt überwacht.</span><span class="sxs-lookup"><span data-stu-id="e397e-131">The UDP protocol listener is a module inside the protocol activator that listens at a UDP endpoint on behalf of the virtual application.</span></span> <span data-ttu-id="e397e-132">Er ist in der `UdpSocketListener`-Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="e397e-132">It is implemented in the class `UdpSocketListener`.</span></span> <span data-ttu-id="e397e-133">Der Endpunkt liegt als `IPEndpoint` vor, bei dem die Portnummer aus der Bindung des Protokolls für die Site extrahiert wird.</span><span class="sxs-lookup"><span data-stu-id="e397e-133">The endpoint is represented as `IPEndpoint` for which the port number is extracted from the binding of the protocol for the site.</span></span>  
  
### <a name="control-service"></a><span data-ttu-id="e397e-134">Steuerungsdienst</span><span class="sxs-lookup"><span data-stu-id="e397e-134">Control Service</span></span>  
 <span data-ttu-id="e397e-135">In diesem Beispiel verwenden wir WCF, um zwischen dem Aktivator und dem WAS-Workerprozess zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e397e-135">In this sample, we use WCF to communicate between the activator and the WAS worker process.</span></span> <span data-ttu-id="e397e-136">Der Dienst, der sich im Aktivierer befindet, wird als "Steuerungsdienst" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e397e-136">The service that resides in the activator is called the Control Service.</span></span>  
  
## <a name="protocol-handlers"></a><span data-ttu-id="e397e-137">Protokollhandler</span><span class="sxs-lookup"><span data-stu-id="e397e-137">Protocol Handlers</span></span>  
 <span data-ttu-id="e397e-138">Nachdem der Listeneradapter `WebhostOpenListenerChannelInstance` aufgerufen hat, startet der WAS-Prozess-Manager den Workerprozess (falls dieser noch nicht gestartet ist).</span><span class="sxs-lookup"><span data-stu-id="e397e-138">After the listener adapter calls `WebhostOpenListenerChannelInstance`, the WAS process manager starts the worker process if it is not started.</span></span> <span data-ttu-id="e397e-139">Anschließend lädt der im Workerprozess befindliche Anwendungs-Manager den UDP-Prozessprotokollhandler (PPH) mit der Anforderung nach dieser `ListenerChannelId`.</span><span class="sxs-lookup"><span data-stu-id="e397e-139">The application manager inside the worker process then loads the UDP Process Protocol Handler (PPH) with the request for that `ListenerChannelId`.</span></span> <span data-ttu-id="e397e-140">Die PPH wiederum `IAdphManager`ruft .`StartAppDomainProtocolListenerChannel`</span><span class="sxs-lookup"><span data-stu-id="e397e-140">The PPH in turns calls `IAdphManager`.`StartAppDomainProtocolListenerChannel`</span></span> <span data-ttu-id="e397e-141">, um den UDP AppDomain Protocol Handler (ADPH) zu starten.</span><span class="sxs-lookup"><span data-stu-id="e397e-141">to start the UDP AppDomain Protocol Handler (ADPH).</span></span>  
  
## <a name="hostedudptransportconfiguration"></a><span data-ttu-id="e397e-142">HostedUDPTransportConfiguration</span><span class="sxs-lookup"><span data-stu-id="e397e-142">HostedUDPTransportConfiguration</span></span>  
 <span data-ttu-id="e397e-143">Diese Informationen werden wie folgt in der Web.config registriert:</span><span class="sxs-lookup"><span data-stu-id="e397e-143">The information is registered in the Web.config as follows:</span></span>  
  
```xml  
<serviceHostingEnvironment>  
<add name="net.udp" transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />  
</serviceHostingEnvironment>  
```  
  
## <a name="special-setup-for-this-sample"></a><span data-ttu-id="e397e-144">Spezielle Einrichtung für dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="e397e-144">Special Setup for This Sample</span></span>  
 <span data-ttu-id="e397e-145">Dieses Beispiel kann nur unter Windows Vista, Windows Server 2008 oder Windows 7 erstellt und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e397e-145">This sample can be only built and run on Windows Vista, Windows Server 2008, or Windows 7.</span></span> <span data-ttu-id="e397e-146">Zum Ausführen des Beispiels müssen Sie zuerst sämtliche Komponenten ordnungsgemäß einrichten.</span><span class="sxs-lookup"><span data-stu-id="e397e-146">To run the sample, you must first get all of the components set up correctly.</span></span> <span data-ttu-id="e397e-147">Gehen Sie folgendermaßen vor, um das Beispiel zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e397e-147">Use the following steps to install the sample.</span></span>  
  
#### <a name="to-set-up-this-sample"></a><span data-ttu-id="e397e-148">So richten Sie dieses Beispiel ein</span><span class="sxs-lookup"><span data-stu-id="e397e-148">To set up this sample</span></span>  
  
1. <span data-ttu-id="e397e-149">Installieren Sie ASP.NET 4.0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="e397e-149">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="e397e-150">Erstellen Sie das Projekt unter Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="e397e-150">Build the project on Windows Vista.</span></span> <span data-ttu-id="e397e-151">Nach dem Kompilieren führt es in der Postbuildphase auch die folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="e397e-151">After compilation, it also performs the following operations in the post-build phase:</span></span>  
  
    - <span data-ttu-id="e397e-152">Es installiert die UDP-Bindung für die Site „Default Web Site“.</span><span class="sxs-lookup"><span data-stu-id="e397e-152">Installs the UDP binding to the site "Default Web Site".</span></span>  
  
    - <span data-ttu-id="e397e-153">Es erstellt den "ServiceModelSamples" der virtuellen Anwendung so, dass er auf den physischen Pfad zeigt: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".</span><span class="sxs-lookup"><span data-stu-id="e397e-153">Creates the virtual application "ServiceModelSamples" to point to the physical path: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".</span></span>  
  
    - <span data-ttu-id="e397e-154">Außerdem aktiviert es für diese virtuelle Anwendung das "net.udp"-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="e397e-154">It also enables "net.udp" protocol for this virtual application.</span></span>  
  
3. <span data-ttu-id="e397e-155">Starten Sie die Benutzeroberflächenanwendung "WasNetActivator.exe".</span><span class="sxs-lookup"><span data-stu-id="e397e-155">Start the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="e397e-156">Klicken Sie auf die Registerkarte **Setup,** aktivieren Sie die folgenden Kontrollkästchen, und klicken Sie dann auf **Installieren,** um sie zu installieren:</span><span class="sxs-lookup"><span data-stu-id="e397e-156">Click the **Setup** tab, check the following check boxes and then click **Install** to install them:</span></span>  
  
    - <span data-ttu-id="e397e-157">UDP-Listeneradapter</span><span class="sxs-lookup"><span data-stu-id="e397e-157">UDP Listener Adapter</span></span>  
  
    - <span data-ttu-id="e397e-158">UDP-Protokollhandler</span><span class="sxs-lookup"><span data-stu-id="e397e-158">UDP Protocol Handlers</span></span>  
  
4. <span data-ttu-id="e397e-159">Klicken Sie auf die **Registerkarte Aktivierung** der Benutzeroberfläche Anwendung "WasNetActivator.exe".</span><span class="sxs-lookup"><span data-stu-id="e397e-159">Click the **Activation** tab of the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="e397e-160">Klicken Sie auf die Schaltfläche **Start,** um den Listeneradapter zu starten.</span><span class="sxs-lookup"><span data-stu-id="e397e-160">Click the **Start** button to start the listener adapter.</span></span> <span data-ttu-id="e397e-161">Nun können Sie das Programm ausführen.</span><span class="sxs-lookup"><span data-stu-id="e397e-161">Now you are ready to run the program.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e397e-162">Wenn Sie die Arbeit mit diesem Beispiel abgeschlossen haben, müssen Sie Cleanup.bat ausführen, um die net.udp-Bindung aus der „Default Web Site“ zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e397e-162">When you are finished with this sample, you must run Cleanup.bat to remove the net.udp binding from the "Default Web Site".</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="e397e-163">Beispielverwendung</span><span class="sxs-lookup"><span data-stu-id="e397e-163">Sample Usage</span></span>  
 <span data-ttu-id="e397e-164">Nach dem Kompilieren liegen vier verschiedene Binärdateien vor:</span><span class="sxs-lookup"><span data-stu-id="e397e-164">After compilation, there are four different binaries generated:</span></span>  
  
- <span data-ttu-id="e397e-165">Client.exe: Der Clientcode.</span><span class="sxs-lookup"><span data-stu-id="e397e-165">Client.exe: The client code.</span></span> <span data-ttu-id="e397e-166">Die App.config ist in die Client.exe-Clientkonfigurationsdatei hinein kompiliert.</span><span class="sxs-lookup"><span data-stu-id="e397e-166">The App.config is compiled into the client configuration file Client.exe.config.</span></span>  
  
- <span data-ttu-id="e397e-167">UDPActivation.dll: Die Bibliothek, die alle wichtigen UDP-Implementierungen enthält.</span><span class="sxs-lookup"><span data-stu-id="e397e-167">UDPActivation.dll: the library that contains all of the major UDP implementations.</span></span>  
  
- <span data-ttu-id="e397e-168">Service.dll: Der Dienstcode.</span><span class="sxs-lookup"><span data-stu-id="e397e-168">Service.dll: The service code.</span></span> <span data-ttu-id="e397e-169">Diese wird in das Verzeichnis \bin der virtuellen Anwendung ServiceModelSamples kopiert.</span><span class="sxs-lookup"><span data-stu-id="e397e-169">This is copied to the \bin directory of the virtual application ServiceModelSamples.</span></span> <span data-ttu-id="e397e-170">Die Dienstdatei ist Service.svc und die Konfigurationsdatei ist Web.config. Nach der Kompilierung werden sie an den folgenden Speicherort kopiert: %SystemDrive%-Inetpub-wwwroot-ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="e397e-170">The service file is Service.svc and the configuration file is Web.config. After compilation, they are copied to the following location: %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples.</span></span>  
  
- <span data-ttu-id="e397e-171">WasNetActivator: Das UDP-Aktiviererprogramm.</span><span class="sxs-lookup"><span data-stu-id="e397e-171">WasNetActivator: The UDP activator program.</span></span>  
  
- <span data-ttu-id="e397e-172">Stellen Sie sicher, dass alle erforderlichen Bestandteile ordnungsgemäß installiert sind.</span><span class="sxs-lookup"><span data-stu-id="e397e-172">Ensure that all of the required pieces are installed correctly.</span></span> <span data-ttu-id="e397e-173">Die folgenden Schritte zeigen, wie das Beispiel ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="e397e-173">The following steps show how to run the sample:</span></span>  
  
1. <span data-ttu-id="e397e-174">Stellen Sie sicher, dass die folgenden Windows-Dienste gestartet sind:</span><span class="sxs-lookup"><span data-stu-id="e397e-174">Ensure that the following Windows services have been started:</span></span>  
  
    - <span data-ttu-id="e397e-175">WAS (Windows Process Activation Service)</span><span class="sxs-lookup"><span data-stu-id="e397e-175">Windows Process Activation Service (WAS).</span></span>  
  
    - <span data-ttu-id="e397e-176">Internetinformationsdienste (IIS): W3SVC.</span><span class="sxs-lookup"><span data-stu-id="e397e-176">Internet Information Services (IIS): W3SVC.</span></span>  
  
2. <span data-ttu-id="e397e-177">Starten Sie anschließend den Aktivierer (WasNetActivator.exe).</span><span class="sxs-lookup"><span data-stu-id="e397e-177">Then start the activator, WasNetActivator.exe.</span></span> <span data-ttu-id="e397e-178">Auf der Registerkarte **Aktivierung** wird das einzige Protokoll, **UDP**, in der Dropdown-Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e397e-178">Under the **Activation** tab, the only protocol, **UDP**, is selected in the drop down list.</span></span> <span data-ttu-id="e397e-179">Klicken Sie auf die Schaltfläche **Start,** um den Aktivator zu starten.</span><span class="sxs-lookup"><span data-stu-id="e397e-179">Click the **Start** button to start the activator.</span></span>  
  
3. <span data-ttu-id="e397e-180">Wenn der Aktivierer gestartet ist, können Sie den Clientcode ausführen, indem Sie in einem Befehlsfenster die Client.exe ausführen.</span><span class="sxs-lookup"><span data-stu-id="e397e-180">Once the activator is started, you can run the client code by running Client.exe from a command window.</span></span> <span data-ttu-id="e397e-181">Nachfolgend ist die Ausgabe des Beispiels aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e397e-181">The following is the sample output:</span></span>  
  
    ```console  
    Testing Udp Activation.  
    Start the status service.  
    Sending UDP datagrams.  
    Type a word that you want to say to the server: Hello, world!  
        Sending datagram: Hello, world![0]  
        Sending datagram: Hello, world![1]  
        Sending datagram: Hello, world![2]  
        Sending datagram: Hello, world![3]  
        Sending datagram: Hello, world![4]  
    Calling UDP duplex contract (ICalculatorContract).  
        0 + 0 = 0  
        1 + 2 = 3  
        2 + 4 = 6  
        3 + 6 = 9  
        4 + 8 = 12  
    Getting status and dump server traces:  
        Operation 'Hello' is called: Hello, world![0]  
        Operation 'Hello' is called: Hello, world![1]  
        Operation 'Hello' is called: Hello, world![2]  
        Operation 'Hello' is called: Hello, world![3]  
        Operation 'Hello' is called: Hello, world![4]  
        Operation 'Add' is called: 0 + 0  
        Operation 'Add' is called: 1 + 2  
        Operation 'Add' is called: 2 + 4  
        Operation 'Add' is called: 3 + 6  
        Operation 'Add' is called: 4 + 8  
    Press <ENTER> to complete test.  
    ```  
  
> [!IMPORTANT]
> <span data-ttu-id="e397e-182">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e397e-182">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e397e-183">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e397e-183">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e397e-184">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="e397e-184">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e397e-185">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e397e-185">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\UdpActivation`  
