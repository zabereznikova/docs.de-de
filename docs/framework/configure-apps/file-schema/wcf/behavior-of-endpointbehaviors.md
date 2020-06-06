---
title: <behavior> von <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 489678a5adeae3965acae90a847c4b087478354d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140809"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="f2f7e-102">\<behavior> von \<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f2f7e-102">\<behavior> of \<endpointBehaviors></span></span>
<span data-ttu-id="f2f7e-103">Das `behavior`-Element enthält eine Auflistung der Einstellungen für das Verhalten eines Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="f2f7e-104">Jedes Verhalten wird durch seinen `name` indiziert.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="f2f7e-105">Endpunkte können über diesen Namen mit den Verhalten verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="f2f7e-106">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-106">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f2f7e-107">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f2f7e-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="f2f7e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2f7e-108">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2f7e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f2f7e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f2f7e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2f7e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f2f7e-111">Attributes</span></span>  
  
|<span data-ttu-id="f2f7e-112">attribute</span><span class="sxs-lookup"><span data-stu-id="f2f7e-112">Attribute</span></span>|<span data-ttu-id="f2f7e-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f2f7e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2f7e-114">name</span><span class="sxs-lookup"><span data-stu-id="f2f7e-114">name</span></span>|<span data-ttu-id="f2f7e-115">Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-115">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="f2f7e-116">Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-116">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="f2f7e-117">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-117">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f2f7e-118">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f2f7e-118">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2f7e-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2f7e-119">Child Elements</span></span>  
  
|<span data-ttu-id="f2f7e-120">Element</span><span class="sxs-lookup"><span data-stu-id="f2f7e-120">Element</span></span>|<span data-ttu-id="f2f7e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2f7e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="f2f7e-122">Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-122">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[\<callbackDebug>](callbackdebug.md)|<span data-ttu-id="f2f7e-123">Gibt das Dienst Debuggen für ein Windows Communication Foundation (WCF)-Rückruf Objekt an.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-123">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[\<callbackTimeouts>](callbacktimeouts.md)|<span data-ttu-id="f2f7e-124">Gibt das Timeout für den Clientrückruf an.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-124">Specifies the timeout for the client callback.</span></span>|  
|[\<clientVia>](clientvia.md)|<span data-ttu-id="f2f7e-125">Gibt die Route an, die eine Nachricht nehmen sollte.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-125">Specifies the route a message should take.</span></span>|  
|[\<dataContractSerializer>](datacontractserializer.md)|<span data-ttu-id="f2f7e-126">Speichert die Konfigurationsinformationen für DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-126">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|<span data-ttu-id="f2f7e-127">Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-127">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[\<enableWebScript>](enablewebscript.md)|<span data-ttu-id="f2f7e-128">Aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-128">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="f2f7e-129">Das Verhalten sollte nur in Verbindung mit der \<webHttpBinding> Standard Bindung oder dem Bindungs Element verwendet werden \<webMessageEncoding> .</span><span class="sxs-lookup"><span data-stu-id="f2f7e-129">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="f2f7e-130">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-130">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[\<soapProcessing>](soapprocessing.md)|<span data-ttu-id="f2f7e-131">Definiert das Clientendpunktverhalten, das verwendet wird, um Nachrichten zwischen unterschiedlichen Bindungstypen und Nachrichtenversionen zu marshallen.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-131">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[\<synchronousReceive>](synchronousreceive-element.md)|<span data-ttu-id="f2f7e-132">Gibt das Laufzeitverhalten für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung an.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-132">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="f2f7e-133">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-133">It does not have any attributes or child elements.</span></span>|  
|[\<transactedBatching>](transactedbatching.md)|<span data-ttu-id="f2f7e-134">Gibt an, ob Transaktionsbatching für Empfangsvorgänge unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-134">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[\<webHttp>](webhttp.md)|<span data-ttu-id="f2f7e-135">Gibt WebHttpBehavior anhand der Konfiguration in einem Endpunkt an.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-135">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="f2f7e-136">Wenn dieses Verhalten in Verbindung mit der \<webHttpBinding> Standard Bindung verwendet wird, wird das webprogrammier Modell für einen WCF-Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-136">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2f7e-137">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2f7e-137">Parent Elements</span></span>  
  
|<span data-ttu-id="f2f7e-138">Element</span><span class="sxs-lookup"><span data-stu-id="f2f7e-138">Element</span></span>|<span data-ttu-id="f2f7e-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2f7e-139">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="f2f7e-140">Eine Auflistung von Endpunktverhaltenselementen.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-140">A collection of endpoint behavior elements.</span></span>|
