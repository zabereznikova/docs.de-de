---
title: "Exemplarische Vorgehensweise – zugreifen auf einen Webdienst mithilfe von Typanbietern (f#)"
description: "Erfahren Sie, wie mit der Web Services Description Language (WSDL) vom Typanbieter in f# 3.0 verfügbare WSDL-Dienst zuzugreifen."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 2929198172a4e9f908daa64af19208e07859263f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a><span data-ttu-id="faff7-104">Exemplarische Vorgehensweise: Zugreifen auf einen Webdienst mithilfe von Typanbietern</span><span class="sxs-lookup"><span data-stu-id="faff7-104">Walkthrough: Accessing a Web Service by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="faff7-105">Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="faff7-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="faff7-106">Unter [FSharp.Data](https://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.</span><span class="sxs-lookup"><span data-stu-id="faff7-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="faff7-107">Die API-Referenz Links gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="faff7-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="faff7-108">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="faff7-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="faff7-109">In dieser exemplarischen Vorgehensweise wird erläutert, wie der in F# 3.0 verfügbare WSDL-Typanbieter (Web Services Description Language) verwendet wird, um auf einen WSDL-Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="faff7-109">This walkthrough shows you how to use the Web Services Description Language (WSDL) type provider that is available in F# 3.0 to access a WSDL service.</span></span> <span data-ttu-id="faff7-110">In anderen .NET-Sprachen generieren Sie Code, um über einen Aufruf von svcutil.exe auf den Webdienst zuzugreifen, oder Sie fügen einen Webverweis hinzu, beispielsweise in einem C#-Projekt, bei dem von Visual Studio ebenfalls svcutil.exe aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="faff7-110">In other .NET languages, you generate the code to access the web service by calling svcutil.exe, or by adding a web reference in, for example, a C# project to get Visual Studio to call svcutil.exe for you.</span></span> <span data-ttu-id="faff7-111">In F# haben Sie zusätzlich die Option, den WSDL-Typanbieter zu verwenden, sodass in dem Moment, in dem Sie den Code zum Erstellen des WsdlService-Typs schreiben, die benötigten Typen generiert werden und zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="faff7-111">In F#, you have the additional option of using the WSDL type provider, so as soon as you write the code that creates the WsdlService type, the types are generated and become available.</span></span> <span data-ttu-id="faff7-112">Für diesen Prozess muss der Dienst verfügbar sein, während Sie den Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="faff7-112">This process relies on the service being available when you are writing the code.</span></span>

<span data-ttu-id="faff7-113">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="faff7-113">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="faff7-114">Sie müssen alle Aufgaben ausführen, um die exemplarische Vorgehensweise erfolgreich abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="faff7-114">You must complete them in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="faff7-115">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="faff7-115">Creating the project</span></span>
<br />

- <span data-ttu-id="faff7-116">Konfigurieren des Typanbieters</span><span class="sxs-lookup"><span data-stu-id="faff7-116">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="faff7-117">Den Webdienst aufrufen und die Ergebnisse verarbeiten</span><span class="sxs-lookup"><span data-stu-id="faff7-117">Calling the web service, and processing the results</span></span>
<br />


## <a name="creating-the-project"></a><span data-ttu-id="faff7-118">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="faff7-118">Creating the project</span></span>
<span data-ttu-id="faff7-119">In dem Schritt erstellen Sie ein Projekt und fügen die entsprechenden Verweise hinzu, um einen WSDL-Typanbieter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="faff7-119">In the step, you create a project and add the appropriate references to use a WSDL type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="faff7-120">So erstellen und richten Sie ein F#-Projekt ein</span><span class="sxs-lookup"><span data-stu-id="faff7-120">To create and set up an F# project</span></span>

1. <span data-ttu-id="faff7-121">Erstellen Sie ein neues F#-Konsolenanwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="faff7-121">Open a new F# Console Application project.</span></span>
<br />

2. <span data-ttu-id="faff7-122">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für des Projekts **Verweis** Knoten, und wählen Sie dann **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="faff7-122">In **Solution Explorer**, open the shortcut menu for the project's **Reference** node, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="faff7-123">In der **Assemblys** Bereich auswählen **Framework**, und wählen Sie dann in der Liste der verfügbaren Assemblys **System.Runtime.Serialization** und  **System.ServiceModel**.</span><span class="sxs-lookup"><span data-stu-id="faff7-123">In the **Assemblies** area, choose **Framework**, and then, in the list of available assemblies, choose **System.Runtime.Serialization** and **System.ServiceModel**.</span></span>
<br />

4. <span data-ttu-id="faff7-124">In der **Assemblys** Bereich auswählen **Erweiterungen**.</span><span class="sxs-lookup"><span data-stu-id="faff7-124">In the **Assemblies** area, choose **Extensions**.</span></span>
<br />

5. <span data-ttu-id="faff7-125">Wählen Sie in der Liste der verfügbaren Assemblys, **FSharp.Data.TypeProviders**, und wählen Sie dann die **OK** Schaltfläche, um Verweise auf diese Assemblys hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="faff7-125">In the list of available assemblies, choose **FSharp.Data.TypeProviders**, and then choose the **OK** button to add references to these assemblies.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="faff7-126">Konfigurieren des Typanbieters</span><span class="sxs-lookup"><span data-stu-id="faff7-126">Configuring the type provider</span></span>
<span data-ttu-id="faff7-127">In diesem Schritt verwenden Sie den WSDL-Typanbieter, um Typen für den TerraServer-Webdienst zu generieren.</span><span class="sxs-lookup"><span data-stu-id="faff7-127">In this step, you use the WSDL type provider to generate types for the TerraServer web service.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="faff7-128">So konfigurieren Sie den Typanbieter und generieren Typen</span><span class="sxs-lookup"><span data-stu-id="faff7-128">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="faff7-129">Fügen Sie die folgende Codezeile hinzu, um den Typanbieternamespace zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="faff7-129">Add the following line of code to open the type provider namespace.</span></span>
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. <span data-ttu-id="faff7-130">Fügen Sie die folgende Codezeile hinzu, um den Typanbieter mit einem Webdienst aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="faff7-130">Add the following line of code to invoke the type provider with a web service.</span></span> <span data-ttu-id="faff7-131">In diesem Beispiel wird der TerraServer-Webdienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="faff7-131">In this example, use the TerraServer web service.</span></span>
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "https://terraserver-usa.com/TerraService2.asmx?WSDL" https://msrmaps.com/TerraService2.asmx?WSDL">
```

  <span data-ttu-id="faff7-132">Wenn der Dienst-URI falsch geschrieben oder der Dienst deaktiviert bzw. nicht erreichbar ist, wird unter dieser Codezeile eine rote Wellenlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="faff7-132">A red squiggle appears under this line of code if the service URI is misspelled or if the service itself is down or isn’t performing.</span></span> <span data-ttu-id="faff7-133">Wenn Sie auf den Code zeigen, beschreibt eine Fehlermeldung das Problem.</span><span class="sxs-lookup"><span data-stu-id="faff7-133">If you point to the code, an error message describes the problem.</span></span> <span data-ttu-id="faff7-134">Sie finden die gleiche Informationen in der **Fehlerliste** Fenster oder in der **Fenster "Ausgabe"** Nachdem Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="faff7-134">You can find the same information in the **Error List** window or in the **Output Window** after you build.</span></span>
<br />  <span data-ttu-id="faff7-135">Es gibt zwei Möglichkeiten, Konfigurationseinstellungen für eine WSDL-Verbindung anzugeben: Entweder durch Verwendung der Datei app.config des Projekts oder durch Verwendung der statischen Typparameter in der Typanbieterdeklaration.</span><span class="sxs-lookup"><span data-stu-id="faff7-135">There are two ways to specify configuration settings for a WSDL connection, by using the app.config file for the project, or by using the static type parameters in the type provider declaration.</span></span> <span data-ttu-id="faff7-136">Sie können svcutil.exe verwenden, um entsprechende Konfigurationsdateielemente zu generieren.</span><span class="sxs-lookup"><span data-stu-id="faff7-136">You can use svcutil.exe to generate appropriate configuration file elements.</span></span> <span data-ttu-id="faff7-137">Weitere Informationen zur Verwendung von svcutil.exe zum Generieren von Konfigurationsinformationen für einen Webdienst finden Sie unter [ServiceModel Metadata Utility Tool &#40; Svcutil.exe &#41; ](https://msdn.microsoft.com/library/aa347733.aspx).</span><span class="sxs-lookup"><span data-stu-id="faff7-137">For more information about using svcutil.exe to generate configuration information for a web service, see [ServiceModel Metadata Utility Tool &#40;Svcutil.exe&#41;](https://msdn.microsoft.com/library/aa347733.aspx).</span></span> <span data-ttu-id="faff7-138">Eine vollständige Beschreibung der statischen Typparameter für den WSDL-Typanbieter, finden Sie unter [WsdlService-Typanbieter](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="faff7-138">For a full description of the static type parameters for the WSDL type provider, see [WsdlService Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span></span>
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a><span data-ttu-id="faff7-139">Den Webdienst aufrufen und die Ergebnisse verarbeiten</span><span class="sxs-lookup"><span data-stu-id="faff7-139">Calling the web service, and processing the results</span></span>
<span data-ttu-id="faff7-140">Jeder Webdienst verfügt über eine eigene Gruppe von Typen, die als Parameter für die Methodenaufrufe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="faff7-140">Each web service has its own set of types that are used as parameters for its method calls.</span></span> <span data-ttu-id="faff7-141">In diesem Schritt bereiten Sie diese Parameter vor, rufen eine Webmethode auf und verarbeiten die von der Methode zurückgegebenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="faff7-141">In this step, you prepare these parameters, call a web method, and process the information that it returns.</span></span>


#### <a name="to-call-the-web-service-and-process-the-results"></a><span data-ttu-id="faff7-142">So rufen Sie den Webdienst auf und verarbeiten die Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="faff7-142">To call the web service, and process the results</span></span>

1. <span data-ttu-id="faff7-143">Da es vorkommen kann, dass beim Webdienst ein Timeout auftritt oder der Dienst ausfällt, sollte der Aufruf des Webdiensts in einen Ausnahmebehandlungsblock eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="faff7-143">The web service might time out or stop functioning, so you should include the web service call in an exception handling block.</span></span> <span data-ttu-id="faff7-144">Fügen Sie den folgenden Code ein, mit dem versucht wird, Daten von einem Webdienst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="faff7-144">Write the following code to try to get data from the web service.</span></span>
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

<span data-ttu-id="faff7-145">Beachten Sie, dass die Datentypen zu erstellen, die für den Webdienst, z. B. erforderlich sind **Stelle** und **Speicherort**, wie geschachtelte Typen unter dem WsdlService-Typs **TerraService**.</span><span class="sxs-lookup"><span data-stu-id="faff7-145">Notice that you create the data types that are needed for the web service, such as **Place** and **Location**, as nested types under the WsdlService type **TerraService**.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="faff7-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="faff7-146">See Also</span></span>
[<span data-ttu-id="faff7-147">WsdlService-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="faff7-147">WsdlService Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[<span data-ttu-id="faff7-148">Typanbieter</span><span class="sxs-lookup"><span data-stu-id="faff7-148">Type Providers</span></span>](index.md)
