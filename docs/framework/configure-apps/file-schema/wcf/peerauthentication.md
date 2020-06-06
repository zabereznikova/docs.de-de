---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 118159617a7f4c27ecc5e8fe077c28cfefac8537
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397621"
---
# \<peerAuthentication>
<span data-ttu-id="55e1e-101">Gibt die Authentifizierungseinstellungen für ein von einem Peerknoten verwendetes Peerzertifikat an.</span><span class="sxs-lookup"><span data-stu-id="55e1e-101">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="55e1e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="55e1e-102">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55e1e-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="55e1e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="55e1e-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55e1e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55e1e-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="55e1e-105">Attributes</span></span>  
  
|<span data-ttu-id="55e1e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="55e1e-106">Attribute</span></span>|<span data-ttu-id="55e1e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="55e1e-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="55e1e-108">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="55e1e-108">Optional enumeration.</span></span> <span data-ttu-id="55e1e-109">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="55e1e-109">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="55e1e-110">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="55e1e-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="55e1e-111">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="55e1e-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="55e1e-112">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="55e1e-112">Optional string.</span></span> <span data-ttu-id="55e1e-113">Bestimmt einen Typ und eine Assembly, die zum Prüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55e1e-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="55e1e-114">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="55e1e-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="55e1e-115">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="55e1e-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="55e1e-116">Windows Communication Foundation (WCF) stellt ein Standardmäßiges Peer Zertifikat-Validierungs Steuerelement bereit, das das Peer Zertifikat anhand des Speicher vertrauenswürdiger Personen überprüft.</span><span class="sxs-lookup"><span data-stu-id="55e1e-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="55e1e-117">Außerdem wird überprüft, ob sich das Zertifikat zu einem gültigen Stamm verkettet.</span><span class="sxs-lookup"><span data-stu-id="55e1e-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="55e1e-118">Sie können ein benutzerdefiniertes Validierungssteuerelement implementieren, um ein anderes Verhalten anzugeben und dieses Attribut zum Verweisen auf das benutzerdefinierte Validierungssteuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="55e1e-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="55e1e-119">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="55e1e-119">Optional enumeration.</span></span> <span data-ttu-id="55e1e-120">Legt den Zertifikatssperrmodus fest.</span><span class="sxs-lookup"><span data-stu-id="55e1e-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="55e1e-121">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="55e1e-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="55e1e-122">Das System stellt anhand der Liste mit den gesperrten Zertifikaten sicher, dass das Clientzertifikat nicht gesperrt wurde.</span><span class="sxs-lookup"><span data-stu-id="55e1e-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="55e1e-123">Diese Überprüfung kann entweder online oder offline mit einer zwischengespeicherten Liste gesperrter Zertifikate erfolgen.</span><span class="sxs-lookup"><span data-stu-id="55e1e-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="55e1e-124">Die Sperrüberprüfung kann deaktiviert werden, indem für dieses Attribut der Wert NoCheck festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="55e1e-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="55e1e-125">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="55e1e-125">Optional enumeration.</span></span> <span data-ttu-id="55e1e-126">Gibt den vertrauenswürdigen Speicherort an, an dem das Peer Zertifikat vom WCF-Sicherheitssystem überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="55e1e-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="55e1e-127">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="55e1e-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55e1e-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55e1e-128">Child Elements</span></span>  
 <span data-ttu-id="55e1e-129">Keine</span><span class="sxs-lookup"><span data-stu-id="55e1e-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55e1e-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55e1e-130">Parent Elements</span></span>  
  
|<span data-ttu-id="55e1e-131">Element</span><span class="sxs-lookup"><span data-stu-id="55e1e-131">Element</span></span>|<span data-ttu-id="55e1e-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55e1e-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="55e1e-133">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="55e1e-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55e1e-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="55e1e-134">Remarks</span></span>  
 <span data-ttu-id="55e1e-135">Das `<authentication>`-Element entspricht der <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="55e1e-135">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="55e1e-136">Mit diesem Element wird ein Validierungssteuerelement angegeben, das bei Nachbar-zu-Nachbar-Authentifizierung im Mesh aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="55e1e-136">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="55e1e-137">Versucht ein neuer Peer, eine Nachbarverbindung herzustellen, übergibt er seine eigenen Anmeldeinformationen an den antwortenden Peer.</span><span class="sxs-lookup"><span data-stu-id="55e1e-137">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="55e1e-138">Das Validierungssteuerelement des antwortenden Peers wird aufgerufen, um die Anmeldeinformationen der Remotepartei zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="55e1e-138">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="55e1e-139">Bei jeder Herstellung einer Peerverbindung im Mesh werden beide Peers gegenseitig authentifziert, das heißt, die Validierungssteuerelemente werden an beiden Enden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="55e1e-139">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e1e-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55e1e-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="55e1e-141">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="55e1e-141">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="55e1e-142">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="55e1e-142">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="55e1e-143">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="55e1e-143">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="55e1e-144">[Benutzerdefinierte Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="55e1e-144">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="55e1e-145">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="55e1e-145">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
