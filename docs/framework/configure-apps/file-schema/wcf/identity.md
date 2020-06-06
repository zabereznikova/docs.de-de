---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 15c9e38a141fc294c47863b1a932711444ac079a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855153"
---
# \<identity>
<span data-ttu-id="2fbbf-101">Mit dem Identitätselement kann ein Cliententwickler zur Entwurfszeit die erwartete Identität des Diensts angeben.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-101">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="2fbbf-102">Beim Hand Shake Prozess zwischen Client und Dienst stellt die Windows Communication Foundation (WCF)-Infrastruktur sicher, dass die Identität des erwarteten Dienstanbieter mit den Werten dieses Elements übereinstimmt und somit authentifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-102">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="2fbbf-103">Weitere Informationen finden Sie unter [Dienst Identität und-Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2fbbf-103">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a><span data-ttu-id="2fbbf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fbbf-104">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fbbf-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2fbbf-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2fbbf-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fbbf-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="2fbbf-107">Attributes</span></span>  
 <span data-ttu-id="2fbbf-108">Keine</span><span class="sxs-lookup"><span data-stu-id="2fbbf-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2fbbf-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fbbf-109">Child Elements</span></span>  
  
|<span data-ttu-id="2fbbf-110">Element</span><span class="sxs-lookup"><span data-stu-id="2fbbf-110">Element</span></span>|<span data-ttu-id="2fbbf-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2fbbf-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fbbf-112">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="2fbbf-112">certificate</span></span>|<span data-ttu-id="2fbbf-113">Gibt die Einstellungen eines X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-113">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="2fbbf-114">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-114">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="2fbbf-115">Es enthält ein `encodedValue`-Attribut, das eine Zeichenfolge ist, die den von diesem Zertifikat codierten Wert angibt.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-115">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="2fbbf-116">certificateReference</span><span class="sxs-lookup"><span data-stu-id="2fbbf-116">certificateReference</span></span>|<span data-ttu-id="2fbbf-117">Legt die Einstellungen für die X.509-Zertifikatüberprüfung fest.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-117">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="2fbbf-118">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="2fbbf-119">dns</span><span class="sxs-lookup"><span data-stu-id="2fbbf-119">dns</span></span>|<span data-ttu-id="2fbbf-120">Gibt den DNS eines X.509-Zertifikats an, das zum Authentifizieren eines Diensts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-120">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="2fbbf-121">Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-121">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="2fbbf-122">rsa</span><span class="sxs-lookup"><span data-stu-id="2fbbf-122">rsa</span></span>|<span data-ttu-id="2fbbf-123">Gibt den Wert des RSA-Felds eines für die Authentifizierung eines Diensts am Client verwendeten X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-123">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="2fbbf-124">Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-124">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="2fbbf-125">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="2fbbf-125">servicePrincipalName</span></span>|<span data-ttu-id="2fbbf-126">Gibt eine SPN-Identität an, die dem Prinzipalnamen entspricht, der vom Client zum eindeutigen Identifizieren einer Dienstinstanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-126">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="2fbbf-127">Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-127">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="2fbbf-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-128">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="2fbbf-129">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2fbbf-129">userPrincipalName</span></span>|<span data-ttu-id="2fbbf-130">Gibt eine UPN-Identität an, die dem Anmeldenamenstyp eines Benutzers in einem Netzwerk entspricht.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-130">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="2fbbf-131">Der Benutzer Prinzipal Name besteht aus dem in Active Directory verwendeten Benutzerobjekt Namen, gefolgt vom at-Symbol ( \@ ) und dann in der Regel der Domain Name System übergeordneten Domäne.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-131">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="2fbbf-132">Beispielsweise könnte Jeff in der Fabrikam.com-Domänen Struktur über den Benutzer Prinzipal Namen verfügen [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) .</span><span class="sxs-lookup"><span data-stu-id="2fbbf-132">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="2fbbf-133">Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-133">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="2fbbf-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-134">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2fbbf-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fbbf-135">Parent Elements</span></span>  
  
|<span data-ttu-id="2fbbf-136">Element</span><span class="sxs-lookup"><span data-stu-id="2fbbf-136">Element</span></span>|<span data-ttu-id="2fbbf-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2fbbf-137">Description</span></span>|  
|-------------|-----------------|  
|[\<custom>](custom.md)|<span data-ttu-id="2fbbf-138">Gibt einen benutzerdefinierten Peerresolver für eine netPeerTcpBinding an.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-138">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="2fbbf-139">Konfiguriert Dienst Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-139">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="2fbbf-140">\<endpoint>Natürlich\<client></span><span class="sxs-lookup"><span data-stu-id="2fbbf-140">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="2fbbf-141">Konfiguriert Kanal Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-141">Configures channel endpoints.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="2fbbf-142">Gibt den Sicherheitstokendienst (STS) für den Verbunddienst an.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-142">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="2fbbf-143">Gibt den Metadatenendpunkt für den Sicherheitstokendienst (STS) eines Verbunddiensts an.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-143">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="2fbbf-144">Definiert Parameter für ein ausgestelltes Token in einer benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-144">Defines parameters for an issued token in a custom binding.</span></span>|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="2fbbf-145">Gibt einen lokalen Sicherheitstokendienst (STS) an.</span><span class="sxs-lookup"><span data-stu-id="2fbbf-145">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fbbf-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2fbbf-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="2fbbf-147">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2fbbf-147">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2fbbf-148">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="2fbbf-148">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
