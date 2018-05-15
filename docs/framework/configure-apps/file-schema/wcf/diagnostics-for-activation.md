---
title: '&lt;diagnostics&gt; für die Aktivierung'
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 4e5332eed87ded51cebcd614f45cbc8e80e570fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="78321-102">&lt;diagnostics&gt; für die Aktivierung</span><span class="sxs-lookup"><span data-stu-id="78321-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="78321-103">Konfiguriert die Diagnosefunktionen von Windows Communication Foundation (WCF)-Listener.</span><span class="sxs-lookup"><span data-stu-id="78321-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="78321-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="78321-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="78321-105">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="78321-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78321-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="78321-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="78321-107">Typ</span><span class="sxs-lookup"><span data-stu-id="78321-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78321-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="78321-108">Attributes and Elements</span></span>  
 <span data-ttu-id="78321-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="78321-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78321-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="78321-110">Attributes</span></span>  
  
|<span data-ttu-id="78321-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="78321-111">Attribute</span></span>|<span data-ttu-id="78321-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78321-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="78321-113">Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="78321-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78321-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="78321-114">Child Elements</span></span>  
 <span data-ttu-id="78321-115">Keine</span><span class="sxs-lookup"><span data-stu-id="78321-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78321-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="78321-116">Parent Elements</span></span>  
  
|<span data-ttu-id="78321-117">Element</span><span class="sxs-lookup"><span data-stu-id="78321-117">Element</span></span>|<span data-ttu-id="78321-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78321-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78321-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="78321-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="78321-120">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="78321-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78321-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78321-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
