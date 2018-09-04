---
title: '&lt;security&gt; von &lt;wsDualHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 023e0dd2a89c005928625cf95f3de61af81c7b6b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514528"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="bafa8-102">&lt;security&gt; von &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="bafa8-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="bafa8-103">Definiert die Sicherheitsfunktionen von der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="bafa8-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="bafa8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bafa8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bafa8-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="bafa8-105">\<bindings></span></span>  
<span data-ttu-id="bafa8-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="bafa8-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="bafa8-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="bafa8-107">\<binding></span></span>  
<span data-ttu-id="bafa8-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="bafa8-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bafa8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="bafa8-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bafa8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bafa8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bafa8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bafa8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bafa8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="bafa8-112">Attributes</span></span>  
  
|<span data-ttu-id="bafa8-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="bafa8-113">Attribute</span></span>|<span data-ttu-id="bafa8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bafa8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bafa8-115">mode</span><span class="sxs-lookup"><span data-stu-id="bafa8-115">mode</span></span>|<span data-ttu-id="bafa8-116">– Optional.</span><span class="sxs-lookup"><span data-stu-id="bafa8-116">-   Optional.</span></span> <span data-ttu-id="bafa8-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="bafa8-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="bafa8-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="bafa8-118">The default value is `Message`.</span></span> <span data-ttu-id="bafa8-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="bafa8-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="bafa8-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="bafa8-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="bafa8-121">Wert</span><span class="sxs-lookup"><span data-stu-id="bafa8-121">Value</span></span>|<span data-ttu-id="bafa8-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bafa8-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bafa8-123">Keine</span><span class="sxs-lookup"><span data-stu-id="bafa8-123">None</span></span>|<span data-ttu-id="bafa8-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bafa8-124">Security is disabled.</span></span>|  
|<span data-ttu-id="bafa8-125">Meldung</span><span class="sxs-lookup"><span data-stu-id="bafa8-125">Message</span></span>|<span data-ttu-id="bafa8-126">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bafa8-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bafa8-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bafa8-127">Child Elements</span></span>  
  
|<span data-ttu-id="bafa8-128">Element</span><span class="sxs-lookup"><span data-stu-id="bafa8-128">Element</span></span>|<span data-ttu-id="bafa8-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bafa8-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bafa8-130">\<message></span><span class="sxs-lookup"><span data-stu-id="bafa8-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="bafa8-131">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="bafa8-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="bafa8-132">Dieses Element ist vom Typ <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="bafa8-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bafa8-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bafa8-133">Parent Elements</span></span>  
  
|<span data-ttu-id="bafa8-134">Element</span><span class="sxs-lookup"><span data-stu-id="bafa8-134">Element</span></span>|<span data-ttu-id="bafa8-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bafa8-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bafa8-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="bafa8-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="bafa8-137">Definiert alle bindungsfähigkeiten von der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="bafa8-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bafa8-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bafa8-138">Remarks</span></span>  
 <span data-ttu-id="bafa8-139">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bafa8-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="bafa8-140">Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bafa8-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafa8-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bafa8-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="bafa8-142">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="bafa8-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="bafa8-143">Bindungen</span><span class="sxs-lookup"><span data-stu-id="bafa8-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="bafa8-144">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="bafa8-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="bafa8-145">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="bafa8-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="bafa8-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="bafa8-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
