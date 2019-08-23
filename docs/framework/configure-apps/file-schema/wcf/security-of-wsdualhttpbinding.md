---
title: <security> von <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: bed7f4ce325e0d5e387e310ca15a3b72ac93f18e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936546"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="1b5ba-102">\<Sicherheits > von \<WSDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="1b5ba-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="1b5ba-103">Definiert die Sicherheitsfunktionen der [ \<WSDualHttpBinding->](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1b5ba-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="1b5ba-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1b5ba-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b5ba-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1b5ba-105">\<bindings></span></span>  
<span data-ttu-id="1b5ba-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1b5ba-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="1b5ba-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b5ba-107">\<binding></span></span>  
<span data-ttu-id="1b5ba-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1b5ba-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b5ba-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b5ba-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b5ba-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1b5ba-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1b5ba-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b5ba-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="1b5ba-112">Attributes</span></span>  
  
|<span data-ttu-id="1b5ba-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="1b5ba-113">Attribute</span></span>|<span data-ttu-id="1b5ba-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b5ba-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b5ba-115">Modus</span><span class="sxs-lookup"><span data-stu-id="1b5ba-115">mode</span></span>|<span data-ttu-id="1b5ba-116">Optionale.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-116">-   Optional.</span></span> <span data-ttu-id="1b5ba-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="1b5ba-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-118">The default value is `Message`.</span></span> <span data-ttu-id="1b5ba-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="1b5ba-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="1b5ba-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="1b5ba-121">Wert</span><span class="sxs-lookup"><span data-stu-id="1b5ba-121">Value</span></span>|<span data-ttu-id="1b5ba-122">Description</span><span class="sxs-lookup"><span data-stu-id="1b5ba-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b5ba-123">None</span><span class="sxs-lookup"><span data-stu-id="1b5ba-123">None</span></span>|<span data-ttu-id="1b5ba-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-124">Security is disabled.</span></span>|  
|<span data-ttu-id="1b5ba-125">Meldung</span><span class="sxs-lookup"><span data-stu-id="1b5ba-125">Message</span></span>|<span data-ttu-id="1b5ba-126">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b5ba-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b5ba-127">Child Elements</span></span>  
  
|<span data-ttu-id="1b5ba-128">Element</span><span class="sxs-lookup"><span data-stu-id="1b5ba-128">Element</span></span>|<span data-ttu-id="1b5ba-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b5ba-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b5ba-130">\<message></span><span class="sxs-lookup"><span data-stu-id="1b5ba-130">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="1b5ba-131">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="1b5ba-132">Dieses Element ist vom Typ <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1b5ba-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b5ba-133">Parent Elements</span></span>  
  
|<span data-ttu-id="1b5ba-134">Element</span><span class="sxs-lookup"><span data-stu-id="1b5ba-134">Element</span></span>|<span data-ttu-id="1b5ba-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b5ba-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b5ba-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b5ba-136">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="1b5ba-137">Definiert alle Bindungsfunktionen der [ \<WSDualHttpBinding->](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1b5ba-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b5ba-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b5ba-138">Remarks</span></span>  
 <span data-ttu-id="1b5ba-139">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="1b5ba-140">Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1b5ba-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5ba-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b5ba-141">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="1b5ba-142">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="1b5ba-142">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1b5ba-143">Bindungen</span><span class="sxs-lookup"><span data-stu-id="1b5ba-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1b5ba-144">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="1b5ba-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1b5ba-145">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="1b5ba-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1b5ba-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b5ba-146">\<binding></span></span>](../../../misc/binding.md)
