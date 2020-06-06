---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 2749bc6c66d491a8a160d98b508fb43aa027b806
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398045"
---
# \<diagnostics>
<span data-ttu-id="f5fcb-101">Das `diagnostics`-Element definiert Einstellungen, die von einem Administrator zur Laufzeitüberprüfung und -steuerung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-101">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="f5fcb-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5fcb-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5fcb-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f5fcb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f5fcb-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5fcb-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="f5fcb-105">Attributes</span></span>  
  
|<span data-ttu-id="f5fcb-106">attribute</span><span class="sxs-lookup"><span data-stu-id="f5fcb-106">Attribute</span></span>|<span data-ttu-id="f5fcb-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f5fcb-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5fcb-108">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="f5fcb-108">etwProviderId</span></span>|<span data-ttu-id="f5fcb-109">Eine Zeichenfolge, die den Bezeichner für den Anbieter der Ereignisablaufverfolgung angibt, der Ereignisse in ETW-Sitzungen schreibt.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-109">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="f5fcb-110">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="f5fcb-110">performanceCounters</span></span>|<span data-ttu-id="f5fcb-111">Gibt an, ob die Leistungsindikatoren für die Assembly aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-111">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="f5fcb-112">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="f5fcb-112">Valid values are</span></span><br /><br /> <span data-ttu-id="f5fcb-113">-Off: Leistungsindikatoren sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-113">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="f5fcb-114">-ServiceOnly: nur Leistungsindikatoren, die für diesen Dienst relevant sind, sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-114">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="f5fcb-115">-All: Leistungsindikatoren können zur Laufzeit angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-115">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="f5fcb-116">-Default: Es wird eine einzelne Instanz _WCF_Admin der Leistungs Instanz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-116">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="f5fcb-117">Diese Instanz wird verwendet, um die Auflistung der SQM-Daten für die Verwendung durch die Infrastruktur zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-117">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="f5fcb-118">Die Indikatorwerte für diese Instanz werden nicht aktualisiert und bleiben deshalb auf null.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-118">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="f5fcb-119">Dies ist der Standardwert, wenn keine Konfiguration für WCF vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-119">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="f5fcb-120">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="f5fcb-120">wmiProviderEnabled</span></span>|<span data-ttu-id="f5fcb-121">Ein boolescher Wert, der angibt, ob der WMI-Anbieter für die Assembly aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-121">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="f5fcb-122">Der WMI-Anbieter ist für Benutzer erforderlich, um Laufzeitzugriff auf die Überprüfungs- und Steuerungsfunktionen von Windows Communication Foundation (WCF) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-122">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="f5fcb-123">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-123">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5fcb-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f5fcb-124">Child Elements</span></span>  
  
|<span data-ttu-id="f5fcb-125">Element</span><span class="sxs-lookup"><span data-stu-id="f5fcb-125">Element</span></span>|<span data-ttu-id="f5fcb-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5fcb-126">Description</span></span>|  
|-------------|-----------------|  
|[\<endToEndTracing>](endtoendtracing.md)|<span data-ttu-id="f5fcb-127">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-127">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[\<messageLogging>](messagelogging.md)|<span data-ttu-id="f5fcb-128">Beschreibt die Einstellungen für die WCF-Nachrichtenprotokollierung.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-128">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5fcb-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f5fcb-129">Parent Elements</span></span>  
  
|<span data-ttu-id="f5fcb-130">Element</span><span class="sxs-lookup"><span data-stu-id="f5fcb-130">Element</span></span>|<span data-ttu-id="f5fcb-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5fcb-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5fcb-132">serviceModel</span><span class="sxs-lookup"><span data-stu-id="f5fcb-132">serviceModel</span></span>|<span data-ttu-id="f5fcb-133">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5fcb-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f5fcb-134">Remarks</span></span>  
 <span data-ttu-id="f5fcb-135">Der `diagnostics`-Abschnitt definiert die Diagnoseeinstellungen für alle Dienste in einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-135">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="f5fcb-136">Es ist nicht möglich, separate Diagnoseeinstellungen auf Dienstebene zu definieren, es sei denn, es befindet sich nur ein Dienst in der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-136">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="f5fcb-137">Attribute werden gemäß den Anforderungen des Abschnitts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f5fcb-137">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5fcb-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5fcb-138">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f5fcb-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5fcb-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
