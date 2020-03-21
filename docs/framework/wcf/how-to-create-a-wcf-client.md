---
title: 'Tutorial: Erstellen eines Windows Communication Foundation-Clients'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184102"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="11c22-102">Tutorial: Erstellen eines Windows Communication Foundation-Clients</span><span class="sxs-lookup"><span data-stu-id="11c22-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="11c22-103">In diesem Tutorial wird die vierte von fünf Aufgaben beschrieben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="11c22-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="11c22-104">Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="11c22-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="11c22-105">Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht darin, einen Client zu erstellen, indem Metadaten von einem WCF-Dienst abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="11c22-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="11c22-106">Sie verwenden Visual Studio, um einen Dienstverweis hinzuzufügen, der die Metadaten vom MEX-Endpunkt des Diensts abruft.</span><span class="sxs-lookup"><span data-stu-id="11c22-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="11c22-107">Visual Studio generiert dann eine verwaltete Quellcodedatei für einen Clientproxy in der von Ihnen gewählten Sprache.</span><span class="sxs-lookup"><span data-stu-id="11c22-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="11c22-108">Außerdem wird eine Clientkonfigurationsdatei (*App.config*) erstellt.</span><span class="sxs-lookup"><span data-stu-id="11c22-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="11c22-109">Diese Datei ermöglicht es der Clientanwendung, eine Verbindung mit dem Dienst an einem Endpunkt herzustellen.</span><span class="sxs-lookup"><span data-stu-id="11c22-109">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="11c22-110">Wenn Sie einen WCF-Dienst aus einem Klassenbibliotheksprojekt in Visual Studio aufrufen, verwenden Sie die Funktion **Dienstreferenz hinzufügen,** um automatisch einen Proxy und eine zugehörige Konfigurationsdatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="11c22-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="11c22-111">Da Klassenbibliotheksprojekte diese Konfigurationsdatei jedoch nicht verwenden, müssen Sie die Einstellungen in der generierten Konfigurationsdatei der *Datei App.config* für die ausführbare Datei hinzufügen, die die Klassenbibliothek aufruft.</span><span class="sxs-lookup"><span data-stu-id="11c22-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="11c22-112">Alternativ können Sie das [ServiceModel-Metadaten-Dienstprogramm](#servicemodel-metadata-utility-tool) anstelle von Visual Studio verwenden, um die Proxyklasse und Konfigurationsdatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="11c22-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="11c22-113">Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="11c22-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="11c22-114">Dieses Verfahren wird in [Tutorial beschrieben: Verwenden eines Clients](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="11c22-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="11c22-115">In diesem Tutorial lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="11c22-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="11c22-116">Erstellen und konfigurieren Sie ein Konsolen-App-Projekt für den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="11c22-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="11c22-117">Fügen Sie dem WCF-Dienst einen Dienstverweis hinzu, um die Proxyklasse und die Konfigurationsdateien zu generieren.</span><span class="sxs-lookup"><span data-stu-id="11c22-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="11c22-118">Erstellen eines Windows Communication Foundation-Clients</span><span class="sxs-lookup"><span data-stu-id="11c22-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="11c22-119">Erstellen eines Konsolen-App-Projekts in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="11c22-119">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="11c22-120">Wählen Sie im Menü **Datei** die Option**Projekt/Projektmappe** **öffnen** > aus, und navigieren Sie zur **Lösung "Erste Schritte",** die Sie zuvor erstellt haben (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="11c22-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="11c22-121">Wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="11c22-121">Select **Open**.</span></span>

    2. <span data-ttu-id="11c22-122">Wählen Sie im Menü **Ansicht** **den Projektmappen-Explorer**aus.</span><span class="sxs-lookup"><span data-stu-id="11c22-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="11c22-123">Wählen Sie im **Projektmappen-Explorer** die **Lösung "Erste Schritte"** (oberster Knoten) und dann im Kontextmenü **"Neues Projekt hinzufügen"** **aus.** > </span><span class="sxs-lookup"><span data-stu-id="11c22-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="11c22-124">Wählen Sie im Fenster **Neues Projekt hinzufügen** auf der linken Seite die Windows **Desktop-Kategorie** unter Visual **C oder** Visual **Basic**aus.</span><span class="sxs-lookup"><span data-stu-id="11c22-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="11c22-125">Wählen Sie die Vorlage **"Konsolen-App" (.NET Framework)** aus, und geben Sie *GettingStartedClient* für den **Namen ein.**</span><span class="sxs-lookup"><span data-stu-id="11c22-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="11c22-126">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="11c22-126">Select **OK**.</span></span>

2. <span data-ttu-id="11c22-127">Fügen Sie der <xref:System.ServiceModel> Assembly einen Verweis im **GettingStartedClient-Projekt** hinzu:</span><span class="sxs-lookup"><span data-stu-id="11c22-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="11c22-128">Wählen Sie im **Projektmappen-Explorer** den Ordner **Referenzen** unter dem **GettingStartedClient-Projekt** aus, und wählen Sie dann im Kontextmenü **Referenz hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="11c22-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="11c22-129">Wählen Sie im Fenster **Referenz hinzufügen** unter **Baugruppen** auf der linken Seite des Fensters **Framework**aus.</span><span class="sxs-lookup"><span data-stu-id="11c22-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="11c22-130">Suchen und wählen Sie **System.ServiceModel**aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="11c22-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="11c22-131">Speichern Sie die Lösung, indem Sie **Datei** > **speichern alle**auswählen.</span><span class="sxs-lookup"><span data-stu-id="11c22-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="11c22-132">Hinzufügen einer Dienstreferenz zum Rechnerdienst:</span><span class="sxs-lookup"><span data-stu-id="11c22-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="11c22-133">Wählen Sie im **Projektmappen-Explorer** den Ordner **Referenzen** unter dem **GettingStartedClient-Projekt** aus, und wählen Sie dann im Kontextmenü **Dienstreferenz hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="11c22-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="11c22-134">Wählen Sie im Fenster **Dienstreferenz hinzufügen** die Option **Ermitteln**aus.</span><span class="sxs-lookup"><span data-stu-id="11c22-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="11c22-135">Der CalculatorService-Dienst wird gestartet, und Visual Studio zeigt ihn im Feld **Dienste** an.</span><span class="sxs-lookup"><span data-stu-id="11c22-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="11c22-136">Wählen Sie **CalculatorService** aus, um ihn zu erweitern und die vom Dienst implementierten Serviceverträge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="11c22-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="11c22-137">Verlassen Sie den **Standardnamespace** und wählen Sie **OK**.</span><span class="sxs-lookup"><span data-stu-id="11c22-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="11c22-138">Visual Studio fügt im **GettingStartedClient-Projekt** ein neues Element unter dem Ordner **Verbundene Dienste** hinzu.</span><span class="sxs-lookup"><span data-stu-id="11c22-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="11c22-139">ServiceModel Metadata Utility-Tool</span><span class="sxs-lookup"><span data-stu-id="11c22-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="11c22-140">Die folgenden Beispiele zeigen, wie Sie optional das [ServiceModel Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden, um die Proxyklassendatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="11c22-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="11c22-141">Dieses Tool generiert die Proxyklassendatei und die *Datei App.config.*</span><span class="sxs-lookup"><span data-stu-id="11c22-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="11c22-142">Die folgenden Beispiele zeigen, wie Sie den Proxy in C- bzw. Visual Basic generieren:</span><span class="sxs-lookup"><span data-stu-id="11c22-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="11c22-143">Clientkonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="11c22-143">Client configuration file</span></span>

<span data-ttu-id="11c22-144">Nachdem Sie den Client erstellt haben, erstellt Visual Studio die **App.config-Konfigurationsdatei** im **GettingStartedClient-Projekt,** die dem folgenden Beispiel ähnlich sein sollte:</span><span class="sxs-lookup"><span data-stu-id="11c22-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="11c22-145">Beachten Sie im [ \<Abschnitt system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) den [ \<Endpunkt>-Element.](../configure-apps/file-schema/wcf/endpoint-element.md)</span><span class="sxs-lookup"><span data-stu-id="11c22-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="11c22-146">Das \*\* &lt;Endpunktelement&gt; \*\* definiert den Endpunkt, den der Client für den Zugriff auf den Dienst verwendet, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="11c22-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="11c22-147">Adresse: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="11c22-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="11c22-148">Die Adresse des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="11c22-148">The address of the endpoint.</span></span>
- <span data-ttu-id="11c22-149">Servicevertrag: `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="11c22-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="11c22-150">Der Servicevertrag verarbeitet die Kommunikation zwischen dem WCF-Client und dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="11c22-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="11c22-151">Visual Studio hat diesen Vertrag generiert, als Sie die Funktion **Dienstreferenz hinzufügen** verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="11c22-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="11c22-152">Es handelt sich im Wesentlichen um eine Kopie des Vertrags, den Sie im GettingStartedLib-Projekt definiert haben.</span><span class="sxs-lookup"><span data-stu-id="11c22-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="11c22-153">Bindung: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="11c22-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="11c22-154">Die Bindung gibt HTTP als Transport, interoperable Sicherheit und andere Konfigurationsdetails an.</span><span class="sxs-lookup"><span data-stu-id="11c22-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="11c22-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="11c22-155">Next steps</span></span>

<span data-ttu-id="11c22-156">In diesem Tutorial haben Sie Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="11c22-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="11c22-157">Erstellen und konfigurieren Sie ein Konsolen-App-Projekt für den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="11c22-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="11c22-158">Fügen Sie dem WCF-Dienst einen Dienstverweis hinzu, um die Proxyklasse und die Konfigurationsdateien für die Clientanwendung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="11c22-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="11c22-159">Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den generierten Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="11c22-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="11c22-160">Tutorial: Verwenden eines WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="11c22-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
