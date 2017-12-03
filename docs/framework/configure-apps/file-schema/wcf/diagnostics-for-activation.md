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
ms.openlocfilehash: 1610c77125d2820e3adc06b3c37177058c85abdd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="58b34-102">&lt;diagnostics&gt; für die Aktivierung</span><span class="sxs-lookup"><span data-stu-id="58b34-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="58b34-103">Konfiguriert die Diagnosefunktionen des [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Listeners.</span><span class="sxs-lookup"><span data-stu-id="58b34-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="58b34-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="58b34-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="58b34-105">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="58b34-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b34-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="58b34-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="58b34-107">Typ</span><span class="sxs-lookup"><span data-stu-id="58b34-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58b34-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="58b34-108">Attributes and Elements</span></span>  
 <span data-ttu-id="58b34-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58b34-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58b34-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="58b34-110">Attributes</span></span>  
  
|<span data-ttu-id="58b34-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="58b34-111">Attribute</span></span>|<span data-ttu-id="58b34-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58b34-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="58b34-113">Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="58b34-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58b34-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58b34-114">Child Elements</span></span>  
 <span data-ttu-id="58b34-115">Keine</span><span class="sxs-lookup"><span data-stu-id="58b34-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58b34-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58b34-116">Parent Elements</span></span>  
  
|<span data-ttu-id="58b34-117">Element</span><span class="sxs-lookup"><span data-stu-id="58b34-117">Element</span></span>|<span data-ttu-id="58b34-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58b34-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58b34-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="58b34-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="58b34-120">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="58b34-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58b34-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58b34-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
