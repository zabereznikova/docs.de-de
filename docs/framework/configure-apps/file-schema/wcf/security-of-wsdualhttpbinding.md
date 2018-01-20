---
title: '&lt;security&gt; von &lt;wsDualHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 6680d01b068a6ac1c4f9abcda69779c9cd0786a0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="559a3-102">&lt;security&gt; von &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="559a3-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="559a3-103">Definiert die Sicherheitsfunktionen des der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="559a3-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="559a3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="559a3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="559a3-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="559a3-105">\<bindings></span></span>  
<span data-ttu-id="559a3-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="559a3-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="559a3-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="559a3-107">\<binding></span></span>  
<span data-ttu-id="559a3-108">\<security></span><span class="sxs-lookup"><span data-stu-id="559a3-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="559a3-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="559a3-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="559a3-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="559a3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="559a3-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="559a3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="559a3-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="559a3-112">Attributes</span></span>  
  
|<span data-ttu-id="559a3-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="559a3-113">Attribute</span></span>|<span data-ttu-id="559a3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="559a3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="559a3-115">mode</span><span class="sxs-lookup"><span data-stu-id="559a3-115">mode</span></span>|<span data-ttu-id="559a3-116">-Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="559a3-116">-   Optional.</span></span> <span data-ttu-id="559a3-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="559a3-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="559a3-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="559a3-118">The default value is `Message`.</span></span> <span data-ttu-id="559a3-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="559a3-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="559a3-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="559a3-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="559a3-121">Wert</span><span class="sxs-lookup"><span data-stu-id="559a3-121">Value</span></span>|<span data-ttu-id="559a3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="559a3-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="559a3-123">Keine</span><span class="sxs-lookup"><span data-stu-id="559a3-123">None</span></span>|<span data-ttu-id="559a3-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="559a3-124">Security is disabled.</span></span>|  
|<span data-ttu-id="559a3-125">Meldung</span><span class="sxs-lookup"><span data-stu-id="559a3-125">Message</span></span>|<span data-ttu-id="559a3-126">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="559a3-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="559a3-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="559a3-127">Child Elements</span></span>  
  
|<span data-ttu-id="559a3-128">Element</span><span class="sxs-lookup"><span data-stu-id="559a3-128">Element</span></span>|<span data-ttu-id="559a3-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="559a3-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="559a3-130">\<message></span><span class="sxs-lookup"><span data-stu-id="559a3-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="559a3-131">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="559a3-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="559a3-132">Dieses Element ist vom Typ <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="559a3-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="559a3-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="559a3-133">Parent Elements</span></span>  
  
|<span data-ttu-id="559a3-134">Element</span><span class="sxs-lookup"><span data-stu-id="559a3-134">Element</span></span>|<span data-ttu-id="559a3-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="559a3-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="559a3-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="559a3-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="559a3-137">Definiert alle bindungsmöglichkeiten der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="559a3-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="559a3-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="559a3-138">Remarks</span></span>  
 <span data-ttu-id="559a3-139">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="559a3-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="559a3-140">Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="559a3-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="559a3-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="559a3-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="559a3-142">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="559a3-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="559a3-143">Bindungen</span><span class="sxs-lookup"><span data-stu-id="559a3-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="559a3-144">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="559a3-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="559a3-145">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="559a3-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="559a3-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="559a3-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
