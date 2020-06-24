---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst'
description: Erfahren Sie, wie Sie einen WCF-Dienst erstellen, der von einem Windows-Dienst gehostet wird. Diese Hostingoption ist in allen Windows-Versionen verfügbar.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: 4e07aa7aac82fae5cfd1bfc759ef724cf87a873a
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246935"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a><span data-ttu-id="b5e8a-104">Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="b5e8a-104">How to: Host a WCF Service in a Managed Windows Service</span></span>

<span data-ttu-id="b5e8a-105">In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um einen von einem Windows-Dienst gehosteten Windows Communication Foundation (WCF)-Dienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-105">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted by a Windows Service.</span></span> <span data-ttu-id="b5e8a-106">Das Szenario wird durch die Hostingoption des verwalteten Windows-Diensts aktiviert, bei der es sich um einen WCF-Dienst mit langer Ausführungszeit handelt, der außerhalb von Internetinformationsdienste (IIS) in einer sicheren Umgebung gehostet wird, die nicht</span><span class="sxs-lookup"><span data-stu-id="b5e8a-106">The scenario is enabled by the managed Windows service hosting option that is a long-running WCF service hosted outside of Internet Information Services (IIS) in a secure environment that is not message activated.</span></span> <span data-ttu-id="b5e8a-107">Die Lebensdauer des Diensts wird stattdessen vom Betriebssystem gesteuert.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-107">The lifetime of the service is controlled instead by the operating system.</span></span> <span data-ttu-id="b5e8a-108">Diese Hostingoption ist in allen Windows-Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-108">This hosting option is available in all versions of Windows.</span></span>

<span data-ttu-id="b5e8a-109">Windows-Dienste können mit Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) verwaltet und so konfiguriert werden, dass sie beim Systemstart automatisch gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-109">Windows services can be managed with the Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) and can be configured to start up automatically when the system boots up.</span></span> <span data-ttu-id="b5e8a-110">Diese Hostingoption besteht darin, die Anwendungsdomäne (AppDomain), die einen WCF-Dienst hostet, als verwalteten Windows-Dienst zu registrieren, sodass die Prozess Lebensdauer des Diensts vom Dienststeuerungs-Manager (SCM) für Windows-Dienste gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-110">This hosting option consists of registering the application domain (AppDomain) that hosts a WCF service as a managed Windows service so that the process lifetime of the service is controlled by the Service Control Manager (SCM) for Windows services.</span></span>

<span data-ttu-id="b5e8a-111">Der Dienstcode enthält eine Dienstimplementierung des Dienstvertrags, eine Windows-Dienstklasse und eine Installerklasse.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-111">The service code includes a service implementation of the service contract, a Windows Service class, and an installer class.</span></span> <span data-ttu-id="b5e8a-112">Die Dienst Implementierungs Klasse, `CalculatorService` , ist ein WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-112">The service implementation class, `CalculatorService`, is a WCF service.</span></span> <span data-ttu-id="b5e8a-113">`CalculatorWindowsService` ist ein Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-113">The `CalculatorWindowsService` is a Windows service.</span></span> <span data-ttu-id="b5e8a-114">Damit sich die Klasse als Windows-Dienst eignet, erbt sie von `ServiceBase` und implementiert die `OnStart`-Methode und die `OnStop`-Methode.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-114">To qualify as a Windows service, the class inherits from `ServiceBase` and implements the `OnStart` and `OnStop` methods.</span></span> <span data-ttu-id="b5e8a-115">In `OnStart` wird <xref:System.ServiceModel.ServiceHost> für den `CalculatorService`-Typ erstellt und geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-115">In `OnStart`, a <xref:System.ServiceModel.ServiceHost> is created for the `CalculatorService` type and opened.</span></span> <span data-ttu-id="b5e8a-116">In `OnStop` wird der Dienst beendet und verworfen.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-116">In `OnStop`, the service is stopped and disposed.</span></span> <span data-ttu-id="b5e8a-117">Der Host ist außerdem für die Bereitstellung einer Basisadresse für den Diensthost verantwortlich, die in den Anwendungseinstellungen konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-117">The host is also responsible for providing a base address to the service host, which has been configured in application settings.</span></span> <span data-ttu-id="b5e8a-118">Durch die Installerklasse, die von <xref:System.Configuration.Install.Installer> erbt, kann das Programm mit dem Tool "Installutil.exe" als Windows-Dienst installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-118">The installer class, which inherits from <xref:System.Configuration.Install.Installer>, allows the program to be installed as a Windows service by the Installutil.exe tool.</span></span>

## <a name="construct-the-service-and-provide-the-hosting-code"></a><span data-ttu-id="b5e8a-119">Erstellen des Diensts und Bereitstellen des Hostcodes</span><span class="sxs-lookup"><span data-stu-id="b5e8a-119">Construct the service and provide the hosting code</span></span>

1. <span data-ttu-id="b5e8a-120">Erstellen Sie ein neues Visual Studio- **Konsolen-App** -Projekt namens **Service**.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-120">Create a new Visual Studio **Console app** project called **Service**.</span></span>

2. <span data-ttu-id="b5e8a-121">Benennen Sie "Program.cs" in "Service.cs" um.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-121">Rename Program.cs to Service.cs.</span></span>

3. <span data-ttu-id="b5e8a-122">Ändern Sie den-Namespace in `Microsoft.ServiceModel.Samples` .</span><span class="sxs-lookup"><span data-stu-id="b5e8a-122">Change the namespace to `Microsoft.ServiceModel.Samples`.</span></span>

4. <span data-ttu-id="b5e8a-123">Fügen Sie Verweise auf die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="b5e8a-123">Add references to the following assemblies:</span></span>

    - <span data-ttu-id="b5e8a-124">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="b5e8a-124">System.ServiceModel.dll</span></span>

    - <span data-ttu-id="b5e8a-125">System.ServiceProcess.dll</span><span class="sxs-lookup"><span data-stu-id="b5e8a-125">System.ServiceProcess.dll</span></span>

    - <span data-ttu-id="b5e8a-126">System.Configuration.Install.dll</span><span class="sxs-lookup"><span data-stu-id="b5e8a-126">System.Configuration.Install.dll</span></span>

5. <span data-ttu-id="b5e8a-127">Fügen Sie der Datei "Service.cs" die folgenden using-Anweisungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-127">Add the following using statements to Service.cs.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. <span data-ttu-id="b5e8a-128">Definieren Sie den `ICalculator`-Dienstvertrag, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-128">Define the `ICalculator` service contract as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. <span data-ttu-id="b5e8a-129">Implementieren Sie den Dienstvertrag in einer Klasse namens `CalculatorService`, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-129">Implement the service contract in a class called `CalculatorService` as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. <span data-ttu-id="b5e8a-130">Erstellen Sie eine neue Klasse namens `CalculatorWindowsService`, die von der <xref:System.ServiceProcess.ServiceBase>-Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-130">Create a new class called `CalculatorWindowsService` that inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="b5e8a-131">Fügen Sie eine lokale Variable namens `serviceHost` hinzu, die auf die <xref:System.ServiceModel.ServiceHost>-Instanz verweist.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-131">Add a local variable called `serviceHost` to reference the <xref:System.ServiceModel.ServiceHost> instance.</span></span> <span data-ttu-id="b5e8a-132">Definieren Sie die `Main`-Methode, die `ServiceBase.Run(new CalculatorWindowsService)` aufruft.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-132">Define the `Main` method that calls `ServiceBase.Run(new CalculatorWindowsService)`</span></span>

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. <span data-ttu-id="b5e8a-133">Überschreiben Sie die <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>-Methode, indem Sie eine neue <xref:System.ServiceModel.ServiceHost>-Instanz erstellen und öffnen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-133">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> method by creating and opening a new <xref:System.ServiceModel.ServiceHost> instance as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. <span data-ttu-id="b5e8a-134">Überschreiben Sie die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Methode, indem Sie <xref:System.ServiceModel.ServiceHost> schließen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-134">Override the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method closing the <xref:System.ServiceModel.ServiceHost> as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. <span data-ttu-id="b5e8a-135">Erstellen Sie eine neue Klasse namens `ProjectInstaller`, die von <xref:System.Configuration.Install.Installer> erbt und die mit dem auf <xref:System.ComponentModel.RunInstallerAttribute> festgelegten `true` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-135">Create a new class called `ProjectInstaller` that inherits from <xref:System.Configuration.Install.Installer> and that is marked with the <xref:System.ComponentModel.RunInstallerAttribute> set to `true`.</span></span> <span data-ttu-id="b5e8a-136">Dies ermöglicht die Installation des Tools "Installutil.exe" durch den Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-136">This allows the Windows service to be installed by the Installutil.exe tool.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. <span data-ttu-id="b5e8a-137">Entfernen Sie die `Service`-Klasse, die beim Erstellen des Projekts generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-137">Remove the `Service` class that was generated when you created the project.</span></span>

13. <span data-ttu-id="b5e8a-138">Fügen Sie dem Projekt eine Anwendungskonfigurationsdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-138">Add an application configuration file to the project.</span></span> <span data-ttu-id="b5e8a-139">Ersetzen Sie den Inhalt der Datei durch das folgende Konfigurations-XML.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-139">Replace the contents of the file with the following configuration XML.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.serviceModel>    <services>
          <!-- This section is optional with the new configuration model
               introduced in .NET Framework 4. -->
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"
                   behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
            <endpoint address=""
                      binding="wsHttpBinding"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />
          </service>
        </services>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceMetadata httpGetEnabled="true"/>
              <serviceDebug includeExceptionDetailInFaults="False"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>
      </system.serviceModel>
    </configuration>
    ```

     <span data-ttu-id="b5e8a-140">Klicken Sie mit der rechten Maustaste auf die Datei App.config im **Projektmappen-Explorer** und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-140">Right click the App.config file in the **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="b5e8a-141">Wählen Sie unter **in Ausgabeverzeichnis kopieren die** Option **kopieren, wenn neuer**aus.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-141">Under **Copy to Output Directory** select **Copy if Newer**.</span></span>

     <span data-ttu-id="b5e8a-142">In diesem Beispiel werden die Endpunkte in der Konfigurationsdatei explizit angegeben.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-142">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="b5e8a-143">Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-143">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="b5e8a-144">Da in diesem Beispiel das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> des Diensts auf `true` festgelegt ist, ist für den Dienst auch die Veröffentlichung von Metadaten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-144">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, your service also has publishing metadata enabled.</span></span> <span data-ttu-id="b5e8a-145">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b5e8a-145">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="install-and-run-the-service"></a><span data-ttu-id="b5e8a-146">Installieren Sie den Dienst, und führen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-146">Install and run the service</span></span>

1. <span data-ttu-id="b5e8a-147">Erstellen Sie die Projektmappe, um `Service.exe` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-147">Build the solution to create the `Service.exe` executable.</span></span>

2. <span data-ttu-id="b5e8a-148">Öffnen Sie Developer-Eingabeaufforderung für Visual Studio, und navigieren Sie zum Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-148">Open Developer Command Prompt for Visual Studio and navigate to the project directory.</span></span> <span data-ttu-id="b5e8a-149">Geben Sie an der Eingabeaufforderung `installutil bin\service.exe` ein, um den Windows-Dienst zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-149">Type `installutil bin\service.exe` at the command prompt to install the Windows service.</span></span>

     <span data-ttu-id="b5e8a-150">Geben Sie an der Eingabeaufforderung `services.msc` ein, um auf den Dienststeuerungs-Manager (SCM) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-150">Type `services.msc` at the command prompt to access the Service Control Manager (SCM).</span></span> <span data-ttu-id="b5e8a-151">Der Windows-Dienst müsste unter "Dienste" als "WCFWindowsServiceSample" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-151">The Windows service should appear in Services as "WCFWindowsServiceSample".</span></span> <span data-ttu-id="b5e8a-152">Der WCF-Dienst kann nur auf Clients antworten, wenn der Windows-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-152">The WCF service can only respond to clients if the Windows service is running.</span></span> <span data-ttu-id="b5e8a-153">Um den Dienst zu starten, klicken Sie im SCM mit der rechten Maustaste darauf, und wählen Sie "Start", oder geben Sie an der Eingabeaufforderung **net Start wcfwindowsservicesample** ein.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-153">To start the service, right-click it in the SCM and select "Start", or type **net start WCFWindowsServiceSample** at the command prompt.</span></span>

3. <span data-ttu-id="b5e8a-154">Wenn Sie Änderungen am Dienst vornehmen, müssen Sie ihn zuerst stoppen und dann deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-154">If you make changes to the service, you must first stop it and uninstall it.</span></span> <span data-ttu-id="b5e8a-155">Um den Dienst zu unterbinden, klicken Sie im SCM mit der rechten Maustaste auf den Dienst, und wählen Sie "Abbrechen" aus, oder geben Sie an der Eingabeaufforderung **net stoppwcfwindowsservicesample** ein.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-155">To stop the service, right-click the service in the SCM and select "Stop", or **type net stop WCFWindowsServiceSample** at the command prompt.</span></span> <span data-ttu-id="b5e8a-156">Wenn Sie den Windows-Dienst beenden und anschließend einen Client ausführen, tritt eine Ausnahme vom Typ <xref:System.ServiceModel.EndpointNotFoundException> auf, wenn ein Client versucht, auf den Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-156">Note that if you stop the Windows service and then run a client, an <xref:System.ServiceModel.EndpointNotFoundException> exception occurs when a client attempts to access the service.</span></span> <span data-ttu-id="b5e8a-157">Um den Windows-Diensttyp " **installutil/u bin\service.exe** an der Eingabeaufforderung zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-157">To uninstall the Windows service type **installutil /u bin\service.exe** at the command prompt.</span></span>

## <a name="example"></a><span data-ttu-id="b5e8a-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5e8a-158">Example</span></span>

<span data-ttu-id="b5e8a-159">Im folgenden finden Sie eine komplette Liste des in diesem Thema verwendeten Codes:</span><span class="sxs-lookup"><span data-stu-id="b5e8a-159">The following is a complete listing of the code used by this topic:</span></span>

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

<span data-ttu-id="b5e8a-160">Wie bei der Option für das "Selbsthosting" muss auch bei der Hostumgebung des Windows-Diensts ein Teil des Hostcodes eine Komponente der Anwendung sein.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-160">Like the "Self-Hosting" option, the Windows service hosting environment requires that some hosting code be written as part of the application.</span></span> <span data-ttu-id="b5e8a-161">Der Dienst wird als eine Konsolenanwendung implementiert und enthält seinen eigenen Hostingcode.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-161">The service is implemented as a console application and contains its own hosting code.</span></span> <span data-ttu-id="b5e8a-162">In anderen Hostumgebungen, z. B. WAS (Windows Process Activation Service, Windows-Prozessaktivierungsdienst) in IIS (Internet Information Services, Internetinformationsdienste), müssen Entwickler keinen Hostcode schreiben.</span><span class="sxs-lookup"><span data-stu-id="b5e8a-162">In other hosting environments, such as Windows Process Activation Service (WAS) hosting in Internet Information Services (IIS), it is not necessary for developers to write hosting code.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5e8a-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5e8a-163">See also</span></span>

- [<span data-ttu-id="b5e8a-164">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b5e8a-164">Simplified Configuration</span></span>](../simplified-configuration.md)
- [<span data-ttu-id="b5e8a-165">Hosten in einer verwalteten Anwendung</span><span class="sxs-lookup"><span data-stu-id="b5e8a-165">Hosting in a Managed Application</span></span>](hosting-in-a-managed-application.md)
- [<span data-ttu-id="b5e8a-166">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="b5e8a-166">Hosting Services</span></span>](../hosting-services.md)
- <span data-ttu-id="b5e8a-167">[Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b5e8a-167">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
