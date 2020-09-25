---
title: <messageSenderAuthentication>-Element
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: e7e636571c0dbb1845438c22f7e7509dfc7987f9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204787"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="14473-102">\<messageSenderAuthentication>-Element</span><span class="sxs-lookup"><span data-stu-id="14473-102">\<messageSenderAuthentication> element</span></span>

<span data-ttu-id="14473-103">Gibt die Authentifizierungsoptionen für Peer-to-Peer-Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="14473-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="14473-104">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="14473-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="14473-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="14473-105">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14473-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14473-106">Attributes and Elements</span></span>  

 <span data-ttu-id="14473-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14473-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14473-108">Attributes</span><span class="sxs-lookup"><span data-stu-id="14473-108">Attributes</span></span>  
  
|<span data-ttu-id="14473-109">attribute</span><span class="sxs-lookup"><span data-stu-id="14473-109">Attribute</span></span>|<span data-ttu-id="14473-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14473-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="14473-111">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14473-111">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="14473-112">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="14473-112">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="14473-113">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="14473-113">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="14473-114">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="14473-114">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="14473-115">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="14473-115">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="14473-116">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="14473-116">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="14473-117">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="14473-117">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="14473-118">Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="14473-118">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="14473-119">customCertificateValidatorType-Attribut</span><span class="sxs-lookup"><span data-stu-id="14473-119">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="14473-120">Wert</span><span class="sxs-lookup"><span data-stu-id="14473-120">Value</span></span>|<span data-ttu-id="14473-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="14473-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14473-122">String</span><span class="sxs-lookup"><span data-stu-id="14473-122">String</span></span>|<span data-ttu-id="14473-123">(Optional)</span><span class="sxs-lookup"><span data-stu-id="14473-123">Optional.</span></span> <span data-ttu-id="14473-124">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="14473-124">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="14473-125">Mindestens ein Namespace und Typname sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14473-125">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="14473-126">Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="14473-126">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="14473-127">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="14473-127">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="14473-128">Wert</span><span class="sxs-lookup"><span data-stu-id="14473-128">Value</span></span>|<span data-ttu-id="14473-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14473-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14473-130">Enumeration</span><span class="sxs-lookup"><span data-stu-id="14473-130">Enumeration</span></span>|<span data-ttu-id="14473-131">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="14473-131">Optional.</span></span> <span data-ttu-id="14473-132">Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="14473-132">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="14473-133">Der Standardwert lautet `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="14473-133">The default is `ChainTrust`.</span></span> <span data-ttu-id="14473-134">Der Standardwert lautet `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="14473-134">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="14473-135">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="14473-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="14473-136">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="14473-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="14473-137">Wert</span><span class="sxs-lookup"><span data-stu-id="14473-137">Value</span></span>|<span data-ttu-id="14473-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14473-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14473-139">Enumeration</span><span class="sxs-lookup"><span data-stu-id="14473-139">Enumeration</span></span>|<span data-ttu-id="14473-140">Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="14473-140">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="14473-141">Der Standardwert lautet `Online`.</span><span class="sxs-lookup"><span data-stu-id="14473-141">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="14473-142">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="14473-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="14473-143">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="14473-143">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="14473-144">Wert</span><span class="sxs-lookup"><span data-stu-id="14473-144">Value</span></span>|<span data-ttu-id="14473-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14473-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14473-146">Enumeration</span><span class="sxs-lookup"><span data-stu-id="14473-146">Enumeration</span></span>|<span data-ttu-id="14473-147">Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="14473-147">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="14473-148">Der Standardwert lautet `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="14473-148">The default is `CurrentUser`.</span></span> <span data-ttu-id="14473-149">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="14473-149">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="14473-150">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="14473-150">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="14473-151">Der Standardwert lautet `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="14473-151">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14473-152">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14473-152">Child Elements</span></span>  

 <span data-ttu-id="14473-153">Keine</span><span class="sxs-lookup"><span data-stu-id="14473-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14473-154">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14473-154">Parent Elements</span></span>  
  
|<span data-ttu-id="14473-155">Element</span><span class="sxs-lookup"><span data-stu-id="14473-155">Element</span></span>|<span data-ttu-id="14473-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14473-156">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="14473-157">Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14473-157">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14473-158">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="14473-158">Remarks</span></span>  

 <span data-ttu-id="14473-159">Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="14473-159">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="14473-160">Für Ausgabekanäle wird jede Nachricht mit dem von bereitgestellten Zertifikat signiert [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="14473-160">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="14473-161">Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="14473-161">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="14473-162">Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="14473-162">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14473-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14473-163">Example</span></span>  

 <span data-ttu-id="14473-164">Mit dem folgenden Code wird der Validierungsmodus des Nachrichtenabsenders auf `PeerOrChainTrust` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="14473-164">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="14473-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14473-165">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="14473-166">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="14473-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="14473-167">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="14473-167">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="14473-168">[Peerkanal-Nachrichtenauthentifizierung](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="14473-168">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="14473-169">[Benutzerdefinierte Peerkanal-Authentifizierung](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="14473-169">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="14473-170">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="14473-170">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
