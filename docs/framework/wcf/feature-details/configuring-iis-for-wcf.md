---
title: Konfigurieren von Internetinformationsdienste 7.0 für Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 6b0cc48c7a817f71339fb6d7eea35baf1d97b245
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556654"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a><span data-ttu-id="3566d-102">Konfigurieren von Internetinformationsdienste 7.0 für Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="3566d-102">Configuring Internet Information Services 7.0 for Windows Communication Foundation</span></span>

<span data-ttu-id="3566d-103">Internetinformationsdienste (IIS) 7.0 weist einen modularen Aufbau auf, der es Ihnen ermöglicht, die benötigten Komponenten selektiv zu installieren.</span><span class="sxs-lookup"><span data-stu-id="3566d-103">Internet Information Services (IIS) 7.0 has a modular design that allows you to selectively install components that are required.</span></span> <span data-ttu-id="3566d-104">Dieser Entwurf basiert auf der neuen, in Windows Vista eingeführten manifestressorisierungstechnologie.</span><span class="sxs-lookup"><span data-stu-id="3566d-104">This design is based on the new manifest-driven componentization technology introduced in Windows Vista.</span></span> <span data-ttu-id="3566d-105">Es gibt mehr als 40 eigenständige Funktionskomponenten von IIS 7,0, die unabhängig installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="3566d-105">There are more than 40 standalone feature components of IIS 7.0 that can be installed independently.</span></span> <span data-ttu-id="3566d-106">Dies ermöglicht es IT-Profis, die Installation problemlos nach Bedarf anzupassen.</span><span class="sxs-lookup"><span data-stu-id="3566d-106">This allows IT professionals to easily customize the installation as required.</span></span> <span data-ttu-id="3566d-107">In diesem Thema wird erläutert, wie Sie IIS 7,0 für die Verwendung mit Windows Communication Foundation (WCF) konfigurieren und ermitteln, welche Komponenten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3566d-107">This topic discusses how to configure IIS 7.0 for use with Windows Communication Foundation (WCF) and determine which components are required.</span></span>

## <a name="minimal-installation-installing-was"></a><span data-ttu-id="3566d-108">Minimale Installation: Installieren von WAS</span><span class="sxs-lookup"><span data-stu-id="3566d-108">Minimal Installation: Installing WAS</span></span>
 <span data-ttu-id="3566d-109">Die minimale Installation des gesamten IIS 7,0-Pakets besteht darin, den Windows-Prozess Aktivierungs Dienst (was) zu installieren.</span><span class="sxs-lookup"><span data-stu-id="3566d-109">The minimal installation of the whole IIS 7.0 package is to install the Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="3566d-110">Was ist ein eigenständiges Feature, das das einzige Feature von IIS 7,0 ist, das für alle Windows Vista-Betriebssysteme (Home Basic, Home Premium, Business und Ultimate und Enterprise) verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3566d-110">WAS is a standalone feature and it is the only feature from the IIS 7.0 that is available for all Windows Vista operating systems (Home Basic, Home Premium, Business, and Ultimate and Enterprise).</span></span>

 <span data-ttu-id="3566d-111">Klicken Sie in der Systemsteuerung auf **Programme** und dann **auf Windows-Funktionen ein-oder ausschalten** , die unter **Programme und Funktionen**aufgeführt sind. die was-Komponente wird in der Liste wie in der folgenden Abbildung dargestellt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3566d-111">From the Control Panel, click **Programs** and then click **Turn Windows features on or off** which is listed under **Programs and Features**, the WAS component is shown in the list as in the following illustration.</span></span>

 <span data-ttu-id="3566d-112">![Dialogfeld zum Aktivieren oder Deaktivieren von Funktionen](media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span><span class="sxs-lookup"><span data-stu-id="3566d-112">![Turn Features On or Off Dialog](media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span></span>

 <span data-ttu-id="3566d-113">Diese Funktion weist die folgenden untergeordneten Komponenten auf:</span><span class="sxs-lookup"><span data-stu-id="3566d-113">This feature has the following sub-components:</span></span>

- <span data-ttu-id="3566d-114">.NET-Umgebung</span><span class="sxs-lookup"><span data-stu-id="3566d-114">.NET Environment</span></span>

- <span data-ttu-id="3566d-115">Konfiguration-APIs</span><span class="sxs-lookup"><span data-stu-id="3566d-115">Configuration APIs</span></span>

- <span data-ttu-id="3566d-116">Prozessmodell</span><span class="sxs-lookup"><span data-stu-id="3566d-116">Process Model</span></span>

 <span data-ttu-id="3566d-117">Wenn Sie den Stamm Knoten von was ausgewählt haben, ist nur der untergeordnete Knoten **Prozessmodell** standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3566d-117">If you select the root node of WAS, only the **Process Model** sub-node is checked by default.</span></span> <span data-ttu-id="3566d-118">Beachten Sie, dass Sie mit dieser Installation lediglich WAS installieren, da kein Webserver unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="3566d-118">Please note that with this installation you are only installing WAS, because there is no support for a Web server.</span></span>

 <span data-ttu-id="3566d-119">Aktivieren Sie das Kontrollkästchen **.NET-Umgebung** , damit WCF oder eine beliebige ASP.NET-Anwendung funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3566d-119">To make WCF or any ASP.NET application work, check the **.NET Environment** checkbox.</span></span> <span data-ttu-id="3566d-120">Dies bedeutet, dass alle was-Komponenten erforderlich sind, damit WCF und ASP.net ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3566d-120">This means that all of WAS components are required to make WCF and ASP.NET to work well.</span></span> <span data-ttu-id="3566d-121">Diese werden automatisch überprüft, sobald Sie eine dieser Komponenten installieren.</span><span class="sxs-lookup"><span data-stu-id="3566d-121">These are automatically checked once you install any of those components.</span></span>

## <a name="iis-70-default-installation"></a><span data-ttu-id="3566d-122">IIS 7.0: Standardinstallation</span><span class="sxs-lookup"><span data-stu-id="3566d-122">IIS 7.0: Default Installation</span></span>
 <span data-ttu-id="3566d-123">Wenn Sie die **Internetinformationsdienste** Funktion aktivieren, werden einige der untergeordneten Knoten automatisch überprüft, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3566d-123">By checking the **Internet Information Services** feature, some of the sub-nodes are automatically checked as shown in the following illustration.</span></span>

 <span data-ttu-id="3566d-124">![Standardeinstellungen für IIS 7.0-Funktionen](media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span><span class="sxs-lookup"><span data-stu-id="3566d-124">![Default settings for IIS 7.0 features](media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span></span>

 <span data-ttu-id="3566d-125">Dies ist die Standardinstallation von IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="3566d-125">This is the default installation of IIS 7.0.</span></span> <span data-ttu-id="3566d-126">Mit dieser Installation können Sie IIS 7,0 verwenden, um statische Inhalte (z. b. HTML-Seiten und anderen Inhalt) zu bedienen.</span><span class="sxs-lookup"><span data-stu-id="3566d-126">With this installation, you can use IIS 7.0 to service static content (such as HTML pages and other content).</span></span> <span data-ttu-id="3566d-127">Sie können jedoch keine ASP.net-oder CGI-Anwendungen ausführen oder WCF-Dienste hosten.</span><span class="sxs-lookup"><span data-stu-id="3566d-127">However, you cannot run ASP.NET or CGI applications or host WCF services.</span></span>

## <a name="iis-70-installation-with-aspnet-support"></a><span data-ttu-id="3566d-128">IIS 7.0: Installation mit ASP.NET-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="3566d-128">IIS 7.0: Installation with ASP.NET Support</span></span>
 <span data-ttu-id="3566d-129">Sie müssen ASP.NET installieren, damit ASP.net auf IIS 7,0 funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3566d-129">You must install ASP.NET to make ASP.NET work on IIS 7.0.</span></span> <span data-ttu-id="3566d-130">Nachdem Sie **ASP.net**überprüft haben, sollte der Bildschirm wie in der folgenden Abbildung aussehen.</span><span class="sxs-lookup"><span data-stu-id="3566d-130">After checking **ASP.NET**, your screen should look like the following illustration.</span></span>

 <span data-ttu-id="3566d-131">![Für ASP.NET erforderliche Einstellungen](media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span><span class="sxs-lookup"><span data-stu-id="3566d-131">![Asp.NET required settings](media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span></span>

 <span data-ttu-id="3566d-132">Dies ist die minimale Umgebung für WCF-und ASP.NET-Anwendungen, die in IIS 7,0 funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3566d-132">This is the minimal environment for both WCF and ASP.NET applications to work in IIS 7.0.</span></span>

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a><span data-ttu-id="3566d-133">IIS 7.0: Installation mit IIS 6.0-Kompatibilitätskomponenten</span><span class="sxs-lookup"><span data-stu-id="3566d-133">IIS 7.0: Installation with IIS 6.0 Compatibility Components</span></span>
 <span data-ttu-id="3566d-134">Bei der Installation von IIS 7,0 auf einem System mit Visual Studio 2005 oder einigen anderen Automatisierungs Skripts oder Tools (z. b. Adsutil. vb), die virtuelle Anwendungen konfigurieren, die die IIS 6,0-Metabasis-API verwenden, müssen Sie die IIS 6,0- **Skript Tools**überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3566d-134">When installing IIS 7.0 on a system with Visual Studio 2005 or some other automation scripts or tools (such as Adsutil.vbs) that configure virtual applications that use IIS 6.0 Metabase API, ensure that you check the IIS 6.0 **Scripting Tools**.</span></span> <span data-ttu-id="3566d-135">Hierdurch werden automatisch die anderen untergeordneten Knoten der IIS 6,0- **Verwaltungs Kompatibilität**überprüft.</span><span class="sxs-lookup"><span data-stu-id="3566d-135">This automatically checks the other sub-nodes of IIS 6.0 **Management Compatibility**.</span></span> <span data-ttu-id="3566d-136">Die folgende Abbildung zeigt den Bildschirm, nachdem dieser Vorgang abgeschlossen wurde:</span><span class="sxs-lookup"><span data-stu-id="3566d-136">The following illustration shows the screen after this is done:</span></span>

 <span data-ttu-id="3566d-137">![Einstellungen der IIS 6.0-Verwaltungskompatibilität](media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span><span class="sxs-lookup"><span data-stu-id="3566d-137">![IIS 6.0 Management Compatibility Settings](media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span></span>

 <span data-ttu-id="3566d-138">Mit dieser Installation haben Sie alles, was Sie für die Verwendung von IIS 7,0, ASP.net und WCF-Features und-Beispielen benötigen, die im Web verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3566d-138">With this installation, you have everything required to use IIS 7.0, ASP.NET and WCF features and samples available on the Web.</span></span>

## <a name="request-limits"></a><span data-ttu-id="3566d-139">Anforderungsbeschränkungen</span><span class="sxs-lookup"><span data-stu-id="3566d-139">Request Limits</span></span>
 <span data-ttu-id="3566d-140">Unter Windows Vista mit IIS 7 wurde der Standardwert der `maxUri` `maxQueryStringSize` Einstellungen und geändert.</span><span class="sxs-lookup"><span data-stu-id="3566d-140">On Windows Vista with IIS 7 the default value of the `maxUri` and `maxQueryStringSize` settings have been changed.</span></span> <span data-ttu-id="3566d-141">Standardmäßig sind in Anforderungsfiltern in IIS 7.0 eine URL-Länge von 4096 Zeichen und Abfragezeichenfolgen mit einer Länge von 2048 Zeichen zulässig.</span><span class="sxs-lookup"><span data-stu-id="3566d-141">By default, request filtering in IIS 7.0 allows a URL length of 4096 characters and a query string length of 2048 characters.</span></span> <span data-ttu-id="3566d-142">Um diese Standardwerte zu ändern, fügen Sie das folgende XML der Datei App.config hinzu.</span><span class="sxs-lookup"><span data-stu-id="3566d-142">To change these defaults add the following XML to your App.config file.</span></span>

```xml
 <system.webServer>
    <security>
        <requestFiltering>
            <requestLimits maxUrl="8192" maxQueryString="8192" />
        </requestFiltering>
    </security>
 </system.webServer>
 ```

## <a name="see-also"></a><span data-ttu-id="3566d-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3566d-143">See also</span></span>

- [<span data-ttu-id="3566d-144">WAS-Aktivierungsarchitektur</span><span class="sxs-lookup"><span data-stu-id="3566d-144">WAS Activation Architecture</span></span>](was-activation-architecture.md)
- [<span data-ttu-id="3566d-145">Konfigurieren von WAS für die Verwendung mit WCF</span><span class="sxs-lookup"><span data-stu-id="3566d-145">Configuring WAS for Use with WCF</span></span>](configuring-the-wpa--service-for-use-with-wcf.md)
- [<span data-ttu-id="3566d-146">Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten</span><span class="sxs-lookup"><span data-stu-id="3566d-146">How to: Install and Configure WCF Activation Components</span></span>](how-to-install-and-configure-wcf-activation-components.md)
- <span data-ttu-id="3566d-147">[Windows Server AppFabric-Hostingfunktionen](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3566d-147">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
