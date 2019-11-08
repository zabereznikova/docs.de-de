---
title: <security> von <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738603"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="6c9d5-102">\<Sicherheits > \<von WSDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="6c9d5-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="6c9d5-103">Definiert die Sicherheitsfunktionen des [\<WSDualHttpBinding->](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="6c9d5-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
<span data-ttu-id="6c9d5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6c9d5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6c9d5-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="6c9d5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6c9d5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6c9d5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6c9d5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSDualHttpBinding >** ](wsdualhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6c9d5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)</span></span>\
<span data-ttu-id="6c9d5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="6c9d5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6c9d5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheit >**</span><span class="sxs-lookup"><span data-stu-id="6c9d5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c9d5-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c9d5-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c9d5-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6c9d5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6c9d5-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c9d5-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c9d5-113">Attributes</span></span>  
  
|<span data-ttu-id="6c9d5-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="6c9d5-114">Attribute</span></span>|<span data-ttu-id="6c9d5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c9d5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c9d5-116">Modus</span><span class="sxs-lookup"><span data-stu-id="6c9d5-116">mode</span></span>|<span data-ttu-id="6c9d5-117">Optionale.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-117">-   Optional.</span></span> <span data-ttu-id="6c9d5-118">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="6c9d5-119">Der Standardwert ist `Message`sein.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-119">The default value is `Message`.</span></span> <span data-ttu-id="6c9d5-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-120">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="6c9d5-121">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="6c9d5-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="6c9d5-122">Wert</span><span class="sxs-lookup"><span data-stu-id="6c9d5-122">Value</span></span>|<span data-ttu-id="6c9d5-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c9d5-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6c9d5-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="6c9d5-124">None</span></span>|<span data-ttu-id="6c9d5-125">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-125">Security is disabled.</span></span>|  
|<span data-ttu-id="6c9d5-126">Nachricht</span><span class="sxs-lookup"><span data-stu-id="6c9d5-126">Message</span></span>|<span data-ttu-id="6c9d5-127">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-127">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c9d5-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c9d5-128">Child Elements</span></span>  
  
|<span data-ttu-id="6c9d5-129">Element</span><span class="sxs-lookup"><span data-stu-id="6c9d5-129">Element</span></span>|<span data-ttu-id="6c9d5-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c9d5-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c9d5-131">\<message ></span><span class="sxs-lookup"><span data-stu-id="6c9d5-131">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="6c9d5-132">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="6c9d5-133">Dieses Element ist vom Typ <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-133">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c9d5-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c9d5-134">Parent Elements</span></span>  
  
|<span data-ttu-id="6c9d5-135">Element</span><span class="sxs-lookup"><span data-stu-id="6c9d5-135">Element</span></span>|<span data-ttu-id="6c9d5-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c9d5-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c9d5-137">\<binding ></span><span class="sxs-lookup"><span data-stu-id="6c9d5-137">\<binding></span></span>](bindings.md)|<span data-ttu-id="6c9d5-138">Definiert alle Bindungsfunktionen des [\<WSDualHttpBinding->](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="6c9d5-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c9d5-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c9d5-139">Remarks</span></span>  
 <span data-ttu-id="6c9d5-140">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-140">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="6c9d5-141">Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c9d5-141">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c9d5-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c9d5-142">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="6c9d5-143">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="6c9d5-143">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6c9d5-144">Bindungen</span><span class="sxs-lookup"><span data-stu-id="6c9d5-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6c9d5-145">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="6c9d5-145">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6c9d5-146">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="6c9d5-146">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6c9d5-147">\<binding ></span><span class="sxs-lookup"><span data-stu-id="6c9d5-147">\<binding></span></span>](bindings.md)
