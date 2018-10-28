---
title: '&lt;security&gt; von &lt;wsDualHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 77e7191b345e59116874e70aaa28241223938eea
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193733"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="51f35-102">&lt;security&gt; von &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="51f35-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="51f35-103">Definiert die Sicherheitsfunktionen von der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="51f35-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="51f35-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="51f35-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="51f35-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="51f35-105">\<bindings></span></span>  
<span data-ttu-id="51f35-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="51f35-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="51f35-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="51f35-107">\<binding></span></span>  
<span data-ttu-id="51f35-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="51f35-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f35-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="51f35-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51f35-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="51f35-110">Attributes and Elements</span></span>  
 <span data-ttu-id="51f35-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="51f35-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51f35-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="51f35-112">Attributes</span></span>  
  
|<span data-ttu-id="51f35-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="51f35-113">Attribute</span></span>|<span data-ttu-id="51f35-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51f35-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51f35-115">mode</span><span class="sxs-lookup"><span data-stu-id="51f35-115">mode</span></span>|<span data-ttu-id="51f35-116">– Optional.</span><span class="sxs-lookup"><span data-stu-id="51f35-116">-   Optional.</span></span> <span data-ttu-id="51f35-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="51f35-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="51f35-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="51f35-118">The default value is `Message`.</span></span> <span data-ttu-id="51f35-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="51f35-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="51f35-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="51f35-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="51f35-121">Wert</span><span class="sxs-lookup"><span data-stu-id="51f35-121">Value</span></span>|<span data-ttu-id="51f35-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51f35-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51f35-123">Keine</span><span class="sxs-lookup"><span data-stu-id="51f35-123">None</span></span>|<span data-ttu-id="51f35-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="51f35-124">Security is disabled.</span></span>|  
|<span data-ttu-id="51f35-125">Meldung</span><span class="sxs-lookup"><span data-stu-id="51f35-125">Message</span></span>|<span data-ttu-id="51f35-126">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="51f35-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51f35-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="51f35-127">Child Elements</span></span>  
  
|<span data-ttu-id="51f35-128">Element</span><span class="sxs-lookup"><span data-stu-id="51f35-128">Element</span></span>|<span data-ttu-id="51f35-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51f35-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51f35-130">\<message></span><span class="sxs-lookup"><span data-stu-id="51f35-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="51f35-131">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="51f35-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="51f35-132">Dieses Element ist vom Typ <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="51f35-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51f35-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="51f35-133">Parent Elements</span></span>  
  
|<span data-ttu-id="51f35-134">Element</span><span class="sxs-lookup"><span data-stu-id="51f35-134">Element</span></span>|<span data-ttu-id="51f35-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51f35-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51f35-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="51f35-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="51f35-137">Definiert alle bindungsfähigkeiten von der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="51f35-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51f35-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51f35-138">Remarks</span></span>  
 <span data-ttu-id="51f35-139">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="51f35-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="51f35-140">Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="51f35-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f35-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51f35-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="51f35-142">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="51f35-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="51f35-143">Bindungen</span><span class="sxs-lookup"><span data-stu-id="51f35-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="51f35-144">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="51f35-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="51f35-145">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="51f35-145">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="51f35-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="51f35-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
