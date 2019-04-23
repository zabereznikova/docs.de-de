---
title: 'Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: b6f010cb5edc3111f05c78f5d27cf178bd501ef9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326423"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="c0e51-102">Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="c0e51-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>
<span data-ttu-id="c0e51-103">Dienste und Clientanwendungen, die Datentypen verwenden, die mit dem <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können, generieren und kompilieren für diese Datentypen während der Laufzeit Code, was zu einem verlangsamten Start führen kann.</span><span class="sxs-lookup"><span data-stu-id="c0e51-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0e51-104">Vorab generierter Serialisierungscode kann nur in Clientanwendungen verwendet werden und nicht in Diensten.</span><span class="sxs-lookup"><span data-stu-id="c0e51-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="c0e51-105">Die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) können startleistung für diese Anwendungen verbessern, indem der erforderliche Serialisierungscode aus den kompilierten Assemblys für die Anwendung generiert.</span><span class="sxs-lookup"><span data-stu-id="c0e51-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="c0e51-106">Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="c0e51-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="c0e51-107">Dienst- und Vorgangsverträge, die <xref:System.Xml.Serialization.XmlSerializer> verwenden, werden mit <xref:System.ServiceModel.XmlSerializerFormatAttribute> gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c0e51-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="c0e51-108">So generieren Sie XmlSerializer-Serialisierungscode</span><span class="sxs-lookup"><span data-stu-id="c0e51-108">To generate XmlSerializer serialization code</span></span>  
  
1. <span data-ttu-id="c0e51-109">Kompilieren Sie den Dienst- oder Clientcode in eine oder mehrere Assemblys.</span><span class="sxs-lookup"><span data-stu-id="c0e51-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2. <span data-ttu-id="c0e51-110">Öffnen Sie eine SDK-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="c0e51-110">Open an SDK command prompt.</span></span>  
  
3. <span data-ttu-id="c0e51-111">Starten Sie das Tool Svcutil.exe an der Eingabeaufforderung mit dem folgenden Format.</span><span class="sxs-lookup"><span data-stu-id="c0e51-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="c0e51-112">Das `assemblyPath`-Argument gibt den Pfad zu einer Assembly an, die Dienstvertragstypen enthält.</span><span class="sxs-lookup"><span data-stu-id="c0e51-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="c0e51-113">Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="c0e51-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="c0e51-114">Svcutil.exe kann lediglich C#-Serialisierungscode generieren.</span><span class="sxs-lookup"><span data-stu-id="c0e51-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="c0e51-115">Für jede Eingabeassembly wird eine Quellcodedatei generiert.</span><span class="sxs-lookup"><span data-stu-id="c0e51-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="c0e51-116">Sie können keine der **/Language** Switch so ändern Sie die Sprache des generierten Codes.</span><span class="sxs-lookup"><span data-stu-id="c0e51-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="c0e51-117">Um den Pfad für abhängige Assemblys anzugeben, verwenden die **/reference** Option.</span><span class="sxs-lookup"><span data-stu-id="c0e51-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4. <span data-ttu-id="c0e51-118">Machen Sie den generierten Serialisierungscode für Ihre Anwendung verfügbar, indem Sie eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="c0e51-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1.  <span data-ttu-id="c0e51-119">Kompilieren Sie den generierten Serialisierungscode in einer separaten Assembly mit dem Namen [*ursprüngliche Assembly*]. XmlSerializers.dll (z. B. MyApp.XmlSerializers.dll).</span><span class="sxs-lookup"><span data-stu-id="c0e51-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="c0e51-120">Ihre Anwendung muss die Assembly laden können. Diese wiederum muss mit demselben Schlüssel wie die ursprüngliche Assembly signiert werden.</span><span class="sxs-lookup"><span data-stu-id="c0e51-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="c0e51-121">Falls Sie die ursprüngliche Assembly neu kompilieren, müssen Sie die Serialisierungsassembly neu generieren.</span><span class="sxs-lookup"><span data-stu-id="c0e51-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2.  <span data-ttu-id="c0e51-122">Kompilieren Sie den generierten Serialisierungscode in eine separate Assembly, und verwenden Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> in dem Dienstvertrag, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0e51-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="c0e51-123">Legen Sie die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>-Eigenschaft oder die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>-Eigenschaft so fest, dass sie auf die kompilierte Serialisierungsassembly verweist.</span><span class="sxs-lookup"><span data-stu-id="c0e51-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3.  <span data-ttu-id="c0e51-124">Kompilieren Sie den generierten Serialisierungscode in Ihre Anwendungsassembly, und fügen Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> dem Dienstvertrag hinzu, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0e51-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="c0e51-125">Die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>-Eigenschaft und die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>-Eigenschaft müssen nicht festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c0e51-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="c0e51-126">Es wird davon ausgegangen, dass die Standardserialisierungsassembly die aktuelle Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="c0e51-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="c0e51-127">Zum Generieren von XmlSerializer-Serialisierungscode in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c0e51-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1. <span data-ttu-id="c0e51-128">Erstellen Sie den WCF-Dienst und Client Projekte in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c0e51-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="c0e51-129">Anschließend fügen Sie einen Dienstverweis auf das Clientprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="c0e51-129">Then, add a service reference to the client project.</span></span>  
  
2. <span data-ttu-id="c0e51-130">Hinzufügen einer <xref:System.ServiceModel.XmlSerializerFormatAttribute> auf den Dienstvertrag in der *reference.cs* -Datei in das Client-app-Projekt unter **ServiceReference** -> **"Reference.SVCMAP"** .</span><span class="sxs-lookup"><span data-stu-id="c0e51-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="c0e51-131">Beachten Sie, dass Sie alle Dateien in anzeigen müssen **Projektmappen-Explorer** auf diese Dateien finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c0e51-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3. <span data-ttu-id="c0e51-132">Erstellen Sie die Client-app.</span><span class="sxs-lookup"><span data-stu-id="c0e51-132">Build the client app.</span></span>  
  
4. <span data-ttu-id="c0e51-133">Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erstellen einer vorab generierte Serialisierungsmodul *cs* Datei mithilfe des Befehls:</span><span class="sxs-lookup"><span data-stu-id="c0e51-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="c0e51-134">Das AssemblyPath-Argument gibt den Pfad zu die WCF-Clientassembly.</span><span class="sxs-lookup"><span data-stu-id="c0e51-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="c0e51-135">Z. B.:</span><span class="sxs-lookup"><span data-stu-id="c0e51-135">Such as:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="c0e51-136">Die *WCFClient.XmlSerializers.dll.cs* Datei generiert werden.</span><span class="sxs-lookup"><span data-stu-id="c0e51-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5. <span data-ttu-id="c0e51-137">Kompilieren Sie die vorab generierte Serialisierungsassembly.</span><span class="sxs-lookup"><span data-stu-id="c0e51-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="c0e51-138">Basierend auf dem Beispiel im vorherigen Schritt, würde der Compile-Befehl kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="c0e51-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="c0e51-139">Stellen Sie sicher, dass die generierte *WCFClient.XmlSerializers.dll* befindet sich im gleichen Verzeichnis wie die Client-app, d.h. *WCFClient.exe* in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="c0e51-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6. <span data-ttu-id="c0e51-140">Führen Sie die Client-app wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="c0e51-140">Run the client app as usual.</span></span> <span data-ttu-id="c0e51-141">Der vorgenerierten Serialisierungsassembly wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0e51-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0e51-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0e51-142">Example</span></span>  
 <span data-ttu-id="c0e51-143">Der folgende Befehl generiert Serialisierungstypen für `XmlSerializer`-Typen, die von Dienstverträgen in der Assembly verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0e51-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0e51-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0e51-144">See also</span></span>

- [<span data-ttu-id="c0e51-145">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="c0e51-145">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
