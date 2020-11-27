---
title: 'Vorgehensweise: Verwenden von „Svcutil.exe“ zum Herunterladen von Metadatendokumenten'
description: Erfahren Sie, wie Sie mit Svcutil.exe Metadaten aus laufenden Diensten herunterladen und die Metadaten in lokalen Dateien speichern.
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 449dd3023b5d688ed0de22e3651cccf16bee0c52
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280675"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a><span data-ttu-id="3da0a-103">Vorgehensweise: Verwenden von „Svcutil.exe“ zum Herunterladen von Metadatendokumenten</span><span class="sxs-lookup"><span data-stu-id="3da0a-103">How to: Use Svcutil.exe to Download Metadata Documents</span></span>

<span data-ttu-id="3da0a-104">Svcutil.exe kann verwendet werden, um Metadaten aus ausgeführten Diensten herunterzuladen und die Metadaten in lokalen Dateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3da0a-104">You can use Svcutil.exe to download metadata from running services and to save the metadata to local files.</span></span> <span data-ttu-id="3da0a-105">Bei http-und HTTPS-URL-Schemas versucht Svcutil.exe, Metadaten mithilfe WS-MetadataExchange und der [XML-Webdienst](/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100))Ermittlung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3da0a-105">For HTTP and HTTPS URL schemes, Svcutil.exe attempts to retrieve metadata using WS-MetadataExchange and [XML Web Service Discovery](/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)).</span></span> <span data-ttu-id="3da0a-106">Bei allen anderen URL-Schemas verwendet Svcutil.exe nur WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="3da0a-106">For all other URL schemes, Svcutil.exe uses only WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="3da0a-107">Standardmäßig verwendet Svcutil.exe die in der <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse definierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="3da0a-107">By default, Svcutil.exe uses the bindings defined in the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class.</span></span> <span data-ttu-id="3da0a-108">Wenn Sie die für WS-MetadataExchange verwendete Bindung konfigurieren möchten, müssen Sie einen Clientendpunkt in der Konfigurationsdatei für „Svcutil.exe“ (svcutil.exe.config) definieren, der den `IMetadataExchange`-Vertrag verwendet und über dasselbe URI-Schema der Metadaten-Endpunktadresse verfügt.</span><span class="sxs-lookup"><span data-stu-id="3da0a-108">To configure the binding used for WS-MetadataExchange, you must define a client endpoint in the configuration file for Svcutil.exe (svcutil.exe.config) that uses the `IMetadataExchange` contract and that has the same name as the Uniform Resource Identifier (URI) scheme of the metadata endpoint address.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="3da0a-109">Beim Ausführen Svcutil.exe zum Abrufen von Metadaten für einen Dienst, der zwei verschiedene Dienstverträge verfügbar macht, die jeweils einen gleichnamigen Vorgang enthalten, zeigt Svcutil.exe einen Fehler an, der besagt, dass keine Metadaten von... abgerufen werden können. Wenn Sie z. b. über einen Dienst verfügen, der einen Dienstvertrag mit dem Namen verfügbar macht `ICarService` , der über einen-Vorgang verfügt `Get(Car c)` und der gleiche Dienst einen Dienstvertrag namens mit einem-Vorgang bereitstellt `IBookService` `Get(Book b)` .</span><span class="sxs-lookup"><span data-stu-id="3da0a-109">When running Svcutil.exe to get metadata for a service that exposes two different service contracts that each contain an operation of the same name, Svcutil.exe displays an error saying, "Cannot obtain Metadata from ...." For example, if you have a service that exposes a service contract called `ICarService` that has an operation `Get(Car c)` and the same service exposes a service contract called `IBookService` that has an operation `Get(Book b)`.</span></span> <span data-ttu-id="3da0a-110">Führen Sie einen der folgenden Schritte aus, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="3da0a-110">To work around this issue, do one of the following:</span></span>
>
> - <span data-ttu-id="3da0a-111">Benennen Sie eine der Operationen um.</span><span class="sxs-lookup"><span data-stu-id="3da0a-111">Rename one of the operations.</span></span>
> - <span data-ttu-id="3da0a-112">Legen Sie die <xref:System.ServiceModel.OperationContractAttribute.Name%2A>-Eigenschaft auf einen anderen Namen fest.</span><span class="sxs-lookup"><span data-stu-id="3da0a-112">Set the <xref:System.ServiceModel.OperationContractAttribute.Name%2A> to a different name.</span></span>
> - <span data-ttu-id="3da0a-113">Legen Sie einen der Namespaces der Operation mit der <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft auf einen anderen Namespace fest.</span><span class="sxs-lookup"><span data-stu-id="3da0a-113">Set one of the operations' namespaces to a different namespace using the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>
  
## <a name="to-download-metadata-using-svcutilexe"></a><span data-ttu-id="3da0a-114">So laden Sie Metadaten mit Svcutil.exe herunter</span><span class="sxs-lookup"><span data-stu-id="3da0a-114">To download metadata using Svcutil.exe</span></span>  
  
1. <span data-ttu-id="3da0a-115">Suchen Sie das Tool Svcutil.exe am folgenden Speicherort:</span><span class="sxs-lookup"><span data-stu-id="3da0a-115">Locate the Svcutil.exe tool at the following location:</span></span>  
  
     <span data-ttu-id="3da0a-116">C:\Programme\Microsoft SDKs\Windows\v1.0.\bin</span><span class="sxs-lookup"><span data-stu-id="3da0a-116">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span></span>  
  
2. <span data-ttu-id="3da0a-117">Starten Sie das Tool an der Eingabeaufforderung mit dem folgenden Format.</span><span class="sxs-lookup"><span data-stu-id="3da0a-117">At the command prompt, launch the tool using the following format.</span></span>  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     <span data-ttu-id="3da0a-118">Um Metadaten herunterzuladen, müssen Sie die `/t:metadata`-Option angeben.</span><span class="sxs-lookup"><span data-stu-id="3da0a-118">You must specify the `/t:metadata` option to download metadata.</span></span> <span data-ttu-id="3da0a-119">Andernfalls werden Clientcode und -konfiguration generiert.</span><span class="sxs-lookup"><span data-stu-id="3da0a-119">Otherwise, client code and configuration are generated.</span></span>  
  
3. <span data-ttu-id="3da0a-120">Das <`url`>-Argument gibt die URL zu einem Dienst Endpunkt an, der Metadaten bereitstellt, oder ein Metadatendokument, das online gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3da0a-120">The <`url`>argument specifies the URL to a service endpoint that provides metadata or to a metadata document hosted online.</span></span> <span data-ttu-id="3da0a-121">Das <`epr`>-Argument gibt den Pfad zu einer XML-Datei an, die eine WS-Addressing `EndpointAddress` für einen Dienst Endpunkt enthält, der WS-MetadataExchange unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3da0a-121">The <`epr`> argument specifies the path to an XML file that contains a WS-Addressing `EndpointAddress` for a service endpoint that supports WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="3da0a-122">Weitere Optionen zur Verwendung dieses Tools für das Herunterladen von Metadaten finden Sie unter [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3da0a-122">For more options about using this tool for metadata download, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3da0a-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3da0a-123">Example</span></span>  

 <span data-ttu-id="3da0a-124">Der folgende Befehl lädt Metadatendokumente aus einem ausführenden Dienst herunter.</span><span class="sxs-lookup"><span data-stu-id="3da0a-124">The following command downloads metadata documents from a running service.</span></span>  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a><span data-ttu-id="3da0a-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3da0a-125">See also</span></span>

- [<span data-ttu-id="3da0a-126">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="3da0a-126">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
