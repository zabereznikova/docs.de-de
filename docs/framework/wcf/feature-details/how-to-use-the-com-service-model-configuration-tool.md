---
title: 'Vorgehensweise: Verwenden des COM+-Dienstmodell-Konfigurationstools'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], using service model configuration tool
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
ms.openlocfilehash: f9e761bafd84726b51a2010a932c68c67c37f899
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595283"
---
# <a name="how-to-use-the-com-service-model-configuration-tool"></a><span data-ttu-id="4756d-102">Vorgehensweise: Verwenden des COM+-Dienstmodell-Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="4756d-102">How to: Use the COM+ Service Model Configuration Tool</span></span>
<span data-ttu-id="4756d-103">Nachdem Sie einen geeigneten Hosting-Modus ausgewählt haben, verwenden Sie das COM+-Dienstmodell-Konfigurations-Befehlszeilentool (ComSvcConfig.exe) zur Konfigurierung der Anwendungsschnittstellen, die als Webdienste verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="4756d-103">Once you have selected an appropriate hosting mode, use the COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) to configure the application interfaces that will be exposed as Web services.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4756d-104">Sie müssen über Administratorrechte verfügen, um die folgenden Aufgaben auszuführen zu können.</span><span class="sxs-lookup"><span data-stu-id="4756d-104">You must be an administrator on the machine to perform any of the following tasks.</span></span>  
  
 <span data-ttu-id="4756d-105">Wenn Sie ComSvcConfig.exe auf einem Windows 7-Computer verwenden, um einen Webdienst für die Verwendung der neuesten Dienstmodellversion (derzeit 4.5) zu konfigurieren, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4756d-105">When using ComSvcConfig.exe on a Windows 7 machine to configure a web service to use the latest service model version (currently v4.5), perform the following steps:</span></span>  
  
1. <span data-ttu-id="4756d-106">Legen Sie den Registrierungsschlüssel `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` auf den DWORD-Wert 0x00000001 fest.</span><span class="sxs-lookup"><span data-stu-id="4756d-106">Set the registry key  `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` to a DWORD value of 0x00000001</span></span>  
  
2. <span data-ttu-id="4756d-107">Führen Sie comsvcconfig.exe aus.</span><span class="sxs-lookup"><span data-stu-id="4756d-107">Run comsvcconfig.exe</span></span>  
  
3. <span data-ttu-id="4756d-108">Legen Sie den in Schritt 1 festgelegten Registrierungsschlüssel wieder auf den ursprünglichen Wert fest, oder löschen Sie ihn, wenn er nicht vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="4756d-108">Revert the registry key added in step 1 back to its original value, or delete it if did not exist.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4756d-109">Es ist wichtig, diesen Registrierungsschlüssel wieder zurückzuversetzen, weil er einen</span><span class="sxs-lookup"><span data-stu-id="4756d-109">Reverting this registry key is important.</span></span> <span data-ttu-id="4756d-110">Kompatibilitätsschlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="4756d-110">This is a compatibility key.</span></span> <span data-ttu-id="4756d-111">Wird diese Änderung nicht rückgängig gemacht, können Probleme mit anderen .NET-Anwendungen auftreten, die auf dem Computer ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="4756d-111">Not reverting this change may cause issues with other .NET applications running on the machine).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="4756d-112">Bei der Verwendung von ComSvcConfig. exe/install auf einem Windows 8-Computer wird ein Dialogfeld mit dem Hinweis angezeigt, dass für eine APP auf Ihrem PC Folgendes Windows-Feature erforderlich ist: .NET Framework 3,5 (enthält .NET 2,0 und .NET 3,0), wenn .NET Framework 3,5 nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4756d-112">When using ComSvcConfig.exe  /install on a Windows 8 machine a dialog is displayed stating "An app on your PC needs the following Windows feature: .NET Framework 3.5 (includes .NET 2.0 and .NET 3.0" if .NET Framework 3.5 is not installed.</span></span> <span data-ttu-id="4756d-113">Dieses Dialogfeld kann ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="4756d-113">This dialog may be ignored.</span></span> <span data-ttu-id="4756d-114">Alternativ können Sie den OnlyUseLatestCLR-Registrierungsschlüssel auf den DWORD-Wert 0x00000001 festlegen.</span><span class="sxs-lookup"><span data-stu-id="4756d-114">Alternatively you can sed the OnlyUseLatestCLR registry key to a DWORD value of 0x00000001</span></span>  
  
## <a name="to-add-an-interface-to-the-set-of-interfaces-exposed-as-web-services-using-the-com-hosting-mode"></a><span data-ttu-id="4756d-115">So fügen Sie dem Satz von Schnittstellen, die als Webdienste verfügbar gemacht werden, mithilfe des COM+-Hostingmodus eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4756d-115">To add an interface to the set of interfaces exposed as Web services, using the COM+ hosting mode</span></span>  
  
- <span data-ttu-id="4756d-116">Führen Sie ComSvcConfig mithilfe der `/install`- und der `/hosting:complus`-Optionen aus, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4756d-116">Run ComSvcConfig using the `/install` and `/hosting:complus` options, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
    ```  
  
     <span data-ttu-id="4756d-117">Der Befehl fügt die `IFinances`-Schnittstelle der `ItemOrders.IFinancial`-Komponente (aus der OnlineStore-COM+-Anwendung) zu der Gruppe von Schnittstellen hinzu, die als Webdienste verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="4756d-117">The command adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="4756d-118">Der Dienst verwendet den COM+-Hostingmodus und erfordert deshalb eine explizite Anwendungsaktivierung.</span><span class="sxs-lookup"><span data-stu-id="4756d-118">The service uses the COM+ hosting mode and therefore requires explicit application activation.</span></span>  
  
     <span data-ttu-id="4756d-119">Das Platzhalter Sternchen ( \* ) kann für die-Komponente und die-Schnittstelle verwendet werden, sollten Sie jedoch nicht verwenden, da Sie möglicherweise nur ausgewählte Funktionen als Webdienst verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="4756d-119">While the wildcard asterisk (\*) character can be used for the component and the interface, avoid using it because you might want to expose only selected functionality as a Web service.</span></span> <span data-ttu-id="4756d-120">Bei der Ausführung mit einer künftigen Version dieser Komponente kann die Verwendung des Platzhalters unbeabsichtigt Schnittstellen verfügbar machen, die noch nicht vorhanden waren, als die Konfigurationssyntax festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4756d-120">If run with a future version of this component, using the wildcard may unintentionally expose interfaces that may not have been present when the configuration syntax was determined.</span></span>  
  
     <span data-ttu-id="4756d-121">Die Option für die ausführliche Ausgabe weist das Tool an, zusätzlich zu Fehlern Warnungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4756d-121">The /verbose option instructs the tool to display warnings in addition to any errors.</span></span>  
  
     <span data-ttu-id="4756d-122">Der Vertrag für den verfügbar gemachten Dienst enthält alle Methoden aus der `IFinances`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4756d-122">The contract for the exposed service will contain all of the methods from the `IFinances` interface.</span></span>  
  
## <a name="to-add-only-specific-methods-from-an-interface-to-the-set-of-interfaces-exposed-as-web-services-using-the-com-hosting-mode"></a><span data-ttu-id="4756d-123">So fügen Sie der Gruppe von Schnittstellen, die als Webdienste verfügbar gemacht werden, mithilfe des COM+-Hostingmodus nur bestimmte Methoden aus einer Schnittstelle hinzu</span><span class="sxs-lookup"><span data-stu-id="4756d-123">To add only specific methods from an interface to the set of interfaces exposed as Web services, using the COM+ hosting mode</span></span>  
  
- <span data-ttu-id="4756d-124">Führen Sie ComSvcConfig mithilfe der `/install`- und der `/hosting:complus`-Optionen mit expliziter Benennung der erforderlichen Methoden aus, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4756d-124">Run ComSvcConfig using the `/install` and `/hosting:complus` options with explicit naming of the required methods, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose  
    ```  
  
     <span data-ttu-id="4756d-125">Der Befehl fügt nur die `Credit`- und die `Debit`-Methode der `IFinances`-Schnittstelle als Vorgänge zu dem verfügbar gemachten Dienstvertrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="4756d-125">The command adds only the `Credit` and `Debit` methods from the `IFinances` interface as operations to the exposed service contract.</span></span> <span data-ttu-id="4756d-126">Alle anderen Methoden der Schnittstelle erscheinen nicht im Vertrag und können von Webdienstclients nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4756d-126">All other methods on the interface will be omitted from the contract and will not be callable from Web service clients.</span></span>  
  
## <a name="to-add-an-interface-to-the-set-of-interfaces-exposed-as-web-services-using-the-web-hosting-mode"></a><span data-ttu-id="4756d-127">So fügen Sie eine Schnittstelle zum Satz von Schnittstellen hinzu, die als Webdienste verfügbar gemacht werden, mithilfe des Webhostingmodus</span><span class="sxs-lookup"><span data-stu-id="4756d-127">To add an interface to the set of interfaces exposed as Web services, using the Web hosting mode</span></span>  
  
- <span data-ttu-id="4756d-128">Führen Sie ComSvcConfig mithilfe der `/install`- und der `/hosting:was`-Option aus, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4756d-128">Run ComSvcConfig using the `/install` option and the `/hosting:was` option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose  
    ```  
  
     <span data-ttu-id="4756d-129">Der Befehl fügt die `IStockLevels`-Schnittstelle der `ItemInventory.Warehouse`-Komponente (aus der OnlineWarehouse-COM+-Anwendung) zu der Gruppe von Schnittstellen hinzu, die als Webdienste verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="4756d-129">The command adds the `IStockLevels` interface on the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="4756d-130">Statt in COM+ wird der Dienst im virtuellen OnlineWarehouse-Verzeichnis von IIS im Internet gehostet, und folglich wird die Anwendung automatisch bei Bedarf aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4756d-130">The service is Web hosted in the OnlineWarehouse virtual directory of IIS rather than in COM+, and thus the application is automatically activated as required.</span></span>  
  
     <span data-ttu-id="4756d-131">Um die im Internet gehostete prozessinterne Konfiguration zu verwenden, muss die COM+-Anwendung mithilfe der Verwaltungskonsole Komponentendienste so konfiguriert werden, dass sie als Library-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4756d-131">To use the Web-hosted in-process configuration, the COM+ application must be configured to run as a Library application rather than a Server application using the Component Services administration console.</span></span> <span data-ttu-id="4756d-132">Anwendungen, die als Serveranwendungen konfiguriert werden, werden standardmäßig im Internet gehostet und bewirken einen Prozesshop für die Verarbeitung jeder Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4756d-132">Applications configured as Server applications use the standard Web-hosted mode and incur a process hop to process each request.</span></span>  
  
     <span data-ttu-id="4756d-133">Die `/mex`-Option fügt einen zusätzlichen Metadatenaustausch-Dienstendpunkt (MEX oder Metadata Exchange) hinzu, der denselben Transport verwendet wie der Dienstendpunkt der Anwendung, um Clients beim Abrufen einer Vertragsdefinition vom Dienst zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4756d-133">The `/mex` option adds an additional Metadata Exchange (MEX) service endpoint that uses the same transport as the application's service endpoint to support clients that want to retrieve a contract definition from the service.</span></span>  
  
## <a name="to-remove-a-web-service-for-a-specified-interface"></a><span data-ttu-id="4756d-134">Entfernen eines Webdiensts aus einer angegebenen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4756d-134">To remove a Web service for a specified interface</span></span>  
  
- <span data-ttu-id="4756d-135">Führen Sie ComSvcConfig mithilfe der `/uninstall`-Optionen aus, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4756d-135">Run ComSvcConfig using the `/uninstall` option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus  
    ```  
  
     <span data-ttu-id="4756d-136">Der Befehl entfernt die `IFinances`-Schnittstelle in der `ItemOrders.Financial`-Komponente (aus der OnlineStore-COM+-Anwendung).</span><span class="sxs-lookup"><span data-stu-id="4756d-136">The command removes the `IFinances` interface on the `ItemOrders.Financial` component (from the OnlineStore COM+ application).</span></span>  
  
## <a name="to-list-currently-exposed-interfaces"></a><span data-ttu-id="4756d-137">So listen Sie zurzeit verfügbare Schnittstellen auf</span><span class="sxs-lookup"><span data-stu-id="4756d-137">To list currently exposed interfaces</span></span>  
  
- <span data-ttu-id="4756d-138">Führen Sie ComSvcConfig mithilfe der `/list`-Optionen aus, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4756d-138">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /list  
    ```  
  
     <span data-ttu-id="4756d-139">Der Befehl listet die derzeit verfügbaren Schnittstellen zusammen mit den entsprechenden Adress- und Bindungsdetails auf, deren Gültigkeitsbereich der lokale Computer ist.</span><span class="sxs-lookup"><span data-stu-id="4756d-139">The command lists the currently exposed interfaces, along with the corresponding address and binding details, scoped to the local machine.</span></span>  
  
## <a name="to-list-specific-currently-exposed-interfaces"></a><span data-ttu-id="4756d-140">So listen Sie bestimmte zurzeit verfügbare Schnittstellen auf</span><span class="sxs-lookup"><span data-stu-id="4756d-140">To list specific currently exposed interfaces</span></span>  
  
- <span data-ttu-id="4756d-141">Führen Sie ComSvcConfig mithilfe der `/list`-Optionen aus, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4756d-141">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
    ```  
  
     <span data-ttu-id="4756d-142">Der Befehl listet derzeit verfügbare COM+-gehostete Schnittstellen zusammen mit den entsprechenden Adress- und Bindungsdetails für die OnlineStore-COM+-Anwendung auf dem lokalen Computer auf.</span><span class="sxs-lookup"><span data-stu-id="4756d-142">The command lists currently exposed COM+-hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
## <a name="to-display-help-on-the-options-that-can-be-used-with-the-utility"></a><span data-ttu-id="4756d-143">So zeigen Sie Hilfe in den Optionen an, die mit dem Hilfsprogramm verwendet werden können</span><span class="sxs-lookup"><span data-stu-id="4756d-143">To display help on the options that can be used with the utility</span></span>  
  
- <span data-ttu-id="4756d-144">Führen Sie ComSvcConfig mithilfe der /?</span><span class="sxs-lookup"><span data-stu-id="4756d-144">Run ComSvcConfig using the /?</span></span> <span data-ttu-id="4756d-145">-Option aus, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4756d-145">option, as shown in the following example.</span></span>  
  
    ```console  
    ComSvcConfig.exe /?  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4756d-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4756d-146">See also</span></span>

- [<span data-ttu-id="4756d-147">Übersicht über die Integration von com+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="4756d-147">Integrating with COM+ Applications Overview</span></span>](integrating-with-com-plus-applications-overview.md)
