---
title: '&lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 819bb9dc9817050e45a39331361dd5489692f0b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltidentitygt"></a><span data-ttu-id="a770c-102">&lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="a770c-102">&lt;identity&gt;</span></span>
<span data-ttu-id="a770c-103">Mit dem Identitätselement kann ein Cliententwickler zur Entwurfszeit die erwartete Identität des Diensts angeben.</span><span class="sxs-lookup"><span data-stu-id="a770c-103">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="a770c-104">Beim Handshakeprozess zwischen Client und Dienst stellt die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Infrastruktur sicher, dass die Identität des erwarteten Diensts mit den Werten dieses Elements übereinstimmt, sodass eine Authentifizierung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="a770c-104">In the handshake process between the client and service, the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="a770c-105">Weitere Informationen finden Sie unter [-Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a770c-105">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="a770c-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a770c-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="a770c-107">\<Client ></span><span class="sxs-lookup"><span data-stu-id="a770c-107">\<client></span></span>  
<span data-ttu-id="a770c-108">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="a770c-108">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a770c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a770c-109">Syntax</span></span>  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a770c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a770c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a770c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a770c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a770c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a770c-112">Attributes</span></span>  
 <span data-ttu-id="a770c-113">Keine</span><span class="sxs-lookup"><span data-stu-id="a770c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a770c-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a770c-114">Child Elements</span></span>  
  
|<span data-ttu-id="a770c-115">Element</span><span class="sxs-lookup"><span data-stu-id="a770c-115">Element</span></span>|<span data-ttu-id="a770c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a770c-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a770c-117">certificate</span><span class="sxs-lookup"><span data-stu-id="a770c-117">certificate</span></span>|<span data-ttu-id="a770c-118">Gibt die Einstellungen eines X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="a770c-118">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="a770c-119">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="a770c-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="a770c-120">Es enthält ein `encodedValue`-Attribut, das eine Zeichenfolge ist, die den von diesem Zertifikat codierten Wert angibt.</span><span class="sxs-lookup"><span data-stu-id="a770c-120">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="a770c-121">certificateReference</span><span class="sxs-lookup"><span data-stu-id="a770c-121">certificateReference</span></span>|<span data-ttu-id="a770c-122">Legt die Einstellungen für die X.509-Zertifikatüberprüfung fest.</span><span class="sxs-lookup"><span data-stu-id="a770c-122">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="a770c-123">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="a770c-123">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="a770c-124">dns</span><span class="sxs-lookup"><span data-stu-id="a770c-124">dns</span></span>|<span data-ttu-id="a770c-125">Gibt den DNS eines X.509-Zertifikats an, das zum Authentifizieren eines Diensts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a770c-125">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="a770c-126">Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.</span><span class="sxs-lookup"><span data-stu-id="a770c-126">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="a770c-127">rsa</span><span class="sxs-lookup"><span data-stu-id="a770c-127">rsa</span></span>|<span data-ttu-id="a770c-128">Gibt den Wert des RSA-Felds eines für die Authentifizierung eines Diensts am Client verwendeten X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="a770c-128">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="a770c-129">Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.</span><span class="sxs-lookup"><span data-stu-id="a770c-129">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="a770c-130">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="a770c-130">servicePrincipalName</span></span>|<span data-ttu-id="a770c-131">Gibt eine SPN-Identität an, die dem Prinzipalnamen entspricht, der vom Client zum eindeutigen Identifizieren einer Dienstinstanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a770c-131">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="a770c-132">Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="a770c-132">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="a770c-133">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="a770c-133">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="a770c-134">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a770c-134">userPrincipalName</span></span>|<span data-ttu-id="a770c-135">Gibt eine UPN-Identität an, die dem Anmeldenamenstyp eines Benutzers in einem Netzwerk entspricht.</span><span class="sxs-lookup"><span data-stu-id="a770c-135">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="a770c-136">Der Benutzerprinzipalname besteht aus dem in Active Directory verwendeten Benutzerobjektnamen, gefolgt vom at-Symbol (@) und der übergeordneten Domäne im Domain Name System (DNS).</span><span class="sxs-lookup"><span data-stu-id="a770c-136">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="a770c-137">Z. B. möglicherweise Jeff in der Fabrikam.com-Domänenstruktur den Benutzerprinzipalnamen [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="a770c-137">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).  This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="a770c-138">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="a770c-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a770c-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a770c-139">Parent Elements</span></span>  
  
|<span data-ttu-id="a770c-140">Element</span><span class="sxs-lookup"><span data-stu-id="a770c-140">Element</span></span>|<span data-ttu-id="a770c-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a770c-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a770c-142">\<Benutzerdefinierte ></span><span class="sxs-lookup"><span data-stu-id="a770c-142">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="a770c-143">Gibt einen benutzerdefinierten Peerresolver für eine netPeerTcpBinding an.</span><span class="sxs-lookup"><span data-stu-id="a770c-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="a770c-144">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="a770c-144">\<endpoint></span></span>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)|<span data-ttu-id="a770c-145">Konfiguriert unterschiedliche Endpunkttypen.</span><span class="sxs-lookup"><span data-stu-id="a770c-145">Configures different types of endpoints.</span></span>|  
|[<span data-ttu-id="a770c-146">\<Aussteller ></span><span class="sxs-lookup"><span data-stu-id="a770c-146">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="a770c-147">Gibt den Sicherheitstokendienst (STS) für den Verbunddienst an.</span><span class="sxs-lookup"><span data-stu-id="a770c-147">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="a770c-148">\<IssuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="a770c-148">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="a770c-149">Gibt den Metadatenendpunkt für den Sicherheitstokendienst (STS) eines Verbunddiensts an.</span><span class="sxs-lookup"><span data-stu-id="a770c-149">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="a770c-150">\<IssuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="a770c-150">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="a770c-151">Definiert Parameter für ein ausgestelltes Token in einer benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="a770c-151">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="a770c-152">\<LocalIssuer ></span><span class="sxs-lookup"><span data-stu-id="a770c-152">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="a770c-153">Gibt einen lokalen Sicherheitstokendienst (STS) an.</span><span class="sxs-lookup"><span data-stu-id="a770c-153">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a770c-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a770c-154">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [<span data-ttu-id="a770c-155">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a770c-155">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a770c-156">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="a770c-156">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
