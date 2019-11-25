---
title: 'Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: ca15d710a30586135f0d030e155b09b63a22ee45
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976063"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="87105-102">Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="87105-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>
<span data-ttu-id="87105-103">Dienste und Clientanwendungen, die Datentypen verwenden, die mit dem <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können, generieren und kompilieren für diese Datentypen während der Laufzeit Code, was zu einem verlangsamten Start führen kann.</span><span class="sxs-lookup"><span data-stu-id="87105-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87105-104">Vorab generierter Serialisierungscode kann nur in Clientanwendungen verwendet werden und nicht in Diensten.</span><span class="sxs-lookup"><span data-stu-id="87105-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="87105-105">Das [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) kann die Startleistung für diese Anwendungen verbessern, indem der erforderliche Serialisierungscode aus den kompilierten Assemblys für die Anwendung erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="87105-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="87105-106">Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="87105-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="87105-107">Dienst- und Vorgangsverträge, die <xref:System.Xml.Serialization.XmlSerializer> verwenden, werden mit <xref:System.ServiceModel.XmlSerializerFormatAttribute> gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="87105-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="87105-108">So generieren Sie XmlSerializer-Serialisierungscode</span><span class="sxs-lookup"><span data-stu-id="87105-108">To generate XmlSerializer serialization code</span></span>  
  
1. <span data-ttu-id="87105-109">Kompilieren Sie den Dienst- oder Clientcode in eine oder mehrere Assemblys.</span><span class="sxs-lookup"><span data-stu-id="87105-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2. <span data-ttu-id="87105-110">Öffnen Sie eine SDK-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="87105-110">Open an SDK command prompt.</span></span>  
  
3. <span data-ttu-id="87105-111">Starten Sie das Tool Svcutil.exe an der Eingabeaufforderung mit dem folgenden Format.</span><span class="sxs-lookup"><span data-stu-id="87105-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="87105-112">Das `assemblyPath`-Argument gibt den Pfad zu einer Assembly an, die Dienstvertragstypen enthält.</span><span class="sxs-lookup"><span data-stu-id="87105-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="87105-113">Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="87105-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="87105-114">Svcutil.exe kann lediglich C#-Serialisierungscode generieren.</span><span class="sxs-lookup"><span data-stu-id="87105-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="87105-115">Für jede Eingabeassembly wird eine Quellcodedatei generiert.</span><span class="sxs-lookup"><span data-stu-id="87105-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="87105-116">Sie können den Schalter **/Language** nicht verwenden, um die Sprache des generierten Codes zu ändern.</span><span class="sxs-lookup"><span data-stu-id="87105-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="87105-117">Verwenden Sie die **/Reference** -Option, um den Pfad zu abhängigen Assemblys anzugeben.</span><span class="sxs-lookup"><span data-stu-id="87105-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4. <span data-ttu-id="87105-118">Machen Sie den generierten Serialisierungscode für Ihre Anwendung verfügbar, indem Sie eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="87105-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1. <span data-ttu-id="87105-119">Kompilieren Sie den generierten Serialisierungscode in eine separate Assembly mit dem Namen [*ursprüngliche Assembly*]. Xmlserializers. dll (z. b. MyApp. xmlserializers. dll).</span><span class="sxs-lookup"><span data-stu-id="87105-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="87105-120">Ihre Anwendung muss die Assembly laden können. Diese wiederum muss mit demselben Schlüssel wie die ursprüngliche Assembly signiert werden.</span><span class="sxs-lookup"><span data-stu-id="87105-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="87105-121">Falls Sie die ursprüngliche Assembly neu kompilieren, müssen Sie die Serialisierungsassembly neu generieren.</span><span class="sxs-lookup"><span data-stu-id="87105-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2. <span data-ttu-id="87105-122">Kompilieren Sie den generierten Serialisierungscode in eine separate Assembly, und verwenden Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> in dem Dienstvertrag, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet.</span><span class="sxs-lookup"><span data-stu-id="87105-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="87105-123">Legen Sie die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>-Eigenschaft oder die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>-Eigenschaft so fest, dass sie auf die kompilierte Serialisierungsassembly verweist.</span><span class="sxs-lookup"><span data-stu-id="87105-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3. <span data-ttu-id="87105-124">Kompilieren Sie den generierten Serialisierungscode in Ihre Anwendungsassembly, und fügen Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> dem Dienstvertrag hinzu, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet.</span><span class="sxs-lookup"><span data-stu-id="87105-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="87105-125">Die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>-Eigenschaft und die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>-Eigenschaft müssen nicht festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="87105-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="87105-126">Es wird davon ausgegangen, dass die Standardserialisierungsassembly die aktuelle Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="87105-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="87105-127">So generieren Sie XmlSerializer-Serialisierungscode in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="87105-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1. <span data-ttu-id="87105-128">Erstellen Sie den WCF-Dienst und die Client Projekte in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="87105-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="87105-129">Fügen Sie dann dem Client Projekt einen Dienst Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="87105-129">Then, add a service reference to the client project.</span></span>  
  
2. <span data-ttu-id="87105-130">Fügen Sie dem Dienstvertrag in der *Reference.cs* -Datei im Client-App-Projekt unter \*\*servicereferen -> \*\* **Reference. svcmap**eine <xref:System.ServiceModel.XmlSerializerFormatAttribute> hinzu.</span><span class="sxs-lookup"><span data-stu-id="87105-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="87105-131">Beachten Sie, dass Sie alle Dateien in **Projektmappen-Explorer** anzeigen müssen, um diese Dateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="87105-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3. <span data-ttu-id="87105-132">Erstellen Sie die Client-App.</span><span class="sxs-lookup"><span data-stu-id="87105-132">Build the client app.</span></span>  
  
4. <span data-ttu-id="87105-133">Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , um mithilfe des Befehls eine vorab generierte Datei Serialisierungsprogramm *. cs* zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="87105-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="87105-134">Das assemblyPath-Argument gibt den Pfad zur WCF-Clientassembly an.</span><span class="sxs-lookup"><span data-stu-id="87105-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="87105-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="87105-135">Such as:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="87105-136">Die *wcfClient.xmlserializers.dll.cs* -Datei wird generiert.</span><span class="sxs-lookup"><span data-stu-id="87105-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5. <span data-ttu-id="87105-137">Kompilieren Sie die vorgenerierte Serialisierungsassembly.</span><span class="sxs-lookup"><span data-stu-id="87105-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="87105-138">Basierend auf dem Beispiel im vorherigen Schritt würde der Kompilierungs Befehl folgendermaßen lauten:</span><span class="sxs-lookup"><span data-stu-id="87105-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```console  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="87105-139">Stellen Sie sicher, dass sich die generierte Datei " *wcfClient. xmlserializers. dll* " im gleichen Verzeichnis wie die Client-App befindet, in diesem Fall " *wcfClient. exe* ".</span><span class="sxs-lookup"><span data-stu-id="87105-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6. <span data-ttu-id="87105-140">Führen Sie die Client-App wie gewohnt aus.</span><span class="sxs-lookup"><span data-stu-id="87105-140">Run the client app as usual.</span></span> <span data-ttu-id="87105-141">Die vorgenerierte Serialisierungsassembly wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="87105-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87105-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87105-142">Example</span></span>  
 <span data-ttu-id="87105-143">Der folgende Befehl generiert Serialisierungstypen für `XmlSerializer`-Typen, die von Dienstverträgen in der Assembly verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87105-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```console  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="87105-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87105-144">See also</span></span>

- [<span data-ttu-id="87105-145">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="87105-145">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
