---
title: <diagnostics> für die Aktivierung
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: ac235b9a3c125cd3fe63ccd899e2ff92d4d3f31b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278449"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="79bf0-102">\<Diagnose > für die Aktivierung</span><span class="sxs-lookup"><span data-stu-id="79bf0-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="79bf0-103">Konfiguriert die Diagnosefunktionen von Windows Communication Foundation (WCF)-Listener.</span><span class="sxs-lookup"><span data-stu-id="79bf0-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="79bf0-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="79bf0-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="79bf0-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="79bf0-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79bf0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="79bf0-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="79bf0-107">Typ</span><span class="sxs-lookup"><span data-stu-id="79bf0-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79bf0-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="79bf0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="79bf0-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79bf0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79bf0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="79bf0-110">Attributes</span></span>  
  
|<span data-ttu-id="79bf0-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="79bf0-111">Attribute</span></span>|<span data-ttu-id="79bf0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79bf0-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="79bf0-113">Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="79bf0-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79bf0-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79bf0-114">Child Elements</span></span>  
 <span data-ttu-id="79bf0-115">Keine</span><span class="sxs-lookup"><span data-stu-id="79bf0-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79bf0-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79bf0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="79bf0-117">Element</span><span class="sxs-lookup"><span data-stu-id="79bf0-117">Element</span></span>|<span data-ttu-id="79bf0-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79bf0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79bf0-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="79bf0-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="79bf0-120">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="79bf0-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79bf0-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79bf0-121">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
