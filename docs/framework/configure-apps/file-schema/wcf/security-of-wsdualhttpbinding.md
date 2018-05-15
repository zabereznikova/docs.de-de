---
title: '&lt;security&gt; von &lt;wsDualHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 734b6d0625cfda79b600a0920ab39bda25ee2e8b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="54075-102">&lt;security&gt; von &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="54075-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="54075-103">Definiert die Sicherheitsfunktionen des der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="54075-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="54075-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="54075-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="54075-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="54075-105">\<bindings></span></span>  
<span data-ttu-id="54075-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="54075-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="54075-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="54075-107">\<binding></span></span>  
<span data-ttu-id="54075-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="54075-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54075-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="54075-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54075-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="54075-110">Attributes and Elements</span></span>  
 <span data-ttu-id="54075-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="54075-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54075-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="54075-112">Attributes</span></span>  
  
|<span data-ttu-id="54075-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="54075-113">Attribute</span></span>|<span data-ttu-id="54075-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54075-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54075-115">mode</span><span class="sxs-lookup"><span data-stu-id="54075-115">mode</span></span>|<span data-ttu-id="54075-116">-Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="54075-116">-   Optional.</span></span> <span data-ttu-id="54075-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="54075-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="54075-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="54075-118">The default value is `Message`.</span></span> <span data-ttu-id="54075-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="54075-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="54075-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="54075-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="54075-121">Wert</span><span class="sxs-lookup"><span data-stu-id="54075-121">Value</span></span>|<span data-ttu-id="54075-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54075-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="54075-123">Keine</span><span class="sxs-lookup"><span data-stu-id="54075-123">None</span></span>|<span data-ttu-id="54075-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="54075-124">Security is disabled.</span></span>|  
|<span data-ttu-id="54075-125">Meldung</span><span class="sxs-lookup"><span data-stu-id="54075-125">Message</span></span>|<span data-ttu-id="54075-126">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="54075-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54075-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54075-127">Child Elements</span></span>  
  
|<span data-ttu-id="54075-128">Element</span><span class="sxs-lookup"><span data-stu-id="54075-128">Element</span></span>|<span data-ttu-id="54075-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54075-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54075-130">\<message></span><span class="sxs-lookup"><span data-stu-id="54075-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="54075-131">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="54075-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="54075-132">Dieses Element ist vom Typ <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="54075-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54075-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54075-133">Parent Elements</span></span>  
  
|<span data-ttu-id="54075-134">Element</span><span class="sxs-lookup"><span data-stu-id="54075-134">Element</span></span>|<span data-ttu-id="54075-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54075-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54075-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="54075-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="54075-137">Definiert alle bindungsmöglichkeiten der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="54075-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54075-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54075-138">Remarks</span></span>  
 <span data-ttu-id="54075-139">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="54075-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="54075-140">Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="54075-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54075-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54075-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="54075-142">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="54075-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="54075-143">Bindungen</span><span class="sxs-lookup"><span data-stu-id="54075-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="54075-144">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="54075-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="54075-145">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="54075-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="54075-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="54075-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
