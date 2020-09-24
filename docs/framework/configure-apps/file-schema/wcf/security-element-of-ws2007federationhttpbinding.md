---
title: <security> Element von <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 943ccc241aef15b58661699408b085d98cf86c3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183701"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="13376-102">\<security> Element von \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="13376-102">\<security> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="13376-103">Definiert die Sicherheitseinstellungen des [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="13376-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="13376-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13376-104">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13376-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="13376-105">Attributes and Elements</span></span>  

 <span data-ttu-id="13376-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13376-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13376-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="13376-107">Attributes</span></span>  
  
|<span data-ttu-id="13376-108">attribute</span><span class="sxs-lookup"><span data-stu-id="13376-108">Attribute</span></span>|<span data-ttu-id="13376-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13376-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="13376-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="13376-110">Optional.</span></span> <span data-ttu-id="13376-111">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="13376-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="13376-112">Standardwert: `Message`.</span><span class="sxs-lookup"><span data-stu-id="13376-112">The default value is `Message`.</span></span> <span data-ttu-id="13376-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="13376-113">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="13376-114">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="13376-114">mode Attribute</span></span>  
  
|<span data-ttu-id="13376-115">Wert</span><span class="sxs-lookup"><span data-stu-id="13376-115">Value</span></span>|<span data-ttu-id="13376-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13376-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="13376-117">Keine</span><span class="sxs-lookup"><span data-stu-id="13376-117">None</span></span>|<span data-ttu-id="13376-118">Die SOAP-Nachricht ist während der Übertragung nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="13376-118">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="13376-119">`Message`</span><span class="sxs-lookup"><span data-stu-id="13376-119">Message</span></span>|<span data-ttu-id="13376-120">Integrität, Vertraulichkeit, Serverauthentifizierung und Clientauthentifizierung werden mittels SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="13376-120">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="13376-121">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="13376-121">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="13376-122">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="13376-122">The service must be configured with a certificate.</span></span> <span data-ttu-id="13376-123">Die Clientauthentifizierung basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="13376-123">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="13376-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="13376-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="13376-125">Integrität, Vertraulichkeit und Serverauthentifizierung werden über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="13376-125">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="13376-126">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="13376-126">The service must be configured with a certificate.</span></span> <span data-ttu-id="13376-127">Die Clientauthentifizierung wird mittels SOAP-Nachrichtensicherheit bereitgestellt und basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="13376-127">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13376-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13376-128">Child Elements</span></span>  
  
|<span data-ttu-id="13376-129">Element</span><span class="sxs-lookup"><span data-stu-id="13376-129">Element</span></span>|<span data-ttu-id="13376-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13376-130">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="13376-131">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="13376-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="13376-132">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="13376-132">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13376-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13376-133">Parent Elements</span></span>  
  
|<span data-ttu-id="13376-134">Element</span><span class="sxs-lookup"><span data-stu-id="13376-134">Element</span></span>|<span data-ttu-id="13376-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13376-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="13376-136">Definiert alle Bindungsfunktionen von [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="13376-136">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13376-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13376-137">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="13376-138">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="13376-138">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="13376-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="13376-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="13376-140">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="13376-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="13376-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="13376-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="13376-142">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="13376-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="13376-143">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="13376-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
