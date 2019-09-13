---
title: 'Tutorial: Erstellen eines Windows Communication Foundation Clients'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: ddb5167c7f71a263377fb465ec44ee21057fbf4a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928906"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="de0bf-102">Tutorial: Erstellen eines Windows Communication Foundation Clients</span><span class="sxs-lookup"><span data-stu-id="de0bf-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="de0bf-103">In diesem Tutorial werden die vier von fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="de0bf-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="de0bf-104">Eine Übersicht über die Tutorials finden [Sie unter Tutorial: Beginnen Sie mit Windows Communication Foundation Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="de0bf-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="de0bf-105">Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht darin, einen Client zu erstellen, indem Sie Metadaten von einem WCF-Dienst abrufen.</span><span class="sxs-lookup"><span data-stu-id="de0bf-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="de0bf-106">Sie verwenden Visual Studio zum Hinzufügen eines Dienst Verweises, mit dem die Metadaten vom MEX-Endpunkt des dienstanders abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="de0bf-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="de0bf-107">Visual Studio generiert dann eine verwaltete Quell Code Datei für einen Client Proxy in der Sprache, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="de0bf-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="de0bf-108">Außerdem wird eine Client Konfigurationsdatei (*app. config*) erstellt.</span><span class="sxs-lookup"><span data-stu-id="de0bf-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="de0bf-109">Diese Datei ermöglicht der Client Anwendung das Herstellen einer Verbindung mit dem Dienst an einem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="de0bf-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="de0bf-110">Wenn Sie einen WCF-Dienst aus einem Klassen Bibliotheksprojekt in Visual Studio aufzurufen, verwenden Sie die **Dienstverweis hinzufügen** Funktion, um automatisch einen Proxy und eine zugehörige Konfigurationsdatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="de0bf-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="de0bf-111">Da in Klassen Bibliotheks Projekten diese Konfigurationsdatei jedoch nicht verwendet wird, müssen Sie die Einstellungen in der generierten Konfigurationsdatei der Datei *app. config* für die ausführbare Datei hinzufügen, die die Klassenbibliothek aufruft.</span><span class="sxs-lookup"><span data-stu-id="de0bf-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="de0bf-112">Verwenden Sie alternativ das [Service Model Metadata Utility-Tool](#servicemodel-metadata-utility-tool) anstelle von Visual Studio, um die Proxy Klasse und die Konfigurationsdatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="de0bf-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="de0bf-113">Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="de0bf-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="de0bf-114">Dieses Verfahren wird in [Tutorial: Verwenden Sie einen](how-to-use-a-wcf-client.md)-Client.</span><span class="sxs-lookup"><span data-stu-id="de0bf-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="de0bf-115">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="de0bf-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="de0bf-116">Erstellen und konfigurieren Sie ein Konsolen-App-Projekt für den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="de0bf-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="de0bf-117">Fügen Sie dem WCF-Dienst einen Dienst Verweis hinzu, um die Proxy Klasse und die Konfigurationsdateien zu generieren.</span><span class="sxs-lookup"><span data-stu-id="de0bf-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="de0bf-118">Erstellen eines Windows Communication Foundation Clients</span><span class="sxs-lookup"><span data-stu-id="de0bf-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="de0bf-119">Erstellen eines Konsolen-App-Projekts in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="de0bf-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="de0bf-120">Wählen Sie im Menü **Datei** die Option**Projekt/Projekt** Mappe **Öffnen** > aus, und navigieren Sie zur zuvor erstellten Lösung **GettingStarted** (*GettingStarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="de0bf-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="de0bf-121">Wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="de0bf-121">Select **Open**.</span></span>

    2. <span data-ttu-id="de0bf-122">Wählen Sie im Menü **Ansicht** die Option **Projektmappen-Explorer**aus.</span><span class="sxs-lookup"><span data-stu-id="de0bf-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="de0bf-123">Wählen Sie im Fenster **Projektmappen-Explorer** die Lösung **GettingStarted** (oberer Knoten) aus, und klicken Sie dann im Kontextmenü auf**Neues Projekt** **Hinzufügen** > .</span><span class="sxs-lookup"><span data-stu-id="de0bf-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="de0bf-124">Wählen Sie im Fenster **Neues Projekt hinzufügen** auf der linken Seite unter **Visual C#**  oder **Visual Basic**die Kategorie **Windows-Desktop** aus.</span><span class="sxs-lookup"><span data-stu-id="de0bf-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="de0bf-125">Wählen Sie die Vorlage **Konsolen-app (.NET Framework)** aus, und geben Sie als **Name den Namen** *gettingstartedclient* ein.</span><span class="sxs-lookup"><span data-stu-id="de0bf-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="de0bf-126">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="de0bf-126">Select **OK**.</span></span>

2. <span data-ttu-id="de0bf-127">Fügen Sie der <xref:System.ServiceModel> Assembly einen Verweis im **gettingstartedclient** -Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="de0bf-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="de0bf-128">Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **Verweise** unter dem **gettingstartedclient** -Projekt aus, und klicken Sie dann im Kontextmenü auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="de0bf-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="de0bf-129">Wählen Sie im Fenster **Verweis hinzufügen** unter Assemblys auf der linken Seite des Fensters **Framework** **aus.**</span><span class="sxs-lookup"><span data-stu-id="de0bf-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="de0bf-130">Suchen und wählen Sie **System. Service Model**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="de0bf-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="de0bf-131">Speichern Sie die Projekt Mappe, indem Sie **Datei** > **Alle speichern**auswählen.</span><span class="sxs-lookup"><span data-stu-id="de0bf-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="de0bf-132">Fügen Sie dem Rechner Dienst einen Dienst Verweis hinzu:</span><span class="sxs-lookup"><span data-stu-id="de0bf-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="de0bf-133">Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **Verweise** unter dem **gettingstartedclient** -Projekt aus, und klicken Sie dann im Kontextmenü **Dienstverweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="de0bf-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="de0bf-134">Klicken Sie im Fenster **Dienstverweis hinzufügen** auf **ermitteln**.</span><span class="sxs-lookup"><span data-stu-id="de0bf-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="de0bf-135">Der Dienst "CalculatorService" wird gestartet, und Visual Studio zeigt ihn im Feld " **Dienste** " an.</span><span class="sxs-lookup"><span data-stu-id="de0bf-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="de0bf-136">Wählen Sie **CalculatorService** aus, um ihn zu erweitern und die vom Dienst implementierten Dienstverträge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de0bf-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="de0bf-137">Belassen Sie den Standard **Namespace** , und wählen Sie **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="de0bf-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="de0bf-138">Visual Studio fügt ein neues Element unter dem Ordner " **verbundene Dienste** " im **gettingstartedclient** -Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="de0bf-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="de0bf-139">Service Model Metadata Utility-Tool</span><span class="sxs-lookup"><span data-stu-id="de0bf-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="de0bf-140">In den folgenden Beispielen wird gezeigt, wie Sie optional das [Service Model Metadata Utility-Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden, um die Proxy Klassendatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="de0bf-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="de0bf-141">Mit diesem Tool werden die Proxy Klassendatei und die Datei " *app. config* " generiert.</span><span class="sxs-lookup"><span data-stu-id="de0bf-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="de0bf-142">In den folgenden Beispielen wird gezeigt, wie der Proxy C# in bzw. Visual Basic generiert wird:</span><span class="sxs-lookup"><span data-stu-id="de0bf-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="de0bf-143">Client Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="de0bf-143">Client configuration file</span></span>

<span data-ttu-id="de0bf-144">Nachdem Sie den Client erstellt haben, erstellt Visual Studio die Konfigurationsdatei " **app. config** " im **gettingstartedclient** -Projekt, die dem folgenden Beispiel ähnelt:</span><span class="sxs-lookup"><span data-stu-id="de0bf-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

<span data-ttu-id="de0bf-145">Beachten Sie im Abschnitt [ System.ServiceModel>denEndpunkt>-Elements.\<](../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<](../configure-apps/file-schema/wcf/endpoint-element.md)</span><span class="sxs-lookup"><span data-stu-id="de0bf-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="de0bf-146">**Das&lt;Endpunkt&gt;** Element definiert den Endpunkt, den der Client für den Zugriff auf den Dienst verwendet, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="de0bf-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="de0bf-147">Adresse: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="de0bf-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="de0bf-148">Die Adresse des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="de0bf-148">The address of the endpoint.</span></span>
- <span data-ttu-id="de0bf-149">Dienstvertrag: `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="de0bf-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="de0bf-150">Der Dienstvertrag verarbeitet die Kommunikation zwischen dem WCF-Client und dem-Dienst.</span><span class="sxs-lookup"><span data-stu-id="de0bf-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="de0bf-151">Visual Studio hat diesen Vertrag generiert, als Sie seine **Dienstverweis hinzufügen** -Funktion verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="de0bf-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="de0bf-152">Es handelt sich im Wesentlichen um eine Kopie des Vertrags, den Sie im gettingstartedlib-Projekt definiert haben.</span><span class="sxs-lookup"><span data-stu-id="de0bf-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="de0bf-153">Bindung: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="de0bf-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="de0bf-154">Die Bindung gibt HTTP als Transport, interoperable Sicherheit und andere Konfigurationsdetails an.</span><span class="sxs-lookup"><span data-stu-id="de0bf-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de0bf-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="de0bf-155">Next steps</span></span>

<span data-ttu-id="de0bf-156">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="de0bf-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="de0bf-157">Erstellen und konfigurieren Sie ein Konsolen-App-Projekt für den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="de0bf-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="de0bf-158">Fügen Sie dem WCF-Dienst einen Dienst Verweis hinzu, um die Proxy Klasse und die Konfigurationsdateien für die Client Anwendung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="de0bf-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="de0bf-159">Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den generierten Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="de0bf-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="de0bf-160">Tutorial: Verwenden eines WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="de0bf-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
