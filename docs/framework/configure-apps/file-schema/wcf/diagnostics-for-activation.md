---
title: <diagnostics>zur Aktivierung
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 543c41936921eda39017e07f1c97294b268a9141
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919222"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="4b04b-102">\<Diagnose > für die Aktivierung</span><span class="sxs-lookup"><span data-stu-id="4b04b-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="4b04b-103">Konfiguriert die Diagnosefunktionen Windows Communication Foundation (WCF)-Listener.</span><span class="sxs-lookup"><span data-stu-id="4b04b-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="4b04b-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="4b04b-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="4b04b-105">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="4b04b-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b04b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b04b-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="4b04b-107">Typ</span><span class="sxs-lookup"><span data-stu-id="4b04b-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b04b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4b04b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4b04b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4b04b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b04b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4b04b-110">Attributes</span></span>  
  
|<span data-ttu-id="4b04b-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4b04b-111">Attribute</span></span>|<span data-ttu-id="4b04b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b04b-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="4b04b-113">Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4b04b-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b04b-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b04b-114">Child Elements</span></span>  
 <span data-ttu-id="4b04b-115">Keine</span><span class="sxs-lookup"><span data-stu-id="4b04b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b04b-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b04b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4b04b-117">Element</span><span class="sxs-lookup"><span data-stu-id="4b04b-117">Element</span></span>|<span data-ttu-id="4b04b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b04b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b04b-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="4b04b-119">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="4b04b-120">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="4b04b-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b04b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b04b-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
