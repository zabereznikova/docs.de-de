---
title: 'Tutorial: Erstellen eines Windows Communication Foundation-Clients'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 0f7f622221e6612ecdb0ea04084d81e923218a5c
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634062"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="19280-102">Tutorial: Erstellen eines Windows Communication Foundation-Clients</span><span class="sxs-lookup"><span data-stu-id="19280-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="19280-103">In diesem Tutorial wird die vierte von fünf Schritte zur Erstellung einer grundlegenden Windows Communication Foundation (WCF)-Anwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="19280-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="19280-104">Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="19280-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="19280-105">Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht, erstellen Sie einen Client vom Abrufen von Metadaten aus einem WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="19280-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="19280-106">Verwenden Sie Visual Studio einen Dienstverweis hinzufügen, der Metadaten vom MEX-Endpunkt des Diensts erhält.</span><span class="sxs-lookup"><span data-stu-id="19280-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="19280-107">Visual Studio generiert dann eine verwaltete Quellcodedatei für einen Clientproxy in der Sprache, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="19280-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="19280-108">Erstellt auch eine Clientkonfigurationsdatei (*"App.config"*).</span><span class="sxs-lookup"><span data-stu-id="19280-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="19280-109">Diese Datei können die Clientanwendung eine Verbindung mit dem Dienst an einem Endpunkt herstellen.</span><span class="sxs-lookup"><span data-stu-id="19280-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="19280-110">Wenn Sie einen WCF-Dienst aus einem Klassenbibliotheksprojekt in Visual Studio aufrufen, verwenden Sie die **Dienstverweis hinzufügen** Funktion, um automatisch einen Proxy und eine zugeordnete Konfigurationsdatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="19280-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="19280-111">Aber da Klassenbibliotheksprojekte diese Konfigurationsdatei nicht verwenden, müssen Sie die Einstellungen in der generierten Konfigurationsdatei zum Hinzufügen der *"App.config"* -Datei für die ausführbare Datei, die die Klassenbibliothek aufruft.</span><span class="sxs-lookup"><span data-stu-id="19280-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="19280-112">Verwenden Sie alternativ die [ServiceModel Metadata Utility-Tool](#servicemodel-metadata-utility-tool) anstelle von Visual Studio, um den Proxycode und der Konfigurationsdatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="19280-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="19280-113">Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="19280-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="19280-114">Dieses Verfahren wird beschrieben, [Lernprogramm: Verwenden Sie einen Client](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="19280-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="19280-115">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="19280-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="19280-116">Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt für den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="19280-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="19280-117">Fügen Sie einen Dienstverweis auf den WCF-Dienst, um den Proxy-Klasse und die Konfigurationsdateien zu generieren.</span><span class="sxs-lookup"><span data-stu-id="19280-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>


## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="19280-118">Erstellen eines Windows Communication Foundation-Clients</span><span class="sxs-lookup"><span data-stu-id="19280-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="19280-119">Erstellen Sie ein Konsolenanwendungsprojekt in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="19280-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="19280-120">Von der **Datei** , wählen Sie im Menü **öffnen** > **Projekt/Projektmappe** und navigieren Sie zu der **GettingStarted** Lösung Sie zuvor erstellt haben (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="19280-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="19280-121">Wählen Sie **öffnen**.</span><span class="sxs-lookup"><span data-stu-id="19280-121">Select **Open**.</span></span>

    2. <span data-ttu-id="19280-122">Von der **Ansicht** , wählen Sie im Menü **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="19280-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="19280-123">In der **Projektmappen-Explorer** wählen Sie im Fenster der **GettingStarted** -Lösung (obersten Knoten), und wählen Sie dann **hinzufügen** > **neues Projekt** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="19280-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="19280-124">In der **neues Projekt hinzufügen** Fenster auf der linken Seite auf die **Windows Desktop** unter Kategorie **Visual C#**  oder **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="19280-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="19280-125">Wählen Sie die **Konsolen-App ((.NET Framework)** Vorlage, und geben Sie *"gettingstartedclient"* für die **Namen**.</span><span class="sxs-lookup"><span data-stu-id="19280-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="19280-126">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="19280-126">Select **OK**.</span></span>

2. <span data-ttu-id="19280-127">Fügen Sie einen Verweis in der **"gettingstartedclient"** Projekt die <xref:System.ServiceModel> Assembly:</span><span class="sxs-lookup"><span data-stu-id="19280-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1.  <span data-ttu-id="19280-128">In der **Projektmappen-Explorer** wählen Sie im Fenster der **Verweise** Ordner unter dem **"gettingstartedclient"** Projekt, und wählen Sie dann **"Verweis hinzufügen"** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="19280-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="19280-129">In der **Verweis hinzufügen** Fenster unter **Assemblys** wählen Sie auf der linken Seite des Fensters **Framework**.</span><span class="sxs-lookup"><span data-stu-id="19280-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="19280-130">Suchen und auswählen **System.ServiceModel**, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="19280-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="19280-131">Speichern Sie die Projektmappe durch Auswahl **Datei** > **Alles speichern**.</span><span class="sxs-lookup"><span data-stu-id="19280-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="19280-132">Fügen Sie einen Dienstverweis auf den rechnerdienst hinzu:</span><span class="sxs-lookup"><span data-stu-id="19280-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="19280-133">In der **Projektmappen-Explorer** wählen Sie im Fenster der **Verweise** Ordner unter dem **"gettingstartedclient"** Projekt, und wählen Sie dann **Dienstverweis hinzufügen**  aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="19280-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="19280-134">In der **Hinzufügen eines Dienstverweises** wählen Sie im Fenster **Discover**.</span><span class="sxs-lookup"><span data-stu-id="19280-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="19280-135">Der CalculatorService-Dienst gestartet wird und die Visual Studio wird in der **Services** Feld.</span><span class="sxs-lookup"><span data-stu-id="19280-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="19280-136">Wählen Sie **CalculatorService** erweitern und die vom Dienst implementierten Dienstverträge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="19280-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="19280-137">Übernehmen Sie den Standardwert **Namespace** , und wählen Sie **OK**.</span><span class="sxs-lookup"><span data-stu-id="19280-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="19280-138">Visual Studio fügt ein neues Element mit dem **verbundene Dienste** Ordner in der **"gettingstartedclient"** Projekt.</span><span class="sxs-lookup"><span data-stu-id="19280-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 


### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="19280-139">ServiceModel Metadata Utility-tool</span><span class="sxs-lookup"><span data-stu-id="19280-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="19280-140">Die folgenden Beispiele zeigen, wie Sie optional die [ServiceModel Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) die Proxy-Klassendatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="19280-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="19280-141">Dieses Tool generiert die proxyklassendatei und *"App.config"* Datei.</span><span class="sxs-lookup"><span data-stu-id="19280-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="19280-142">Die folgenden Beispiele zeigen, wie Sie den Proxy in zu generieren C# und Visual Basic bzw.:</span><span class="sxs-lookup"><span data-stu-id="19280-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="19280-143">Clientkonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="19280-143">Client configuration file</span></span>

<span data-ttu-id="19280-144">Nachdem Sie den Client erstellt haben, erstellt Visual Studio die **"App.config"** Konfigurationsdatei in die **"gettingstartedclient"** -Projekt, das ähnlich wie im folgenden Beispiel werden soll:</span><span class="sxs-lookup"><span data-stu-id="19280-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="19280-145">Unter den [ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) Abschnitt der [ \<Endpunkt >](../configure-apps/file-schema/wcf/endpoint-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="19280-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="19280-146">Die **&lt;Endpunkt&gt;** -Element definiert den Endpunkt, den der Client verwendet wird, Zugriff auf den Dienst wie folgt:</span><span class="sxs-lookup"><span data-stu-id="19280-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>
- <span data-ttu-id="19280-147">Adresse: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="19280-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="19280-148">Die Adresse des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="19280-148">The address of the endpoint.</span></span>
- <span data-ttu-id="19280-149">Servicevertrag: `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="19280-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="19280-150">Die Dienstvertrag verarbeitet die Kommunikation zwischen dem WCF-Client und dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="19280-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="19280-151">Visual Studio generiert diesen Vertrag aus, wenn Sie verwendet die **Hinzufügen eines Dienstverweises** Funktion.</span><span class="sxs-lookup"><span data-stu-id="19280-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="19280-152">Es ist im Wesentlichen eine Kopie des Vertrags, die Sie im GettingStartedLib-Projekt definiert.</span><span class="sxs-lookup"><span data-stu-id="19280-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="19280-153">Bindung: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="19280-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="19280-154">Die Bindung gibt HTTP als Transport, interoperable Sicherheit und andere Einzelheiten der Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="19280-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19280-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="19280-155">Next steps</span></span>

<span data-ttu-id="19280-156">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="19280-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="19280-157">Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt für den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="19280-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="19280-158">Fügen Sie einen Dienstverweis auf den WCF-Dienst, um die Proxy-Klasse und die Konfigurationsdateien für die Clientanwendung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="19280-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="19280-159">Fahren Sie fort mit dem nächsten Tutorial erfahren, wie den generierten Client verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="19280-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="19280-160">Tutorial: Verwenden Sie einen WCF-client</span><span class="sxs-lookup"><span data-stu-id="19280-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)


