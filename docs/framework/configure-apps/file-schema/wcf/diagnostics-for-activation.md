---
title: "&lt;diagnostics&gt; für die Aktivierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20b956bb58142f26fa1402f1f974b3984ed759f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="1647e-102">&lt;diagnostics&gt; für die Aktivierung</span><span class="sxs-lookup"><span data-stu-id="1647e-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="1647e-103">Konfiguriert die Diagnosefunktionen des [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Listeners.</span><span class="sxs-lookup"><span data-stu-id="1647e-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="1647e-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="1647e-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="1647e-105">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="1647e-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1647e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1647e-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="1647e-107">Typ</span><span class="sxs-lookup"><span data-stu-id="1647e-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1647e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1647e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1647e-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1647e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1647e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="1647e-110">Attributes</span></span>  
  
|<span data-ttu-id="1647e-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="1647e-111">Attribute</span></span>|<span data-ttu-id="1647e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1647e-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="1647e-113">Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1647e-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1647e-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1647e-114">Child Elements</span></span>  
 <span data-ttu-id="1647e-115">Keine</span><span class="sxs-lookup"><span data-stu-id="1647e-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1647e-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1647e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1647e-117">Element</span><span class="sxs-lookup"><span data-stu-id="1647e-117">Element</span></span>|<span data-ttu-id="1647e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1647e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1647e-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="1647e-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="1647e-120">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="1647e-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1647e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1647e-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
