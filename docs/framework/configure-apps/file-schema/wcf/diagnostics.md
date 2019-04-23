---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 3fc7828d399555f7c459f6dd067ce9a24b8998b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108029"
---
# <a name="diagnostics"></a><span data-ttu-id="07087-101">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="07087-101">\<diagnostics></span></span>
<span data-ttu-id="07087-102">Das `diagnostics`-Element definiert Einstellungen, die von einem Administrator zur Laufzeitüberprüfung und -steuerung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="07087-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="07087-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="07087-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="07087-104">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="07087-104">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07087-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="07087-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07087-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07087-106">Attributes and Elements</span></span>  
 <span data-ttu-id="07087-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07087-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07087-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="07087-108">Attributes</span></span>  
  
|<span data-ttu-id="07087-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="07087-109">Attribute</span></span>|<span data-ttu-id="07087-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07087-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07087-111">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="07087-111">etwProviderId</span></span>|<span data-ttu-id="07087-112">Eine Zeichenfolge, die den Bezeichner für den Anbieter der Ereignisablaufverfolgung angibt, der Ereignisse in ETW-Sitzungen schreibt.</span><span class="sxs-lookup"><span data-stu-id="07087-112">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="07087-113">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="07087-113">performanceCounters</span></span>|<span data-ttu-id="07087-114">Gibt an, ob die Leistungsindikatoren für die Assembly aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="07087-114">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="07087-115">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="07087-115">Valid values are</span></span><br /><br /> <span data-ttu-id="07087-116">-Deaktiviert: Leistungsindikatoren sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="07087-116">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="07087-117">-ServiceOnly: Nur Leistungsindikatoren für diesen Dienst sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="07087-117">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="07087-118">– Alle: Leistungsindikatoren können zur Laufzeit angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="07087-118">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="07087-119">– Default: Die einzelne Leistungsindikatorinstanz _WCF_Admin wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="07087-119">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="07087-120">Diese Instanz wird verwendet, um die Auflistung der SQM-Daten für die Verwendung durch die Infrastruktur zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="07087-120">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="07087-121">Die Indikatorwerte für diese Instanz werden nicht aktualisiert und bleiben deshalb auf null.</span><span class="sxs-lookup"><span data-stu-id="07087-121">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="07087-122">Dies ist der Standardwert, wenn keine Konfiguration für WCF vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="07087-122">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="07087-123">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="07087-123">wmiProviderEnabled</span></span>|<span data-ttu-id="07087-124">Ein boolescher Wert, der angibt, ob der WMI-Anbieter für die Assembly aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="07087-124">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="07087-125">Der WMI-Anbieter ist für Benutzer erforderlich, um Laufzeitzugriff auf die Überprüfungs- und Steuerungsfunktionen von Windows Communication Foundation (WCF) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="07087-125">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="07087-126">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="07087-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07087-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07087-127">Child Elements</span></span>  
  
|<span data-ttu-id="07087-128">Element</span><span class="sxs-lookup"><span data-stu-id="07087-128">Element</span></span>|<span data-ttu-id="07087-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07087-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07087-130">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="07087-130">\<endToEndTracing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|<span data-ttu-id="07087-131">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="07087-131">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="07087-132">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="07087-132">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|<span data-ttu-id="07087-133">Beschreibt die Einstellungen für die WCF-Nachrichtenprotokollierung.</span><span class="sxs-lookup"><span data-stu-id="07087-133">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07087-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07087-134">Parent Elements</span></span>  
  
|<span data-ttu-id="07087-135">Element</span><span class="sxs-lookup"><span data-stu-id="07087-135">Element</span></span>|<span data-ttu-id="07087-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07087-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="07087-137">serviceModel</span><span class="sxs-lookup"><span data-stu-id="07087-137">serviceModel</span></span>|<span data-ttu-id="07087-138">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="07087-138">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07087-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07087-139">Remarks</span></span>  
 <span data-ttu-id="07087-140">Der `diagnostics`-Abschnitt definiert die Diagnoseeinstellungen für alle Dienste in einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="07087-140">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="07087-141">Es ist nicht möglich, separate Diagnoseeinstellungen auf Dienstebene zu definieren, es sei denn, es befindet sich nur ein Dienst in der Assembly.</span><span class="sxs-lookup"><span data-stu-id="07087-141">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="07087-142">Attribute werden gemäß den Anforderungen des Abschnitts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="07087-142">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07087-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07087-143">Example</span></span>  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
  <messageLogging logEntireMessage="true"
                  logMalformedMessages="true"
                  logMessagesAtServiceLevel="true"
                  logMessagesAtTransportLevel="true"
                  maxMessagesToLog="42"
                  maxSizeOfMessageToLog="42">
    <filters>
      <clear />
    </filters>
  </messageLogging>
</diagnostics>
```  
  
## <a name="see-also"></a><span data-ttu-id="07087-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07087-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
