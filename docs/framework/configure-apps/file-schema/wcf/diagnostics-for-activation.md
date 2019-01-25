---
title: '&lt;diagnostics&gt; für die Aktivierung'
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 5d8fcce28182dcac945655a52d829945a432a9b3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723913"
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="9b8b8-102">&lt;diagnostics&gt; für die Aktivierung</span><span class="sxs-lookup"><span data-stu-id="9b8b8-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="9b8b8-103">Konfiguriert die Diagnosefunktionen von Windows Communication Foundation (WCF)-Listener.</span><span class="sxs-lookup"><span data-stu-id="9b8b8-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="9b8b8-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="9b8b8-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="9b8b8-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="9b8b8-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b8b8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b8b8-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="9b8b8-107">Typ</span><span class="sxs-lookup"><span data-stu-id="9b8b8-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b8b8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9b8b8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9b8b8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b8b8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b8b8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9b8b8-110">Attributes</span></span>  
  
|<span data-ttu-id="9b8b8-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="9b8b8-111">Attribute</span></span>|<span data-ttu-id="9b8b8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b8b8-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="9b8b8-113">Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9b8b8-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b8b8-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b8b8-114">Child Elements</span></span>  
 <span data-ttu-id="9b8b8-115">Keine</span><span class="sxs-lookup"><span data-stu-id="9b8b8-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b8b8-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b8b8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9b8b8-117">Element</span><span class="sxs-lookup"><span data-stu-id="9b8b8-117">Element</span></span>|<span data-ttu-id="9b8b8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b8b8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b8b8-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="9b8b8-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="9b8b8-120">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="9b8b8-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b8b8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b8b8-121">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
