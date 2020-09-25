---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: e7888d01838312aa51397ca39133edb9318fac80
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204774"
---
# \<messageSenderAuthentication>

<span data-ttu-id="e193e-101">Gibt Authentifizierungseinstellungen für ein Peerzertifikat an, das von einem Nachrichtenabsender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e193e-101">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="e193e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="e193e-102">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e193e-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e193e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e193e-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e193e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e193e-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="e193e-105">Attributes</span></span>  
  
|<span data-ttu-id="e193e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="e193e-106">Attribute</span></span>|<span data-ttu-id="e193e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e193e-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="e193e-108">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e193e-108">Optional enumeration.</span></span> <span data-ttu-id="e193e-109">Gibt einen von fünf die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="e193e-109">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="e193e-110">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="e193e-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="e193e-111">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e193e-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="e193e-112">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e193e-112">Optional string.</span></span> <span data-ttu-id="e193e-113">Bestimmt einen Typ und eine Assembly, die zum Prüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e193e-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="e193e-114">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e193e-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="e193e-115">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="e193e-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="e193e-116">Windows Communication Foundation (WCF) stellt ein Standardmäßiges Peer Zertifikat-Validierungs Steuerelement bereit, das das Peer Zertifikat anhand des Speicher vertrauenswürdiger Personen überprüft.</span><span class="sxs-lookup"><span data-stu-id="e193e-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="e193e-117">Außerdem wird überprüft, ob sich das Zertifikat zu einem gültigen Stamm verkettet.</span><span class="sxs-lookup"><span data-stu-id="e193e-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="e193e-118">Sie können ein benutzerdefiniertes Validierungssteuerelement implementieren, um ein anderes Verhalten anzugeben und dieses Attribut zum Verweisen auf das benutzerdefinierte Validierungssteuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="e193e-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="e193e-119">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e193e-119">Optional enumeration.</span></span> <span data-ttu-id="e193e-120">Legt den Zertifikatssperrmodus fest.</span><span class="sxs-lookup"><span data-stu-id="e193e-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="e193e-121">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="e193e-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="e193e-122">Das System stellt anhand der Liste mit den gesperrten Zertifikaten sicher, dass das Clientzertifikat nicht gesperrt wurde.</span><span class="sxs-lookup"><span data-stu-id="e193e-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="e193e-123">Diese Überprüfung kann entweder online oder offline mit einer zwischengespeicherten Liste gesperrter Zertifikate erfolgen.</span><span class="sxs-lookup"><span data-stu-id="e193e-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="e193e-124">Die Sperrüberprüfung kann deaktiviert werden, indem für dieses Attribut der Wert NoCheck festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e193e-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="e193e-125">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e193e-125">Optional enumeration.</span></span> <span data-ttu-id="e193e-126">Gibt den vertrauenswürdigen Speicherort an, an dem das Peer Zertifikat vom WCF-Sicherheitssystem überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="e193e-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="e193e-127">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="e193e-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e193e-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e193e-128">Child Elements</span></span>  

 <span data-ttu-id="e193e-129">Keine</span><span class="sxs-lookup"><span data-stu-id="e193e-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e193e-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e193e-130">Parent Elements</span></span>  
  
|<span data-ttu-id="e193e-131">Element</span><span class="sxs-lookup"><span data-stu-id="e193e-131">Element</span></span>|<span data-ttu-id="e193e-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e193e-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="e193e-133">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="e193e-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e193e-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e193e-134">Remarks</span></span>  

 <span data-ttu-id="e193e-135">Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="e193e-135">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="e193e-136">Für Ausgabekanäle wird jede Nachricht mit dem von bereitgestellten Zertifikat signiert [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="e193e-136">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="e193e-137">Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="e193e-137">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="e193e-138">Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="e193e-138">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e193e-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e193e-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="e193e-140">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="e193e-140">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e193e-141">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="e193e-141">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="e193e-142">[Peerkanal-Nachrichtenauthentifizierung](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e193e-142">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="e193e-143">[Benutzerdefinierte Peerkanal-Authentifizierung](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e193e-143">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="e193e-144">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="e193e-144">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
