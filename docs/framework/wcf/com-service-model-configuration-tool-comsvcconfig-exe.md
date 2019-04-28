---
title: COM+ Service Model Configuration-Tool (ComSvcConfig.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
ms.openlocfilehash: 6d0967355e64640e0fd5c81f04a5bf4f33c7b3f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608839"
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a><span data-ttu-id="e132f-102">COM+ Service Model Configuration-Tool (ComSvcConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="e132f-102">COM+ Service Model Configuration Tool (ComSvcConfig.exe)</span></span>
<span data-ttu-id="e132f-103">Das Befehlszeilentool COM+ Service Model Configuration (ComSvcConfig.exe) ermöglicht die Konfiguration von COM+-Schnittstellen, die als Webdienste verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e132f-103">The COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) enables you to configure COM+ interfaces to be exposed as Web services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e132f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e132f-104">Syntax</span></span>  
  
```  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a><span data-ttu-id="e132f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e132f-105">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e132f-106">Sie müssen Administrator auf dem lokalen Computer sein, um ComSvcConfig.exe zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e132f-106">You must be an administrator on the local computer to use ComSvcConfig.exe.</span></span>  
  
 <span data-ttu-id="e132f-107">Das Tool befindet sich an folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="e132f-107">The tool can be found in the following location</span></span>  
  
 <span data-ttu-id="e132f-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span><span class="sxs-lookup"><span data-stu-id="e132f-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span></span>  
  
 <span data-ttu-id="e132f-109">Weitere Informationen über ComSvcConfig.exe finden Sie unter [Vorgehensweise: Verwenden Sie das COM+ Service Model Configuration-Tool](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="e132f-109">For more information about ComSvcConfig.exe, see [How to: Use the COM+ Service Model Configuration Tool](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span></span>  
  
 <span data-ttu-id="e132f-110">In der folgenden Tabelle werden die Modi beschrieben, die mit ComSvcConfig.exe verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e132f-110">The following table describes the modes that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="e132f-111">Option</span><span class="sxs-lookup"><span data-stu-id="e132f-111">Option</span></span>|<span data-ttu-id="e132f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e132f-112">Description</span></span>|  
|------------|-----------------|  
|`install`|<span data-ttu-id="e132f-113">Installiert eine Konfiguration für eine COM+-Schnittstelle für die Service Model-Integration.</span><span class="sxs-lookup"><span data-stu-id="e132f-113">Installs a configuration for a COM+ interface for Service Model integration.</span></span><br /><br /> <span data-ttu-id="e132f-114">Kurzform: `/i`.</span><span class="sxs-lookup"><span data-stu-id="e132f-114">Short form `/i`.</span></span>|  
|`uninstall`|<span data-ttu-id="e132f-115">Deinstalliert eine Konfiguration für eine COM+-Schnittstelle aus der Service Model-Integration.</span><span class="sxs-lookup"><span data-stu-id="e132f-115">Uninstalls a configuration for a COM+ interface from Service Model integration.</span></span><br /><br /> <span data-ttu-id="e132f-116">Kurzform: `/u`.</span><span class="sxs-lookup"><span data-stu-id="e132f-116">Short form `/u`.</span></span>|  
|`list`|<span data-ttu-id="e132f-117">Listet Informationen über COM+-Anwendungen und -Komponenten auf, die über Schnittstellen verfügen, die für die Service Model-Integration konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="e132f-117">Lists information about COM+ applications and components that have interfaces that are configured for Service Model integration.</span></span><br /><br /> <span data-ttu-id="e132f-118">Kurzform: `/l`.</span><span class="sxs-lookup"><span data-stu-id="e132f-118">Short form `/l`.</span></span>|  
  
 <span data-ttu-id="e132f-119">In der folgenden Tabelle werden die Flags beschrieben, die mit ComSvcConfig.exe verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e132f-119">The following table describes the flags that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="e132f-120">Option</span><span class="sxs-lookup"><span data-stu-id="e132f-120">Option</span></span>|<span data-ttu-id="e132f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e132f-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e132f-122">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span><span class="sxs-lookup"><span data-stu-id="e132f-122">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span></span>|<span data-ttu-id="e132f-123">Gibt die zu konfigurierende COM+-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="e132f-123">Specifies the COM+ application to configure.</span></span><br /><br /> <span data-ttu-id="e132f-124">Kurzform: `/a`.</span><span class="sxs-lookup"><span data-stu-id="e132f-124">Short form `/a`.</span></span>|  
|<span data-ttu-id="e132f-125">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span><span class="sxs-lookup"><span data-stu-id="e132f-125">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span></span>|<span data-ttu-id="e132f-126">Gibt die COM+-Komponente und -Schnittstelle an, die als Vertrag für den Dienst konfiguriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e132f-126">Specifies the COM+ component and interface that will be configured as the contract for the service.</span></span><br /><br /> <span data-ttu-id="e132f-127">Kurzform: `/c`.</span><span class="sxs-lookup"><span data-stu-id="e132f-127">Short form `/c`.</span></span><br /><br /> <span data-ttu-id="e132f-128">Während Sie das Platzhalterzeichen (\*) kann verwendet werden, bei der Angabe der Komponenten- und Schnittstellennamen-Namen, es wird empfohlen, dass Sie nicht zu, verwenden, da Sie Schnittstellen verfügbar werden, die Sie nicht zum beabsichtigten gemacht können.</span><span class="sxs-lookup"><span data-stu-id="e132f-128">While the wildcard character (\*) can be used when you specify the component and interface names, we recommend that you do not use it, because you might expose interfaces that you did not intend to.</span></span>|  
|<span data-ttu-id="e132f-129">`/hosting:` \<*complus*  &#124; *was*\></span><span class="sxs-lookup"><span data-stu-id="e132f-129">`/hosting:` \<*complus*  &#124; *was*\></span></span>|<span data-ttu-id="e132f-130">Gibt an, ob der COM+-Hostingmodus oder der Webhostingmodus verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e132f-130">Specifies whether to use the COM+ hosting mode or the Web hosting mode.</span></span><br /><br /> <span data-ttu-id="e132f-131">Kurzform: `/h`.</span><span class="sxs-lookup"><span data-stu-id="e132f-131">Short form `/h`.</span></span><br /><br /> <span data-ttu-id="e132f-132">Die Verwendung des COM+-Hostingmodus erfordert die explizite Aktivierung der COM+-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e132f-132">Using the COM+ hosting mode requires explicit activation of the COM+ application.</span></span> <span data-ttu-id="e132f-133">Bei der Verwendung des Webhostingmodus wird die COM+-Anwendung automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e132f-133">Using the Web hosting mode allows the COM+ application to be automatically activated as required.</span></span> <span data-ttu-id="e132f-134">Wenn die COM+-Anwendung eine Bibliotheksanwendung ist, wird sie im IIS-Prozess (Internetinformationsdienste) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e132f-134">If the COM+ application is a library application, it runs in the Internet Information Services (IIS) process.</span></span> <span data-ttu-id="e132f-135">Wenn die COM+-Anwendung eine Serveranwendung ist, wird sie im Dllhost.exe-Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e132f-135">If the COM+ application is a server application, it runs in the Dllhost.exe process.</span></span>|  
|<span data-ttu-id="e132f-136">`/webSite:` \<*WebsiteName*\></span><span class="sxs-lookup"><span data-stu-id="e132f-136">`/webSite:` \<*WebsiteName*\></span></span>|<span data-ttu-id="e132f-137">Gibt bei Verwendung des Webhostingmodus die Website für das Hosting an (siehe das `/hosting`-Flag).</span><span class="sxs-lookup"><span data-stu-id="e132f-137">Specifies the Web site for hosting when Web hosting mode is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="e132f-138">Kurzform: `/w`.</span><span class="sxs-lookup"><span data-stu-id="e132f-138">Short form `/w`.</span></span><br /><br /> <span data-ttu-id="e132f-139">Wenn keine Website angegeben wird, wird die Standardwebsite verwendet.</span><span class="sxs-lookup"><span data-stu-id="e132f-139">If no Web site is specified, the default Web site is used.</span></span>|  
|<span data-ttu-id="e132f-140">`/webDirectory:` \<*WebDirectoryName*\></span><span class="sxs-lookup"><span data-stu-id="e132f-140">`/webDirectory:` \<*WebDirectoryName*\></span></span>|<span data-ttu-id="e132f-141">Gibt bei Verwendung des Webhosting das virtuelle Hostingverzeichnis an (siehe das `/hosting`-Flag).</span><span class="sxs-lookup"><span data-stu-id="e132f-141">Specifies the virtual directory for hosting when Web hosting is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="e132f-142">Kurzform: `/d`.</span><span class="sxs-lookup"><span data-stu-id="e132f-142">Short form `/d`.</span></span>|  
|`/mex`|<span data-ttu-id="e132f-143">Fügt der Standarddienstkonfiguration einen MEX-Dienstendpunkt (Metadata Exchange, Metadatenaustausch) hinzu, um Clients zu unterstützen, die eine Vertragsdefinition vom Dienst abrufen.</span><span class="sxs-lookup"><span data-stu-id="e132f-143">Adds a Metadata Exchange (MEX) service endpoint to the default service configuration to support clients that want to retrieve a contract definition from the service.</span></span><br /><br /> <span data-ttu-id="e132f-144">Kurzform: `/x`.</span><span class="sxs-lookup"><span data-stu-id="e132f-144">Short form `/x`.</span></span>|  
|`/id`|<span data-ttu-id="e132f-145">Zeigt die Anwendungs-, Komponenten- und Schnittstelleninformationen als IDs an.</span><span class="sxs-lookup"><span data-stu-id="e132f-145">Displays the application, component, and interface information as IDs.</span></span><br /><br /> <span data-ttu-id="e132f-146">Kurzform: `/k`.</span><span class="sxs-lookup"><span data-stu-id="e132f-146">Short form `/k`.</span></span>|  
|`/nologo`|<span data-ttu-id="e132f-147">Verhindert, dass ComSvcConfig.exe sein Logo anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e132f-147">Prevents ComSvcConfig.exe from displaying its logo.</span></span><br /><br /> <span data-ttu-id="e132f-148">Kurzform: `/n`.</span><span class="sxs-lookup"><span data-stu-id="e132f-148">Short form `/n`.</span></span>|  
|`/verbose`|<span data-ttu-id="e132f-149">Gibt alle Warnungen oder Informationsmeldungen zusätzlich zu gefundenen Fehlern aus.</span><span class="sxs-lookup"><span data-stu-id="e132f-149">Outputs all warnings or informational text in addition to any errors encountered.</span></span><br /><br /> <span data-ttu-id="e132f-150">Kurzform: `/v`.</span><span class="sxs-lookup"><span data-stu-id="e132f-150">Short form `/v`.</span></span>|  
|`/help`|<span data-ttu-id="e132f-151">Zeigt die Syntaxmeldung an.</span><span class="sxs-lookup"><span data-stu-id="e132f-151">Displays the usage message.</span></span><br /><br /> <span data-ttu-id="e132f-152">Kurzform: `/?`.</span><span class="sxs-lookup"><span data-stu-id="e132f-152">Short form `/?`.</span></span>|  
|`/partial`|<span data-ttu-id="e132f-153">Generiert eine Dienstkonfiguration, wenn die angegebene Schnittstelle ein oder mehr Methodensignaturen umfasst, die verfügbar gemacht werden können.</span><span class="sxs-lookup"><span data-stu-id="e132f-153">Generates a service configuration when the specified interface includes one or more method signatures that can be exposed.</span></span> <span data-ttu-id="e132f-154">Zum Zeitpunkt der Dienstinitialisierung werden kompatible Methoden als Vorgänge für den Dienstvertrag angezeigt, und nicht kompatible Methoden werden ignoriert und gelten als nicht vorhanden für den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="e132f-154">At service initialization time, compatible methods appear as operations on the service contract, and non-compatible methods are ignored and absent from the service contract.</span></span><br /><br /> <span data-ttu-id="e132f-155">Fehlt das Flag, generiert das Tool keine Dienstkonfiguration, wenn die angegebene Schnittstelle ein oder mehr inkompatible Methoden umfasst.</span><span class="sxs-lookup"><span data-stu-id="e132f-155">If this flag is missing, the tool will not generate a service configuration when the specified interface includes one or more incompatible methods.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="e132f-156">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e132f-156">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="e132f-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e132f-157">Description</span></span>  
 <span data-ttu-id="e132f-158">Im folgenden Beispiel wird die `IFinances`-Schnittstelle der `ItemOrders.IFinancial`-Komponente (aus der OnlineStore-COM+-Anwendung) mithilfe des COM+-Hostingmodus der Gruppe von Schnittstellen hinzugefügt, die als Webdienste verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e132f-158">The following example adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that are exposed as Web services, using the COM+ hosting mode.</span></span> <span data-ttu-id="e132f-159">Alle Warnungen werden zusätzlich zu gefundenen Fehlern ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="e132f-159">All warnings will be output in addition to any errors encountered.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e132f-160">Code</span><span class="sxs-lookup"><span data-stu-id="e132f-160">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a><span data-ttu-id="e132f-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e132f-161">Description</span></span>  
 <span data-ttu-id="e132f-162">Im folgenden Beispiel wird die `IStockLevels`-Schnittstelle der `ItemInventory.Warehouse`-Komponente (aus der OnlineWarehouse-COM+-Anwendung) mithilfe des Webhostingmodus der Gruppe von Schnittstellen hinzugefügt, die als Webdienste verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e132f-162">The following example adds the `IStockLevels` interface of the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that are exposed as Web services, using the Web hosting mode.</span></span> <span data-ttu-id="e132f-163">Der Webdienst wird im virtuellen IIS-Verzeichnis OnlineWarehouse gehostet.</span><span class="sxs-lookup"><span data-stu-id="e132f-163">The Web service is Web hosted in the OnlineWarehouse virtual directory of IIS.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e132f-164">Code</span><span class="sxs-lookup"><span data-stu-id="e132f-164">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a><span data-ttu-id="e132f-165">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e132f-165">Description</span></span>  
 <span data-ttu-id="e132f-166">Im folgenden Beispiel wird die `IFinances`-Schnittstelle der `ItemOrders.Financial`-Komponente (aus der OnlineStore-COM+-Anwendung) aus der Gruppe von Schnittstellen entfernt, die als Webdienste verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="e132f-166">The following example removes the `IFinances` interface of the `ItemOrders.Financial` component (from the OnlineStore COM+ application) from the set of interfaces that are exposed as Web services.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e132f-167">Code</span><span class="sxs-lookup"><span data-stu-id="e132f-167">Code</span></span>  
  
```  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a><span data-ttu-id="e132f-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e132f-168">Description</span></span>  
 <span data-ttu-id="e132f-169">Im folgenden Beispiel werden die derzeit verfügbar gemachten COM+-gehosteten Schnittstellen zusammen mit den entsprechenden Adress- und Bindungsdetails für die OnlineStore-COM+-Anwendung auf dem lokalen Computer aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e132f-169">The following example lists currently exposed COM+ hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e132f-170">Code</span><span class="sxs-lookup"><span data-stu-id="e132f-170">Code</span></span>  
  
```  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a><span data-ttu-id="e132f-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e132f-171">See also</span></span>

- [<span data-ttu-id="e132f-172">Vorgehensweise: Verwenden Sie das COM+ Service Model Configuration-Tool</span><span class="sxs-lookup"><span data-stu-id="e132f-172">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
