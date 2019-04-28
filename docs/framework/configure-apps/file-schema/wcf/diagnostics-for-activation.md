---
title: <diagnostics> für die Aktivierung
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704257"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="ae2a6-102">\<Diagnose > für die Aktivierung</span><span class="sxs-lookup"><span data-stu-id="ae2a6-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="ae2a6-103">Konfiguriert die Diagnosefunktionen von Windows Communication Foundation (WCF)-Listener.</span><span class="sxs-lookup"><span data-stu-id="ae2a6-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="ae2a6-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ae2a6-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="ae2a6-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="ae2a6-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae2a6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae2a6-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="ae2a6-107">Typ</span><span class="sxs-lookup"><span data-stu-id="ae2a6-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae2a6-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ae2a6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ae2a6-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ae2a6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae2a6-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ae2a6-110">Attributes</span></span>  
  
|<span data-ttu-id="ae2a6-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ae2a6-111">Attribute</span></span>|<span data-ttu-id="ae2a6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae2a6-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="ae2a6-113">Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="ae2a6-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae2a6-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae2a6-114">Child Elements</span></span>  
 <span data-ttu-id="ae2a6-115">Keine</span><span class="sxs-lookup"><span data-stu-id="ae2a6-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae2a6-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae2a6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ae2a6-117">Element</span><span class="sxs-lookup"><span data-stu-id="ae2a6-117">Element</span></span>|<span data-ttu-id="ae2a6-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae2a6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae2a6-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ae2a6-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="ae2a6-120">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="ae2a6-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae2a6-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae2a6-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
