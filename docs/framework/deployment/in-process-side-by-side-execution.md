---
title: Prozessinterne parallele Ausführung
ms.date: 03/30/2017
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
ms.openlocfilehash: 0c699f90143a87b7e7bee24c892efe2936a9399e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716482"
---
# <a name="in-process-side-by-side-execution"></a><span data-ttu-id="567ae-102">Prozessinterne parallele Ausführung</span><span class="sxs-lookup"><span data-stu-id="567ae-102">In-Process Side-by-Side Execution</span></span>
<span data-ttu-id="567ae-103">Ab .NET Framework 4 können Sie mit prozessinternem parallelem Hosting mehrere Versionen der Common Language Runtime (CLR) in einem einzigen Prozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="567ae-103">Starting with the .NET Framework 4, you can use in-process side-by-side hosting to run multiple versions of the common language runtime (CLR) in a single process.</span></span> <span data-ttu-id="567ae-104">Standardmäßig werden verwaltete COM-Komponenten mit der .NET Framework-Version ausgeführt, mit der sie erstellt wurden, unabhängig von der .NET Framework-Version, die für den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="567ae-104">By default, managed COM components run with the .NET Framework version they were built with, regardless of the .NET Framework version that is loaded for the process.</span></span>  
  
## <a name="background"></a><span data-ttu-id="567ae-105">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="567ae-105">Background</span></span>  
 <span data-ttu-id="567ae-106">.NET Framework bot schon immer paralleles Hosting für verwaltete Codeanwendungen. Vor .NET Framework 4 stand diese Funktion jedoch nicht für verwaltete COM-Komponenten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="567ae-106">The .NET Framework has always provided side-by-side hosting for managed code applications, but before the .NET Framework 4, it did not provide that functionality for managed COM components.</span></span> <span data-ttu-id="567ae-107">In der Vergangenheit wurden verwaltete COM-Komponenten, die in einen Prozess geladen wurden, entweder mit der Version der bereits geladenen Runtime oder mit der neuesten installierten Version von .NET Framework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="567ae-107">In the past, managed COM components that were loaded into a process ran either with the version of the runtime that was already loaded or with the latest installed version of the .NET Framework.</span></span> <span data-ttu-id="567ae-108">Wenn diese Version nicht mit der COM-Komponente kompatibel war, ist die Komponente fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="567ae-108">If this version was not compatible with the COM component, the component would fail.</span></span>  
  
 <span data-ttu-id="567ae-109">.NET Framework 4 bietet eine neue Herangehensweise des parallelen Hostings, wodurch Folgendes sichergestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="567ae-109">The .NET Framework 4 provides a new approach to side-by-side hosting that ensures the following:</span></span>  
  
- <span data-ttu-id="567ae-110">Die Installation einer neuen Version von .NET Framework hat keinen Einfluss auf vorhandene Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="567ae-110">Installing a new version of the .NET Framework has no effect on existing applications.</span></span>  
  
- <span data-ttu-id="567ae-111">Anwendungen werden auf der Version des .NET Framework aufgeführt, mit dem sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="567ae-111">Applications run against the version of the .NET Framework that they were built with.</span></span> <span data-ttu-id="567ae-112">Sie verwenden nicht die neue Version des .NET Framework, es sei denn, es wird ausdrücklich darauf hingewiesen.</span><span class="sxs-lookup"><span data-stu-id="567ae-112">They do not use the new version of the .NET Framework unless expressly directed to do so.</span></span> <span data-ttu-id="567ae-113">Es ist für Anwendungen, zu der ein Übergang stattfindet, jedoch einfacher, eine neue Version von .NET Framework zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="567ae-113">However, it is easier for applications to transition to using a new version of the .NET Framework.</span></span>  
  
## <a name="effects-on-users-and-developers"></a><span data-ttu-id="567ae-114">Auswirkungen auf Benutzer und Entwickler</span><span class="sxs-lookup"><span data-stu-id="567ae-114">Effects on Users and Developers</span></span>  
  
- <span data-ttu-id="567ae-115">**Endbenutzer und Systemadministratoren**.</span><span class="sxs-lookup"><span data-stu-id="567ae-115">**End users and system administrators**.</span></span> <span data-ttu-id="567ae-116">Diese Benutzer können nun bei der Installation einer Version der Runtime sicherer sein, wenn sie diese entweder eigenständig oder mit einer Anwendung erstellen. Dies hat keinen Einfluss auf deren Computer.</span><span class="sxs-lookup"><span data-stu-id="567ae-116">These users can now have greater confidence that when they install a new version of the runtime, either independently or with an application, it will have no impact on their computers.</span></span> <span data-ttu-id="567ae-117">Vorhandene Anwendungen werden genauso wie vorher ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="567ae-117">Existing applications will continue to run as they did before.</span></span>  
  
- <span data-ttu-id="567ae-118">**Anwendungsentwickler**.</span><span class="sxs-lookup"><span data-stu-id="567ae-118">**Application developers**.</span></span> <span data-ttu-id="567ae-119">Das parallele Hosting hat so gut wie keine Auswirkungen auf Anwendungsentwickler.</span><span class="sxs-lookup"><span data-stu-id="567ae-119">Side-by-side hosting has almost no effect on application developers.</span></span> <span data-ttu-id="567ae-120">Standardmäßig werden Anwendungen immer auf der Version des .NET Framework ausgeführt, auf dem sie erstellt wurden; dies hat sich nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="567ae-120">By default, applications always run against the version of the .NET Framework they were built on; this has not changed.</span></span> <span data-ttu-id="567ae-121">Jedoch können Entwickler dieses Verhalten außer Kraft setzen und Anwendungen dazu bringen, unter einer neueren Version des .NET Framework zu laufen (siehe [Szenario 2](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="567ae-121">However, developers can override this behavior and direct the application to run under a newer version of the .NET Framework (see [scenario 2](#scenarios)).</span></span>  
  
- <span data-ttu-id="567ae-122">**Bibliotheksentwickler und Consumer**.</span><span class="sxs-lookup"><span data-stu-id="567ae-122">**Library developers and consumers**.</span></span> <span data-ttu-id="567ae-123">Das parallele Hosting löst nicht die Probleme mit der Kompatibilität, denen Bibliotheksentwickler gegenüberstehen.</span><span class="sxs-lookup"><span data-stu-id="567ae-123">Side-by-side hosting does not solve the compatibility problems that library developers face.</span></span> <span data-ttu-id="567ae-124">Eine Bibliothek, die direkt durch eine Anwendung geladen wird, entweder durch einen Direktverweis oder einen <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Aufruf, verwendet weiterhin die Runtime von <xref:System.AppDomain>, in der sie geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="567ae-124">A library that is directly loaded by an application -- either through a direct reference or through an <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> call -- continues to use the runtime of the <xref:System.AppDomain> it is loaded into.</span></span> <span data-ttu-id="567ae-125">Sie sollten Ihre Bibliotheken für alle .NET Framework-Versionen testen, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="567ae-125">You should test your libraries against all versions of the .NET Framework that you want to support.</span></span> <span data-ttu-id="567ae-126">Wenn eine Anwendung mithilfe der .NET Framework 4-Runtime kompiliert wird, aber eine Bibliothek enthält, die mit einer früheren Runtime erstellt wurde, nutzt diese Bibliothek ebenso die .NET Framework 4-Runtime.</span><span class="sxs-lookup"><span data-stu-id="567ae-126">If an application is compiled using the .NET Framework 4 runtime but includes a library that was built using an earlier runtime, that library will use the .NET Framework 4 runtime as well.</span></span> <span data-ttu-id="567ae-127">Wenn Sie jedoch über eine Anwendung verfügen, die mithilfe einer früheren Runtime erstellt wurde, sowie über eine Bibliothek, die mit .NET Framework 4 erstellt wurde, müssen Sie für Ihre Anwendung die Verwendung von .NET Framework 4 erzwingen (siehe [Szenario 3](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="567ae-127">However, if you have an application that was built using an earlier runtime and a library that was built using the .NET Framework 4, you must force your application to also use the .NET Framework 4 (see [scenario 3](#scenarios)).</span></span>  
  
- <span data-ttu-id="567ae-128">**Entwickler verwalteter COM-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="567ae-128">**Managed COM component developers**.</span></span> <span data-ttu-id="567ae-129">Früher wurden die verwalteten COM-Komponenten automatisch mithilfe der aktuellsten Version der Runtime ausgeführt, die auf dem Computer installiert war.</span><span class="sxs-lookup"><span data-stu-id="567ae-129">In the past, managed COM components automatically ran using the latest version of the runtime installed on the computer.</span></span> <span data-ttu-id="567ae-130">Sie können nun COM-Komponenten für die Version der Runtime ausführen, mit der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="567ae-130">You can now execute COM components against the version of the runtime they were built with.</span></span>  
  
     <span data-ttu-id="567ae-131">So wie in der folgenden Tabelle gezeigt, können Komponenten, die mit der .NET Framework-Version 1.1 erstellt wurden, parallel mit Komponenten der Version 4 ausgeführt werden. Sie können jedoch nicht mit Komponenten der Version 2.0, 3.0 oder 3.5 ausgeführt werden, da das parallele Hosting für diese Versionen nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="567ae-131">As shown by the following table, components that were built with the .NET Framework version 1.1 can run side by side with version 4 components, but they cannot run with version 2.0, 3.0, or 3.5 components, because side-by-side hosting is not available for those versions.</span></span>  
  
    |<span data-ttu-id="567ae-132">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="567ae-132">.NET Framework version</span></span>|<span data-ttu-id="567ae-133">1.1</span><span class="sxs-lookup"><span data-stu-id="567ae-133">1.1</span></span>|<span data-ttu-id="567ae-134">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="567ae-134">2.0 - 3.5</span></span>|<span data-ttu-id="567ae-135">4</span><span class="sxs-lookup"><span data-stu-id="567ae-135">4</span></span>|  
    |----------------------------|---------|----------------|-------|  
    |<span data-ttu-id="567ae-136">1.1</span><span class="sxs-lookup"><span data-stu-id="567ae-136">1.1</span></span>|<span data-ttu-id="567ae-137">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="567ae-137">Not applicable</span></span>|<span data-ttu-id="567ae-138">Nein</span><span class="sxs-lookup"><span data-stu-id="567ae-138">No</span></span>|<span data-ttu-id="567ae-139">Ja</span><span class="sxs-lookup"><span data-stu-id="567ae-139">Yes</span></span>|  
    |<span data-ttu-id="567ae-140">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="567ae-140">2.0 - 3.5</span></span>|<span data-ttu-id="567ae-141">Nein</span><span class="sxs-lookup"><span data-stu-id="567ae-141">No</span></span>|<span data-ttu-id="567ae-142">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="567ae-142">Not applicable</span></span>|<span data-ttu-id="567ae-143">Ja</span><span class="sxs-lookup"><span data-stu-id="567ae-143">Yes</span></span>|  
    |<span data-ttu-id="567ae-144">4</span><span class="sxs-lookup"><span data-stu-id="567ae-144">4</span></span>|<span data-ttu-id="567ae-145">Ja</span><span class="sxs-lookup"><span data-stu-id="567ae-145">Yes</span></span>|<span data-ttu-id="567ae-146">Ja</span><span class="sxs-lookup"><span data-stu-id="567ae-146">Yes</span></span>|<span data-ttu-id="567ae-147">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="567ae-147">Not applicable</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="567ae-148">.NET Framework-Versionen 3.0 und 3.5 werden inkrementell auf Version 2.0 erstellt und müssen nicht parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="567ae-148">.NET Framework versions 3.0 and 3.5 are built incrementally on version 2.0, and do not need to run side by side.</span></span> <span data-ttu-id="567ae-149">Sie sind an und für sich dieselbe Version.</span><span class="sxs-lookup"><span data-stu-id="567ae-149">These are inherently the same version.</span></span>  
  
<a name="scenarios"></a>   
## <a name="common-side-by-side-hosting-scenarios"></a><span data-ttu-id="567ae-150">Häufige Szenarios des parallelen Hostings</span><span class="sxs-lookup"><span data-stu-id="567ae-150">Common Side-by-Side Hosting Scenarios</span></span>  
  
- <span data-ttu-id="567ae-151">**Szenario 1:** Eine Native Anwendung, die COM-Komponenten verwendet, die mit früheren Versionen von .NET Framework erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="567ae-151">**Scenario 1:** Native application that uses COM components built with earlier versions of the .NET Framework.</span></span>  
  
     <span data-ttu-id="567ae-152">Installierte .NET Framework-Versionen: .NET Framework 4 und alle anderen Versionen von .NET Framework, die von den COM-Komponenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="567ae-152">.NET Framework versions installed: The .NET Framework 4 and all other versions of the .NET Framework used by the COM components.</span></span>  
  
     <span data-ttu-id="567ae-153">Vorgehensweise: In diesem Szenario unternehmen Sie nichts.</span><span class="sxs-lookup"><span data-stu-id="567ae-153">What to do: In this scenario, do nothing.</span></span> <span data-ttu-id="567ae-154">Die COM-Komponenten werden mit der Version des .NET Framework ausgeführt, mit der sie registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="567ae-154">The COM components will run with the version of the .NET Framework they were registered with.</span></span>  
  
- <span data-ttu-id="567ae-155">**Szenario 2:** Mit .NET Framework 2.0 SP1 erstellte verwaltete Anwendung, die bevorzugt mit .NET Framework 2.0 ausgeführt werden soll, jedoch auch mit .NET Framework 4 ausgeführt werden kann, falls Version 2.0 nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="567ae-155">**Scenario 2**: Managed application built with the .NET Framework 2.0 SP1 that you would prefer to run with the .NET Framework 2.0, but are willing to run on the .NET Framework 4 if version 2.0 is not present.</span></span>  
  
     <span data-ttu-id="567ae-156">Installierte .NET Framework-Versionen: Eine frühere Version von .NET Framework sowie .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="567ae-156">.NET Framework versions installed: An earlier version of the .NET Framework and the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="567ae-157">Vorgehensweise: Verwenden Sie in der [Anwendungskonfigurationsdatei](../configure-apps/index.md) im Anwendungsverzeichnis das [Element \<startup>](../configure-apps/file-schema/startup/startup-element.md) und das [Element \<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md), die wie folgt festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="567ae-157">What to do: In the [application configuration file](../configure-apps/index.md) in the application directory, use the [\<startup> element](../configure-apps/file-schema/startup/startup-element.md) and the [\<supportedRuntime> element](../configure-apps/file-schema/startup/supportedruntime-element.md) set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
- <span data-ttu-id="567ae-158">**Szenario 3:** Native Anwendung, die COM-Komponenten verwendet, die mit früheren Versionen von .NET Framework erstellt wurden und die Sie mit .NET Framework 4 ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="567ae-158">**Scenario 3:** Native application that uses COM components built with earlier versions of the .NET Framework that you want to run with the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="567ae-159">Installierte .NET Framework-Versionen: .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="567ae-159">.NET Framework versions installed: The .NET Framework 4.</span></span>  
  
     <span data-ttu-id="567ae-160">Vorgehensweise: Verwenden Sie in der Anwendungskonfigurationsdatei im Anwendungsverzeichnis das `<startup>`-Element, mit dem `useLegacyV2RuntimeActivationPolicy`-Attribut, das auf `true` festgelegt ist, sowie das `<supportedRuntime>`-Element, das wie folgt festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="567ae-160">What to do: In the application configuration file in the application directory, use the `<startup>` element with the `useLegacyV2RuntimeActivationPolicy` attribute set to `true` and the `<supportedRuntime>` element set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="567ae-161">Beispiel</span><span class="sxs-lookup"><span data-stu-id="567ae-161">Example</span></span>  
 <span data-ttu-id="567ae-162">Das folgende Beispiel stellt einen nicht verwalteten COM-Host dar, der eine verwaltete COM-Komponente mithilfe der Version von .NET Framework ausführt, für deren Verwendung die Komponente kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="567ae-162">The following example demonstrates an unmanaged COM host that is running a managed COM component by using the version of the .NET Framework that the component was compiled to use.</span></span>  
  
 <span data-ttu-id="567ae-163">Um das folgende Beispiel auszuführen, kompilieren und registrieren Sie die folgende verwaltete COM-Komponente mithilfe von .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="567ae-163">To run the following example, compile and register the following managed COM component using the .NET Framework 3.5.</span></span> <span data-ttu-id="567ae-164">Um die Komponente zu registrieren, klicken Sie im **Projekt**-Menü auf **Eigenschaften**, auf die Registerkarte **Erstellen**, und aktivieren Sie dann das Kontrollkästchen **Für COM-Interop registrieren**.</span><span class="sxs-lookup"><span data-stu-id="567ae-164">To register the component, on the **Project** menu, click **Properties**, click the **Build** tab, and then select the **Register for COM interop** check box.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="567ae-165">Kompilieren Sie die folgende nicht verwaltete C++-Anwendung, die das COM-Objekt aktiviert, das durch das vorherige Beispiel erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="567ae-165">Compile the following unmanaged C++ application, which activates the COM object that is created by the previous example.</span></span>  
  
```cpp
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
  
## <a name="see-also"></a><span data-ttu-id="567ae-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="567ae-166">See also</span></span>

- [<span data-ttu-id="567ae-167">\<startup>-Element</span><span class="sxs-lookup"><span data-stu-id="567ae-167">\<startup> Element</span></span>](../configure-apps/file-schema/startup/startup-element.md)
- [<span data-ttu-id="567ae-168">\<supportedRuntime> Element</span><span class="sxs-lookup"><span data-stu-id="567ae-168">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
