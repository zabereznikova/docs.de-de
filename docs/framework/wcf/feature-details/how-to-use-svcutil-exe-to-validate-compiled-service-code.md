---
title: 'Vorgehensweise: Verwenden von „Svcutil.exe“ zum Überprüfen von kompiliertem Dienstcode'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 6f2064c696e3186c3208a7e57dc51655056d23ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595348"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="a4493-102">Vorgehensweise: Verwenden von „Svcutil.exe“ zum Überprüfen von kompiliertem Dienstcode</span><span class="sxs-lookup"><span data-stu-id="a4493-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="a4493-103">Sie können das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden, um Fehler in Dienst Implementierungen und Konfigurationen zu erkennen, ohne den Dienst zu Hosting.</span><span class="sxs-lookup"><span data-stu-id="a4493-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="a4493-104">So überprüfen Sie einen Dienst</span><span class="sxs-lookup"><span data-stu-id="a4493-104">To validate a service</span></span>  
  
1. <span data-ttu-id="a4493-105">Kompilieren Sie den Dienst in eine ausführbare Datei und eine oder mehrere abhängige Assemblys.</span><span class="sxs-lookup"><span data-stu-id="a4493-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2. <span data-ttu-id="a4493-106">Öffnen Sie eine SDK-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="a4493-106">Open an SDK command prompt</span></span>  
  
3. <span data-ttu-id="a4493-107">Starten Sie das Tool Svcutil.exe an der Eingabeaufforderung mit dem folgenden Format.</span><span class="sxs-lookup"><span data-stu-id="a4493-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="a4493-108">Weitere Informationen zu den verschiedenen Parametern finden Sie im Abschnitt "Service validationsection" des Themas "Service [Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) ".</span><span class="sxs-lookup"><span data-stu-id="a4493-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```console
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="a4493-109">Sie müssen die `/serviceName`-Option verwenden, um den Konfigurationsnamen des Dienstes anzugeben, den Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="a4493-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="a4493-110">Das `assemblyPath`-Argument gibt den Pfad zur ausführbaren Datei für den Dienst und eine oder mehrere Assemblys an, die die zu überprüfenden Diensttypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4493-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="a4493-111">Die ausführbare Assembly muss über eine zugeordnete Konfigurationsdatei verfügen, um die Dienstkonfiguration bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a4493-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="a4493-112">Sie können standardmäßige Befehlszeilenplatzhalter verwenden, um mehrere Assemblys anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a4493-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4493-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a4493-113">Example</span></span>  
 <span data-ttu-id="a4493-114">Der folgende Befehl hat den Dienst myServiceName in der ausführbaren Datei myServiceHost.exe implementiert.</span><span class="sxs-lookup"><span data-stu-id="a4493-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="a4493-115">Die Konfigurationsdatei für den Dienst (myServiceHost.exe.config) wird automatisch geladen.</span><span class="sxs-lookup"><span data-stu-id="a4493-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```console  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4493-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4493-116">See also</span></span>

- [<span data-ttu-id="a4493-117">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="a4493-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
