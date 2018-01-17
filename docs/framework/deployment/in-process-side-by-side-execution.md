---
title: "Prozessinterne parallele Ausführung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 023a8db1e34498c4c2cbe741225d218280c04e41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="in-process-side-by-side-execution"></a><span data-ttu-id="bfd12-102">Prozessinterne parallele Ausführung</span><span class="sxs-lookup"><span data-stu-id="bfd12-102">In-Process Side-by-Side Execution</span></span>
<span data-ttu-id="bfd12-103">Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie mit prozessinternem parallelem Hosting mehrere Versionen der Common Language Runtime (CLR) in einem einzelnen Prozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="bfd12-103">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use in-process side-by-side hosting to run multiple versions of the common language runtime (CLR) in a single process.</span></span> <span data-ttu-id="bfd12-104">Standardmäßig werden verwaltete COM-Komponenten mit der .NET Framework-Version ausgeführt, mit der sie erstellt wurden, unabhängig von der .NET Framework-Version, die für den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="bfd12-104">By default, managed COM components run with the .NET Framework version they were built with, regardless of the .NET Framework version that is loaded for the process.</span></span>  
  
## <a name="background"></a><span data-ttu-id="bfd12-105">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="bfd12-105">Background</span></span>  
 <span data-ttu-id="bfd12-106">Das .NET Framework bot schon immer paralleles Hosting für verwaltete Codeanwendungen, vor [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] gab es diese Funktion jedoch nicht für verwaltete COM-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="bfd12-106">The .NET Framework has always provided side-by-side hosting for managed code applications, but before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], it did not provide that functionality for managed COM components.</span></span> <span data-ttu-id="bfd12-107">In der Vergangenheit wurden verwaltete COM-Komponenten, die in einen Prozess geladen wurden, entweder mit der Version der bereits geladenen Runtime oder mit der neuesten installierten Version von .NET Framework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bfd12-107">In the past, managed COM components that were loaded into a process ran either with the version of the runtime that was already loaded or with the latest installed version of the .NET Framework.</span></span> <span data-ttu-id="bfd12-108">Wenn diese Version nicht mit der COM-Komponente kompatibel war, ist die Komponente fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="bfd12-108">If this version was not compatible with the COM component, the component would fail.</span></span>  
  
 <span data-ttu-id="bfd12-109">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] bietet eine neue Herangehensweise des parallelen Hostings, wodurch Folgendes sichergestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="bfd12-109">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] provides a new approach to side-by-side hosting that ensures the following:</span></span>  
  
-   <span data-ttu-id="bfd12-110">Die Installation einer neuen Version von .NET Framework hat keinen Einfluss auf vorhandene Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="bfd12-110">Installing a new version of the .NET Framework has no effect on existing applications.</span></span>  
  
-   <span data-ttu-id="bfd12-111">Anwendungen werden auf der Version des .NET Framework aufgeführt, mit dem sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bfd12-111">Applications run against the version of the .NET Framework that they were built with.</span></span> <span data-ttu-id="bfd12-112">Sie verwenden nicht die neue Version des .NET Framework, es sei denn, es wird ausdrücklich darauf hingewiesen.</span><span class="sxs-lookup"><span data-stu-id="bfd12-112">They do not use the new version of the .NET Framework unless expressly directed to do so.</span></span> <span data-ttu-id="bfd12-113">Es ist für Anwendungen, zu der ein Übergang stattfindet, jedoch einfacher, eine neue Version von .NET Framework zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bfd12-113">However, it is easier for applications to transition to using a new version of the .NET Framework.</span></span>  
  
## <a name="effects-on-users-and-developers"></a><span data-ttu-id="bfd12-114">Auswirkungen auf Benutzer und Entwickler</span><span class="sxs-lookup"><span data-stu-id="bfd12-114">Effects on Users and Developers</span></span>  
  
-   <span data-ttu-id="bfd12-115">**Endbenutzer und Systemadministratoren**.</span><span class="sxs-lookup"><span data-stu-id="bfd12-115">**End users and system administrators**.</span></span> <span data-ttu-id="bfd12-116">Diese Benutzer können nun bei der Installation einer Version der Runtime sicherer sein, wenn sie diese entweder eigenständig oder mit einer Anwendung erstellen. Dies hat keinen Einfluss auf deren Computer.</span><span class="sxs-lookup"><span data-stu-id="bfd12-116">These users can now have greater confidence that when they install a new version of the runtime, either independently or with an application, it will have no impact on their computers.</span></span> <span data-ttu-id="bfd12-117">Vorhandene Anwendungen werden genauso wie vorher ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bfd12-117">Existing applications will continue to run as they did before.</span></span>  
  
-   <span data-ttu-id="bfd12-118">**Anwendungsentwickler**.</span><span class="sxs-lookup"><span data-stu-id="bfd12-118">**Application developers**.</span></span> <span data-ttu-id="bfd12-119">Das parallele Hosting hat so gut wie keine Auswirkungen auf Anwendungsentwickler.</span><span class="sxs-lookup"><span data-stu-id="bfd12-119">Side-by-side hosting has almost no effect on application developers.</span></span> <span data-ttu-id="bfd12-120">Standardmäßig werden Anwendungen immer auf der Version des .NET Framework ausgeführt, auf dem sie erstellt wurden; dies hat sich nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="bfd12-120">By default, applications always run against the version of the .NET Framework they were built on; this has not changed.</span></span> <span data-ttu-id="bfd12-121">Jedoch können Entwickler dieses Verhalten außer Kraft setzen und Anwendungen dazu bringen, unter einer neueren Version des .NET Framework zu laufen (siehe [Szenario 2](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="bfd12-121">However, developers can override this behavior and direct the application to run under a newer version of the .NET Framework (see [scenario 2](#scenarios)).</span></span>  
  
-   <span data-ttu-id="bfd12-122">**Bibliotheksentwickler und Consumer**.</span><span class="sxs-lookup"><span data-stu-id="bfd12-122">**Library developers and consumers**.</span></span> <span data-ttu-id="bfd12-123">Das parallele Hosting löst nicht die Probleme mit der Kompatibilität, denen Bibliotheksentwickler gegenüberstehen.</span><span class="sxs-lookup"><span data-stu-id="bfd12-123">Side-by-side hosting does not solve the compatibility problems that library developers face.</span></span> <span data-ttu-id="bfd12-124">Eine Bibliothek, die direkt durch eine Anwendung geladen wird, entweder durch einen Direktverweis oder einen <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Aufruf, verwendet weiterhin die Runtime von <xref:System.AppDomain>, in der sie geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bfd12-124">A library that is directly loaded by an application -- either through a direct reference or through an <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> call -- continues to use the runtime of the <xref:System.AppDomain> it is loaded into.</span></span> <span data-ttu-id="bfd12-125">Sie sollten Ihre Bibliotheken für alle .NET Framework-Versionen testen, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="bfd12-125">You should test your libraries against all versions of the .NET Framework that you want to support.</span></span> <span data-ttu-id="bfd12-126">Wenn eine Anwendung mithilfe der [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]-Runtime kompiliert wird, jedoch eine Bibliothek enthält, die mit einer früheren Runtime erstellt wurde, wird dies Bibliothek ebenso die [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]-Runtime verwenden.</span><span class="sxs-lookup"><span data-stu-id="bfd12-126">If an application is compiled using the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] runtime but includes a library that was built using an earlier runtime, that library will use the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] runtime as well.</span></span> <span data-ttu-id="bfd12-127">Wenn Sie jedoch über eine Anwendung verfügen, die mithilfe einer früheren Runtime erstellt wurde, sowie eine Bibliothek, die mit [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] erstellt wurde, müssen Sie Ihre Anwendung dazu zwingen, auch [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] zu verwenden (siehe [Szenario 3](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="bfd12-127">However, if you have an application that was built using an earlier runtime and a library that was built using the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], you must force your application to also use the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] (see [scenario 3](#scenarios)).</span></span>  
  
-   <span data-ttu-id="bfd12-128">**Entwickler verwalteter COM-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="bfd12-128">**Managed COM component developers**.</span></span> <span data-ttu-id="bfd12-129">Früher wurden die verwalteten COM-Komponenten automatisch mithilfe der aktuellsten Version der Runtime ausgeführt, die auf dem Computer installiert war.</span><span class="sxs-lookup"><span data-stu-id="bfd12-129">In the past, managed COM components automatically ran using the latest version of the runtime installed on the computer.</span></span> <span data-ttu-id="bfd12-130">Sie können nun COM-Komponenten für die Version der Runtime ausführen, mit der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bfd12-130">You can now execute COM components against the version of the runtime they were built with.</span></span>  
  
     <span data-ttu-id="bfd12-131">So wie in der folgenden Tabelle gezeigt, können Komponenten, die mit der .NET Framework-Version 1.1 erstellt wurden, parallel mit Komponenten der Version 4 ausgeführt werden. Sie können jedoch nicht mit Komponenten der Version 2.0, 3.0 oder 3.5 ausgeführt werden, da das parallele Hosting für diese Versionen nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bfd12-131">As shown by the following table, components that were built with the .NET Framework version 1.1 can run side by side with version 4 components, but they cannot run with version 2.0, 3.0, or 3.5 components, because side-by-side hosting is not available for those versions.</span></span>  
  
    |<span data-ttu-id="bfd12-132">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="bfd12-132">.NET Framework version</span></span>|<span data-ttu-id="bfd12-133">1,1</span><span class="sxs-lookup"><span data-stu-id="bfd12-133">1.1</span></span>|<span data-ttu-id="bfd12-134">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="bfd12-134">2.0 - 3.5</span></span>|<span data-ttu-id="bfd12-135">4</span><span class="sxs-lookup"><span data-stu-id="bfd12-135">4</span></span>|  
    |----------------------------|---------|----------------|-------|  
    |<span data-ttu-id="bfd12-136">1,1</span><span class="sxs-lookup"><span data-stu-id="bfd12-136">1.1</span></span>|<span data-ttu-id="bfd12-137">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="bfd12-137">Not applicable</span></span>|<span data-ttu-id="bfd12-138">Nein</span><span class="sxs-lookup"><span data-stu-id="bfd12-138">No</span></span>|<span data-ttu-id="bfd12-139">Ja</span><span class="sxs-lookup"><span data-stu-id="bfd12-139">Yes</span></span>|  
    |<span data-ttu-id="bfd12-140">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="bfd12-140">2.0 - 3.5</span></span>|<span data-ttu-id="bfd12-141">Nein</span><span class="sxs-lookup"><span data-stu-id="bfd12-141">No</span></span>|<span data-ttu-id="bfd12-142">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="bfd12-142">Not applicable</span></span>|<span data-ttu-id="bfd12-143">Ja</span><span class="sxs-lookup"><span data-stu-id="bfd12-143">Yes</span></span>|  
    |<span data-ttu-id="bfd12-144">4</span><span class="sxs-lookup"><span data-stu-id="bfd12-144">4</span></span>|<span data-ttu-id="bfd12-145">Ja</span><span class="sxs-lookup"><span data-stu-id="bfd12-145">Yes</span></span>|<span data-ttu-id="bfd12-146">Ja</span><span class="sxs-lookup"><span data-stu-id="bfd12-146">Yes</span></span>|<span data-ttu-id="bfd12-147">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="bfd12-147">Not applicable</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="bfd12-148">.NET Framework-Versionen 3.0 und 3.5 werden inkrementell auf Version 2.0 erstellt und müssen nicht parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bfd12-148">.NET Framework versions 3.0 and 3.5 are built incrementally on version 2.0, and do not need to run side by side.</span></span> <span data-ttu-id="bfd12-149">Sie sind an und für sich dieselbe Version.</span><span class="sxs-lookup"><span data-stu-id="bfd12-149">These are inherently the same version.</span></span>  
  
<a name="scenarios"></a>   
## <a name="common-side-by-side-hosting-scenarios"></a><span data-ttu-id="bfd12-150">Häufige Szenarios des parallelen Hostings</span><span class="sxs-lookup"><span data-stu-id="bfd12-150">Common Side-by-Side Hosting Scenarios</span></span>  
  
-   <span data-ttu-id="bfd12-151">**Szenario 1:** Native Anwendung, die COM-Komponenten verwendet, die mit früheren Versionen von .NET Framework erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bfd12-151">**Scenario 1:** Native application that uses COM components built with earlier versions of the .NET Framework.</span></span>  
  
     <span data-ttu-id="bfd12-152">Installierte .NET Framework-Versionen: Die [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] und alle anderen Versionen des .NET Framework, die von den COM-Komponenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bfd12-152">.NET Framework versions installed: The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] and all other versions of the .NET Framework used by the COM components.</span></span>  
  
     <span data-ttu-id="bfd12-153">Das muss ich tun: In diesem Szenario unternehmen Sie nichts.</span><span class="sxs-lookup"><span data-stu-id="bfd12-153">What to do: In this scenario, do nothing.</span></span> <span data-ttu-id="bfd12-154">Die COM-Komponenten werden mit der Version des .NET Framework ausgeführt, mit der sie registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="bfd12-154">The COM components will run with the version of the .NET Framework they were registered with.</span></span>  
  
-   <span data-ttu-id="bfd12-155">**Szenario 2**: Verwaltete Anwendung, die mit [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] erstellt wurde, die lieber mit [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)] ausgeführt werden soll, jedoch auch unter [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ausgeführt werden kann, wenn Version 2.0 nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bfd12-155">**Scenario 2**: Managed application built with the [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] that you would prefer to run with the [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)], but are willing to run on the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] if version 2.0 is not present.</span></span>  
  
     <span data-ttu-id="bfd12-156">Installierte .NET Framework-Version: Eine frühere Version von .NET Framework und [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfd12-156">.NET Framework versions installed: An earlier version of the .NET Framework and the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
     <span data-ttu-id="bfd12-157">Vorgehensweise: Verwenden Sie in der [Anwendungskonfigurationsdatei](../../../docs/framework/configure-apps/index.md) im Anwendungsverzeichnis das [\<startup>-Element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) und das [\<supportedRuntime>-Element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md), die wie folgt festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="bfd12-157">What to do: In the [application configuration file](../../../docs/framework/configure-apps/index.md) in the application directory, use the [\<startup> element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) and the [\<supportedRuntime> element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="bfd12-158">**Szenario 3:** Native Anwendung, die COM-Komponenten verwendet, die mit früheren Versionen von .NET Framework erstellt wurden, die Sie mit [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="bfd12-158">**Scenario 3:** Native application that uses COM components built with earlier versions of the .NET Framework that you want to run with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
     <span data-ttu-id="bfd12-159">Installierte .NET Framework-Versionen: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfd12-159">.NET Framework versions installed: The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
     <span data-ttu-id="bfd12-160">Vorgehensweise: Verwenden Sie in der Anwendungskonfigurationsdatei im Anwendungsverzeichnis das `<startup>`-Element, mit mit dem `useLegacyV2RuntimeActivationPolicy`-Attribut, das auf `true` festgelegt ist, sowie das `<supportedRuntime>`-Element, das wie folgt festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="bfd12-160">What to do: In the application configuration file in the application directory, use the `<startup>` element with the `useLegacyV2RuntimeActivationPolicy` attribute set to `true` and the `<supportedRuntime>` element set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="bfd12-161">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bfd12-161">Example</span></span>  
 <span data-ttu-id="bfd12-162">Das folgende Beispiel stellt einen nicht verwalteten COM-Host dar, der eine verwaltete COM-Komponente mithilfe der Version von .NET Framework ausführt, für deren Verwendung die Komponente kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="bfd12-162">The following example demonstrates an unmanaged COM host that is running a managed COM component by using the version of the .NET Framework that the component was compiled to use.</span></span>  
  
 <span data-ttu-id="bfd12-163">Um das folgende Beispiel auszuführen, kompilieren und registrieren Sie die folgende verwaltete COM-Komponente mithilfe von [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfd12-163">To run the following example, compile and register the following managed COM component using the [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].</span></span> <span data-ttu-id="bfd12-164">Um die Komponente zu registrieren, klicken Sie im **Projekt**-Menü auf **Eigenschaften**, auf die Registerkarte **Erstellen**, und aktivieren Sie dann das Kontrollkästchen **Für COM-Interop registrieren**.</span><span class="sxs-lookup"><span data-stu-id="bfd12-164">To register the component, on the **Project** menu, click **Properties**, click the **Build** tab, and then select the **Register for COM interop** check box.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="bfd12-165">Kompilieren Sie die folgende nicht verwaltete C++-Anwendung, die das COM-Objekt aktiviert, das durch das vorherige Beispiel erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bfd12-165">Compile the following unmanaged C++ application, which activates the COM object that is created by the previous example.</span></span>  
  
```  
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");   
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfd12-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfd12-166">See Also</span></span>  
 [<span data-ttu-id="bfd12-167">\<startup>-Element</span><span class="sxs-lookup"><span data-stu-id="bfd12-167">\<startup> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
 [<span data-ttu-id="bfd12-168">\<supportedRuntime> Element</span><span class="sxs-lookup"><span data-stu-id="bfd12-168">\<supportedRuntime> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)
