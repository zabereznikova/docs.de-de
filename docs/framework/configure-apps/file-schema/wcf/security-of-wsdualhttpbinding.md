---
title: <security> von <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738603"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="9ce2a-102">\<security> von \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9ce2a-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="9ce2a-103">Definiert die Sicherheitsfunktionen von [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9ce2a-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="9ce2a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ce2a-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ce2a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9ce2a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9ce2a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ce2a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ce2a-107">Attributes</span></span>  
  
|<span data-ttu-id="9ce2a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9ce2a-108">Attribute</span></span>|<span data-ttu-id="9ce2a-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9ce2a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ce2a-110">Modus</span><span class="sxs-lookup"><span data-stu-id="9ce2a-110">mode</span></span>|<span data-ttu-id="9ce2a-111">Optionale.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-111">-   Optional.</span></span> <span data-ttu-id="9ce2a-112">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="9ce2a-113">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-113">The default value is `Message`.</span></span> <span data-ttu-id="9ce2a-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-114">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="9ce2a-115">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="9ce2a-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="9ce2a-116">Wert</span><span class="sxs-lookup"><span data-stu-id="9ce2a-116">Value</span></span>|<span data-ttu-id="9ce2a-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9ce2a-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ce2a-118">Keine</span><span class="sxs-lookup"><span data-stu-id="9ce2a-118">None</span></span>|<span data-ttu-id="9ce2a-119">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-119">Security is disabled.</span></span>|  
|<span data-ttu-id="9ce2a-120">`Message`</span><span class="sxs-lookup"><span data-stu-id="9ce2a-120">Message</span></span>|<span data-ttu-id="9ce2a-121">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-121">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ce2a-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ce2a-122">Child Elements</span></span>  
  
|<span data-ttu-id="9ce2a-123">Element</span><span class="sxs-lookup"><span data-stu-id="9ce2a-123">Element</span></span>|<span data-ttu-id="9ce2a-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ce2a-124">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="9ce2a-125">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-125">Defines the settings for the message-level security.</span></span> <span data-ttu-id="9ce2a-126">Dieses Element ist vom Typ <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-126">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ce2a-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ce2a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="9ce2a-128">Element</span><span class="sxs-lookup"><span data-stu-id="9ce2a-128">Element</span></span>|<span data-ttu-id="9ce2a-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ce2a-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="9ce2a-130">Definiert alle Bindungsfunktionen von [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9ce2a-130">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ce2a-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9ce2a-131">Remarks</span></span>  
 <span data-ttu-id="9ce2a-132">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-132">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="9ce2a-133">Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9ce2a-133">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce2a-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ce2a-134">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="9ce2a-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="9ce2a-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9ce2a-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9ce2a-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9ce2a-137">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="9ce2a-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9ce2a-138">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9ce2a-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
