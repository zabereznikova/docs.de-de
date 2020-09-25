---
title: <behavior> von <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 739f95f527fd73062c8cec43efc6777efeb077f3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195154"
---
# <a name="behavior-of-servicebehaviors"></a><span data-ttu-id="4aa2a-102">\<behavior> von \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4aa2a-102">\<behavior> of \<serviceBehaviors></span></span>

<span data-ttu-id="4aa2a-103">Das `behavior`-Element enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-103">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="4aa2a-104">Jedes Verhalten wird durch seinen `name` indiziert.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="4aa2a-105">Dienste können mit dem-Attribut des-Elements über diesen Namen mit den einzelnen Verhalten verknüpft werden `behaviorConfiguration` [\<endpoint>](endpoint-element.md) .</span><span class="sxs-lookup"><span data-stu-id="4aa2a-105">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](endpoint-element.md) element.</span></span> <span data-ttu-id="4aa2a-106">Dies ermöglicht es Endpunkten, allgemeine Verhaltenskonfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="4aa2a-107">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-107">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="4aa2a-108">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="4aa2a-108">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4aa2a-109">Verhaltenselemente, die für Windows Workflow-Aktivitäten spezifisch sind, z. b. das- [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) Element, werden auf der Seite [ \<behavior> von \<serviceBehaviors> ](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-109">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="4aa2a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4aa2a-110">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4aa2a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4aa2a-111">Attributes and Elements</span></span>  

 <span data-ttu-id="4aa2a-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4aa2a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4aa2a-113">Attributes</span></span>  
  
|<span data-ttu-id="4aa2a-114">attribute</span><span class="sxs-lookup"><span data-stu-id="4aa2a-114">Attribute</span></span>|<span data-ttu-id="4aa2a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4aa2a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4aa2a-116">name</span><span class="sxs-lookup"><span data-stu-id="4aa2a-116">name</span></span>|<span data-ttu-id="4aa2a-117">Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-117">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="4aa2a-118">Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-118">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="4aa2a-119">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-119">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="4aa2a-120">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="4aa2a-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4aa2a-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4aa2a-121">Child Elements</span></span>  
  
|<span data-ttu-id="4aa2a-122">Element</span><span class="sxs-lookup"><span data-stu-id="4aa2a-122">Element</span></span>|<span data-ttu-id="4aa2a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4aa2a-123">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-element.md)|<span data-ttu-id="4aa2a-124">Speichert die Konfigurationsinformationen für DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-124">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<persistenceProvider>](persistenceprovider.md)|<span data-ttu-id="4aa2a-125">Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-125">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[\<routing>](routing-of-servicebehavior.md)|<span data-ttu-id="4aa2a-126">Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-126">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|<span data-ttu-id="4aa2a-127">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-127">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|<span data-ttu-id="4aa2a-128">Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-128">Specifies settings that authorize access to service operations.</span></span>|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="4aa2a-129">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-129">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[\<serviceDebug>](servicedebug.md)|<span data-ttu-id="4aa2a-130">Gibt Debugging-und Hilfe Informationsfunktionen für einen Windows Communication Foundation (WCF)-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-130">Specifies debugging and help information features for a Windows Communication Foundation (WCF) service.</span></span>|  
|[\<serviceDiscovery>](servicediscovery.md)|<span data-ttu-id="4aa2a-131">Gibt die Ermittelbarkeit von Dienstendpunkten an.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-131">Specifies the discoverability of service endpoints.</span></span>|  
|[\<serviceMetadata>](servicemetadata.md)|<span data-ttu-id="4aa2a-132">Gibt die Veröffentlichung der Dienstmetadaten und der zugeordneten Informationen an.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-132">Specifies the publication of service metadata and associated information.</span></span>|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|<span data-ttu-id="4aa2a-133">Legt Einstellungen fest, die die Überwachung von Sicherheitsereignissen während der Dienstvorgänge ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-133">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[\<serviceThrottling>](servicethrottling.md)|<span data-ttu-id="4aa2a-134">Gibt den Drosselungs Mechanismus eines WCF-Dienstanbieter an.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-134">Specifies the throttling mechanism of a WCF service.</span></span>|  
|[\<serviceTimeouts>](servicetimeouts.md)|<span data-ttu-id="4aa2a-135">Gibt den Timeout für einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-135">Specifies the timeout for a service.</span></span>|  
|[\<workflowRuntime>](workflowruntime.md)|<span data-ttu-id="4aa2a-136">Gibt Einstellungen für eine Instanz von WorkflowRuntime zum Hosting Workflow basierter WCF-Dienste an.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-136">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based WCF services.</span></span>|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="4aa2a-137">Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-137">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4aa2a-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4aa2a-138">Parent Elements</span></span>  
  
|<span data-ttu-id="4aa2a-139">Element</span><span class="sxs-lookup"><span data-stu-id="4aa2a-139">Element</span></span>|<span data-ttu-id="4aa2a-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4aa2a-140">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="4aa2a-141">Eine Auflistung von Dienstverhaltenselementen.</span><span class="sxs-lookup"><span data-stu-id="4aa2a-141">A collection of service behavior elements.</span></span>|
