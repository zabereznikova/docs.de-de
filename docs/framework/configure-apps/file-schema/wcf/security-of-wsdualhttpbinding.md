---
title: <security> von <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 7398cd538bb240e78413575f7c28abe7f797d05c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162204"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="b9fd6-102">\<security> von \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b9fd6-102">\<security> of \<wsDualHttpBinding></span></span>

<span data-ttu-id="b9fd6-103">Definiert die Sicherheitsfunktionen von [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b9fd6-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="b9fd6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9fd6-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9fd6-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b9fd6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b9fd6-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9fd6-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b9fd6-107">Attributes</span></span>  
  
|<span data-ttu-id="b9fd6-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b9fd6-108">Attribute</span></span>|<span data-ttu-id="b9fd6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9fd6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9fd6-110">Modus</span><span class="sxs-lookup"><span data-stu-id="b9fd6-110">mode</span></span>|<span data-ttu-id="b9fd6-111">Optionale.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-111">-   Optional.</span></span> <span data-ttu-id="b9fd6-112">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="b9fd6-113">Standardwert: `Message`.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-113">The default value is `Message`.</span></span> <span data-ttu-id="b9fd6-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-114">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b9fd6-115">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="b9fd6-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="b9fd6-116">Wert</span><span class="sxs-lookup"><span data-stu-id="b9fd6-116">Value</span></span>|<span data-ttu-id="b9fd6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9fd6-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b9fd6-118">Keine</span><span class="sxs-lookup"><span data-stu-id="b9fd6-118">None</span></span>|<span data-ttu-id="b9fd6-119">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-119">Security is disabled.</span></span>|  
|<span data-ttu-id="b9fd6-120">`Message`</span><span class="sxs-lookup"><span data-stu-id="b9fd6-120">Message</span></span>|<span data-ttu-id="b9fd6-121">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-121">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9fd6-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9fd6-122">Child Elements</span></span>  
  
|<span data-ttu-id="b9fd6-123">Element</span><span class="sxs-lookup"><span data-stu-id="b9fd6-123">Element</span></span>|<span data-ttu-id="b9fd6-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9fd6-124">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="b9fd6-125">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-125">Defines the settings for the message-level security.</span></span> <span data-ttu-id="b9fd6-126">Dieses Element ist vom Typ <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-126">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b9fd6-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9fd6-127">Parent Elements</span></span>  
  
|<span data-ttu-id="b9fd6-128">Element</span><span class="sxs-lookup"><span data-stu-id="b9fd6-128">Element</span></span>|<span data-ttu-id="b9fd6-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9fd6-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b9fd6-130">Definiert alle Bindungsfunktionen von [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b9fd6-130">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9fd6-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b9fd6-131">Remarks</span></span>  

 <span data-ttu-id="b9fd6-132">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-132">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="b9fd6-133">Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b9fd6-133">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9fd6-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9fd6-134">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="b9fd6-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="b9fd6-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b9fd6-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b9fd6-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b9fd6-137">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="b9fd6-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b9fd6-138">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="b9fd6-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
