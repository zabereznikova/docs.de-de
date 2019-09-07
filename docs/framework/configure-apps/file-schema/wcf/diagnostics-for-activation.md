---
title: <diagnostics>zur Aktivierung
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400410"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="60b62-102">\<Diagnose > für die Aktivierung</span><span class="sxs-lookup"><span data-stu-id="60b62-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="60b62-103">Konfiguriert die Diagnosefunktionen Windows Communication Foundation (WCF)-Listener.</span><span class="sxs-lookup"><span data-stu-id="60b62-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
<span data-ttu-id="60b62-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="60b62-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="60b62-105">&nbsp;&nbsp;[ **\<System. Service Model. Activation->** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="60b62-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="60b62-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Diagnose >**</span><span class="sxs-lookup"><span data-stu-id="60b62-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60b62-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="60b62-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="60b62-108">Typ</span><span class="sxs-lookup"><span data-stu-id="60b62-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60b62-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="60b62-109">Attributes and Elements</span></span>  
 <span data-ttu-id="60b62-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60b62-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60b62-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="60b62-111">Attributes</span></span>  
  
|<span data-ttu-id="60b62-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="60b62-112">Attribute</span></span>|<span data-ttu-id="60b62-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60b62-113">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="60b62-114">Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="60b62-114">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60b62-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60b62-115">Child Elements</span></span>  
 <span data-ttu-id="60b62-116">Keine</span><span class="sxs-lookup"><span data-stu-id="60b62-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60b62-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60b62-117">Parent Elements</span></span>  
  
|<span data-ttu-id="60b62-118">Element</span><span class="sxs-lookup"><span data-stu-id="60b62-118">Element</span></span>|<span data-ttu-id="60b62-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60b62-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60b62-120">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="60b62-120">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="60b62-121">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="60b62-121">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60b62-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60b62-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
