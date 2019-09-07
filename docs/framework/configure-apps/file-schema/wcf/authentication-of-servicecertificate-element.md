---
title: <authentication>of <serviceCertificate> -Element
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398230"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="6bcfc-102">\<Authentifizierungs > von \<serviceCertificate >-Element</span><span class="sxs-lookup"><span data-stu-id="6bcfc-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="6bcfc-103">Gibt die vom Clientproxy zum Authentifizieren von Dienstzertifikaten verwendeten Einstellungen an, die mittels SSL/TLS-Verhandlung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
<span data-ttu-id="6bcfc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bcfc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6bcfc-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6bcfc-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6bcfc-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6bcfc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6bcfc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6bcfc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="6bcfc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6bcfc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="6bcfc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="6bcfc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="6bcfc-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate->** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bcfc-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="6bcfc-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Authentifizierungs >**</span><span class="sxs-lookup"><span data-stu-id="6bcfc-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bcfc-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bcfc-112">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bcfc-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6bcfc-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6bcfc-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bcfc-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="6bcfc-115">Attributes</span></span>  
  
|<span data-ttu-id="6bcfc-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="6bcfc-116">Attribute</span></span>|<span data-ttu-id="6bcfc-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bcfc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6bcfc-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="6bcfc-118">customCertificateValidatorType</span></span>|<span data-ttu-id="6bcfc-119">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-119">String.</span></span> <span data-ttu-id="6bcfc-120">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-120">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="6bcfc-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="6bcfc-121">certificateValidationMode</span></span>|<span data-ttu-id="6bcfc-122">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="6bcfc-123">Ist dies auf `Custom` festgelegt, muss außerdem ein customCertificateValidator zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-123">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="6bcfc-124">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-124">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="6bcfc-125">revocationMode</span><span class="sxs-lookup"><span data-stu-id="6bcfc-125">revocationMode</span></span>|<span data-ttu-id="6bcfc-126">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="6bcfc-127">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-127">The default is `Online`.</span></span>|  
|<span data-ttu-id="6bcfc-128">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="6bcfc-128">trustedStoreLocation</span></span>|<span data-ttu-id="6bcfc-129">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="6bcfc-130">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="6bcfc-131">Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="6bcfc-132">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="6bcfc-133">customCertificateValidator-Attribut</span><span class="sxs-lookup"><span data-stu-id="6bcfc-133">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="6bcfc-134">Wert</span><span class="sxs-lookup"><span data-stu-id="6bcfc-134">Value</span></span>|<span data-ttu-id="6bcfc-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bcfc-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6bcfc-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6bcfc-136">String</span></span>|<span data-ttu-id="6bcfc-137">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-137">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="6bcfc-138">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="6bcfc-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="6bcfc-139">Wert</span><span class="sxs-lookup"><span data-stu-id="6bcfc-139">Value</span></span>|<span data-ttu-id="6bcfc-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bcfc-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6bcfc-141">Enumeration</span><span class="sxs-lookup"><span data-stu-id="6bcfc-141">Enumeration</span></span>|<span data-ttu-id="6bcfc-142">Einer der folgenden Werte: "None", "Peer Trust", "ChainTrust", "Peer-orchaintrust", "Custom"</span><span class="sxs-lookup"><span data-stu-id="6bcfc-142">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="6bcfc-143">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6bcfc-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="6bcfc-144">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="6bcfc-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="6bcfc-145">Wert</span><span class="sxs-lookup"><span data-stu-id="6bcfc-145">Value</span></span>|<span data-ttu-id="6bcfc-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bcfc-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6bcfc-147">Enumeration</span><span class="sxs-lookup"><span data-stu-id="6bcfc-147">Enumeration</span></span>|<span data-ttu-id="6bcfc-148">Einer der folgenden Werte: NOCHECK, Online, offline.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-148">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="6bcfc-149">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6bcfc-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="6bcfc-150">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="6bcfc-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="6bcfc-151">Wert</span><span class="sxs-lookup"><span data-stu-id="6bcfc-151">Value</span></span>|<span data-ttu-id="6bcfc-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bcfc-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6bcfc-153">Enumeration</span><span class="sxs-lookup"><span data-stu-id="6bcfc-153">Enumeration</span></span>|<span data-ttu-id="6bcfc-154">Einer der folgenden Werte: LocalMachine oder CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-154">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="6bcfc-155">Der Standardwert ist CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-155">The default is CurrentUser.</span></span> <span data-ttu-id="6bcfc-156">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-156">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="6bcfc-157">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-157">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bcfc-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6bcfc-158">Child Elements</span></span>  
 <span data-ttu-id="6bcfc-159">Keine</span><span class="sxs-lookup"><span data-stu-id="6bcfc-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bcfc-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6bcfc-160">Parent Elements</span></span>  
  
|<span data-ttu-id="6bcfc-161">Element</span><span class="sxs-lookup"><span data-stu-id="6bcfc-161">Element</span></span>|<span data-ttu-id="6bcfc-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bcfc-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bcfc-163">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="6bcfc-163">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="6bcfc-164">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-164">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bcfc-165">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6bcfc-165">Remarks</span></span>  
 <span data-ttu-id="6bcfc-166">Mit dem `certificateValidationMode`-Attribut dieses Konfigurationselements wird die Ebene der Vertrauenswürdigkeit angegeben, mit der Zertifikate authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-166">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="6bcfc-167">Standardmäßig wird die Ebene `ChainTrust` verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-167">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="6bcfc-168">Dies ist der sicherste Modus.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-168">This is the most secure mode.</span></span> <span data-ttu-id="6bcfc-169">Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-169">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="6bcfc-170">Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-170">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="6bcfc-171">Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-171">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="6bcfc-172">Sie können den Wert auch auf `Custom` oder `None` festlegen.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-172">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="6bcfc-173">Wenn Sie den `Custom`-Wert verwenden möchten, müssen Sie auch das `customCertificateValidator`-Attribut auf eine Assembly und einen Typ festlegen, die zur Validierung des Zertifikats verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-173">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="6bcfc-174">Wenn Sie eine eigene benutzerdefinierte Validierung erstellen möchten, müssen Sie von der abstrakten X509CertificateValidator-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-174">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="6bcfc-175">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Dienst, der ein benutzerdefiniertes](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)zertifikatvalidator verwendet.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-175">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="6bcfc-176">Das `revocationMode`-Attribut gibt an, wie Zertifikate auf eine Sperre hin überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-176">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="6bcfc-177">Der Standardwert ist `online`, wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-177">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="6bcfc-178">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6bcfc-178">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bcfc-179">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6bcfc-179">Example</span></span>  
 <span data-ttu-id="6bcfc-180">In folgendem Beispiel werden zwei Aufgaben ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-180">The following example does two tasks.</span></span> <span data-ttu-id="6bcfc-181">Zuerst wird ein Dienst Zertifikat angegeben, das der Client bei der Kommunikation mit Endpunkten, deren Domänen `www.contoso.com` Name sich über dem HTTP-Protokoll befindet, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-181">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="6bcfc-182">Danach gibt es den Sperrmodus und den Speicherort für die Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="6bcfc-182">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="6bcfc-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bcfc-183">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="6bcfc-184">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="6bcfc-184">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6bcfc-185">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="6bcfc-185">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="6bcfc-186">Vorgehensweise: Erstellen eines Dienstes, der ein benutzerdefiniertes zertifikatvalidator verwendet</span><span class="sxs-lookup"><span data-stu-id="6bcfc-186">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="6bcfc-187">\<authentication></span><span class="sxs-lookup"><span data-stu-id="6bcfc-187">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="6bcfc-188">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="6bcfc-188">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="6bcfc-189">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="6bcfc-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
