---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 2749bc6c66d491a8a160d98b508fb43aa027b806
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398045"
---
# <a name="diagnostics"></a><span data-ttu-id="af0f9-101">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="af0f9-101">\<diagnostics></span></span>
<span data-ttu-id="af0f9-102">Das `diagnostics`-Element definiert Einstellungen, die von einem Administrator zur Laufzeitüberprüfung und -steuerung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="af0f9-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
<span data-ttu-id="af0f9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af0f9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af0f9-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="af0f9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="af0f9-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<Diagnose >**</span><span class="sxs-lookup"><span data-stu-id="af0f9-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af0f9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="af0f9-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af0f9-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af0f9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="af0f9-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af0f9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af0f9-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="af0f9-109">Attributes</span></span>  
  
|<span data-ttu-id="af0f9-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="af0f9-110">Attribute</span></span>|<span data-ttu-id="af0f9-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af0f9-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af0f9-112">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="af0f9-112">etwProviderId</span></span>|<span data-ttu-id="af0f9-113">Eine Zeichenfolge, die den Bezeichner für den Anbieter der Ereignisablaufverfolgung angibt, der Ereignisse in ETW-Sitzungen schreibt.</span><span class="sxs-lookup"><span data-stu-id="af0f9-113">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="af0f9-114">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="af0f9-114">performanceCounters</span></span>|<span data-ttu-id="af0f9-115">Gibt an, ob die Leistungsindikatoren für die Assembly aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="af0f9-115">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="af0f9-116">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="af0f9-116">Valid values are</span></span><br /><br /> <span data-ttu-id="af0f9-117">Abgeschrieben Leistungsindikatoren sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="af0f9-117">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="af0f9-118">ServiceOnly Nur Leistungsindikatoren für diesen Dienst sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="af0f9-118">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="af0f9-119">Allen Leistungsindikatoren können zur Laufzeit angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="af0f9-119">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="af0f9-120">Vorgegebene Die einzelne Leistungsindikatorinstanz _WCF_Admin wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="af0f9-120">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="af0f9-121">Diese Instanz wird verwendet, um die Auflistung der SQM-Daten für die Verwendung durch die Infrastruktur zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="af0f9-121">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="af0f9-122">Die Indikatorwerte für diese Instanz werden nicht aktualisiert und bleiben deshalb auf null.</span><span class="sxs-lookup"><span data-stu-id="af0f9-122">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="af0f9-123">Dies ist der Standardwert, wenn keine Konfiguration für WCF vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="af0f9-123">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="af0f9-124">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="af0f9-124">wmiProviderEnabled</span></span>|<span data-ttu-id="af0f9-125">Ein boolescher Wert, der angibt, ob der WMI-Anbieter für die Assembly aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="af0f9-125">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="af0f9-126">Der WMI-Anbieter ist für Benutzer erforderlich, um Laufzeitzugriff auf die Überprüfungs- und Steuerungsfunktionen von Windows Communication Foundation (WCF) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="af0f9-126">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="af0f9-127">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="af0f9-127">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af0f9-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af0f9-128">Child Elements</span></span>  
  
|<span data-ttu-id="af0f9-129">Element</span><span class="sxs-lookup"><span data-stu-id="af0f9-129">Element</span></span>|<span data-ttu-id="af0f9-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af0f9-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af0f9-131">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="af0f9-131">\<endToEndTracing></span></span>](endtoendtracing.md)|<span data-ttu-id="af0f9-132">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="af0f9-132">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="af0f9-133">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="af0f9-133">\<messageLogging></span></span>](messagelogging.md)|<span data-ttu-id="af0f9-134">Beschreibt die Einstellungen für die WCF-Nachrichtenprotokollierung.</span><span class="sxs-lookup"><span data-stu-id="af0f9-134">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af0f9-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af0f9-135">Parent Elements</span></span>  
  
|<span data-ttu-id="af0f9-136">Element</span><span class="sxs-lookup"><span data-stu-id="af0f9-136">Element</span></span>|<span data-ttu-id="af0f9-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af0f9-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af0f9-138">serviceModel</span><span class="sxs-lookup"><span data-stu-id="af0f9-138">serviceModel</span></span>|<span data-ttu-id="af0f9-139">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="af0f9-139">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af0f9-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af0f9-140">Remarks</span></span>  
 <span data-ttu-id="af0f9-141">Der `diagnostics`-Abschnitt definiert die Diagnoseeinstellungen für alle Dienste in einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="af0f9-141">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="af0f9-142">Es ist nicht möglich, separate Diagnoseeinstellungen auf Dienstebene zu definieren, es sei denn, es befindet sich nur ein Dienst in der Assembly.</span><span class="sxs-lookup"><span data-stu-id="af0f9-142">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="af0f9-143">Attribute werden gemäß den Anforderungen des Abschnitts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="af0f9-143">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af0f9-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af0f9-144">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af0f9-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af0f9-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
