---
title: <diagnostics> zur Aktivierung
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: c16f32357d40b9b69d52c525ce8a395a3de8fdb1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192320"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="16a1d-102">\<diagnostics> zur Aktivierung</span><span class="sxs-lookup"><span data-stu-id="16a1d-102">\<diagnostics> for Activation</span></span>

<span data-ttu-id="16a1d-103">Konfiguriert die Diagnosefunktionen Windows Communication Foundation (WCF)-Listener.</span><span class="sxs-lookup"><span data-stu-id="16a1d-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="16a1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16a1d-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="16a1d-105">Typ</span><span class="sxs-lookup"><span data-stu-id="16a1d-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16a1d-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16a1d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="16a1d-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16a1d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16a1d-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="16a1d-108">Attributes</span></span>  
  
|<span data-ttu-id="16a1d-109">attribute</span><span class="sxs-lookup"><span data-stu-id="16a1d-109">Attribute</span></span>|<span data-ttu-id="16a1d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16a1d-110">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="16a1d-111">Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="16a1d-111">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16a1d-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16a1d-112">Child Elements</span></span>  

 <span data-ttu-id="16a1d-113">Keine</span><span class="sxs-lookup"><span data-stu-id="16a1d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16a1d-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16a1d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="16a1d-115">Element</span><span class="sxs-lookup"><span data-stu-id="16a1d-115">Element</span></span>|<span data-ttu-id="16a1d-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16a1d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="16a1d-117">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="16a1d-117">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16a1d-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16a1d-118">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
