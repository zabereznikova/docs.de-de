---
title: 'Vorgehensweise: Verwenden von „Svcutil.exe“ zum Überprüfen von kompiliertem Dienstcode'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 599f5624b7eb0c32cbcc0a78e6c7f989ce470b58
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312422"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="31b40-102">Vorgehensweise: Verwenden von „Svcutil.exe“ zum Überprüfen von kompiliertem Dienstcode</span><span class="sxs-lookup"><span data-stu-id="31b40-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="31b40-103">Sie können die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) um Fehler in dienstimplementierungen und Konfigurationen zu erkennen, ohne den Dienst zu hosten.</span><span class="sxs-lookup"><span data-stu-id="31b40-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="31b40-104">So überprüfen Sie einen Dienst</span><span class="sxs-lookup"><span data-stu-id="31b40-104">To validate a service</span></span>  
  
1. <span data-ttu-id="31b40-105">Kompilieren Sie den Dienst in eine ausführbare Datei und eine oder mehrere abhängige Assemblys.</span><span class="sxs-lookup"><span data-stu-id="31b40-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2. <span data-ttu-id="31b40-106">Öffnen Sie eine SDK-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="31b40-106">Open an SDK command prompt</span></span>  
  
3. <span data-ttu-id="31b40-107">Starten Sie das Tool Svcutil.exe an der Eingabeaufforderung mit dem folgenden Format.</span><span class="sxs-lookup"><span data-stu-id="31b40-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="31b40-108">Weitere Informationen zu den verschiedenen Parametern finden Sie im Abschnitt zur Dienstvalidierung des der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="31b40-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="31b40-109">Sie müssen die `/serviceName`-Option verwenden, um den Konfigurationsnamen des Dienstes anzugeben, den Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="31b40-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="31b40-110">Das `assemblyPath`-Argument gibt den Pfad zur ausführbaren Datei für den Dienst und eine oder mehrere Assemblys an, die die zu überprüfenden Diensttypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="31b40-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="31b40-111">Die ausführbare Assembly muss über eine zugeordnete Konfigurationsdatei verfügen, um die Dienstkonfiguration bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="31b40-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="31b40-112">Sie können standardmäßige Befehlszeilenplatzhalter verwenden, um mehrere Assemblys anzugeben.</span><span class="sxs-lookup"><span data-stu-id="31b40-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31b40-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31b40-113">Example</span></span>  
 <span data-ttu-id="31b40-114">Der folgende Befehl hat den Dienst myServiceName in der ausführbaren Datei myServiceHost.exe implementiert.</span><span class="sxs-lookup"><span data-stu-id="31b40-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="31b40-115">Die Konfigurationsdatei für den Dienst (myServiceHost.exe.config) wird automatisch geladen.</span><span class="sxs-lookup"><span data-stu-id="31b40-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="31b40-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31b40-116">See also</span></span>

- [<span data-ttu-id="31b40-117">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="31b40-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
