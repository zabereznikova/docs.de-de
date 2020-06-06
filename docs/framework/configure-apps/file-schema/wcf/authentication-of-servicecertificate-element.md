---
title: <authentication>of- <serviceCertificate> Element
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398230"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="3cb15-102">\<authentication>of- \<serviceCertificate> Element</span><span class="sxs-lookup"><span data-stu-id="3cb15-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="3cb15-103">Gibt die vom Clientproxy zum Authentifizieren von Dienstzertifikaten verwendeten Einstellungen an, die mittels SSL/TLS-Verhandlung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3cb15-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="3cb15-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3cb15-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cb15-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3cb15-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3cb15-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3cb15-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cb15-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="3cb15-107">Attributes</span></span>  
  
|<span data-ttu-id="3cb15-108">attribute</span><span class="sxs-lookup"><span data-stu-id="3cb15-108">Attribute</span></span>|<span data-ttu-id="3cb15-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3cb15-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3cb15-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="3cb15-110">customCertificateValidatorType</span></span>|<span data-ttu-id="3cb15-111">Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3cb15-111">String.</span></span> <span data-ttu-id="3cb15-112">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3cb15-112">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="3cb15-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="3cb15-113">certificateValidationMode</span></span>|<span data-ttu-id="3cb15-114">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="3cb15-114">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="3cb15-115">Ist dies auf `Custom` festgelegt, muss außerdem ein customCertificateValidator zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3cb15-115">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="3cb15-116">Der Standardwert lautet `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="3cb15-116">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="3cb15-117">revocationMode</span><span class="sxs-lookup"><span data-stu-id="3cb15-117">revocationMode</span></span>|<span data-ttu-id="3cb15-118">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="3cb15-118">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="3cb15-119">Der Standardwert lautet `Online`.</span><span class="sxs-lookup"><span data-stu-id="3cb15-119">The default is `Online`.</span></span>|  
|<span data-ttu-id="3cb15-120">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="3cb15-120">trustedStoreLocation</span></span>|<span data-ttu-id="3cb15-121">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3cb15-121">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="3cb15-122">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="3cb15-122">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="3cb15-123">Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="3cb15-123">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="3cb15-124">Der Standardwert lautet `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3cb15-124">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="3cb15-125">customCertificateValidator-Attribut</span><span class="sxs-lookup"><span data-stu-id="3cb15-125">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="3cb15-126">Wert</span><span class="sxs-lookup"><span data-stu-id="3cb15-126">Value</span></span>|<span data-ttu-id="3cb15-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3cb15-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3cb15-128">String</span><span class="sxs-lookup"><span data-stu-id="3cb15-128">String</span></span>|<span data-ttu-id="3cb15-129">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="3cb15-129">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="3cb15-130">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="3cb15-130">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="3cb15-131">Wert</span><span class="sxs-lookup"><span data-stu-id="3cb15-131">Value</span></span>|<span data-ttu-id="3cb15-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3cb15-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3cb15-133">Enumeration</span><span class="sxs-lookup"><span data-stu-id="3cb15-133">Enumeration</span></span>|<span data-ttu-id="3cb15-134">Einer der folgenden Werte: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="3cb15-134">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="3cb15-135">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="3cb15-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="3cb15-136">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="3cb15-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="3cb15-137">Wert</span><span class="sxs-lookup"><span data-stu-id="3cb15-137">Value</span></span>|<span data-ttu-id="3cb15-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3cb15-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3cb15-139">Enumeration</span><span class="sxs-lookup"><span data-stu-id="3cb15-139">Enumeration</span></span>|<span data-ttu-id="3cb15-140">Einer der folgenden Werte: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="3cb15-140">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="3cb15-141">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="3cb15-141">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="3cb15-142">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="3cb15-142">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="3cb15-143">Wert</span><span class="sxs-lookup"><span data-stu-id="3cb15-143">Value</span></span>|<span data-ttu-id="3cb15-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3cb15-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3cb15-145">Enumeration</span><span class="sxs-lookup"><span data-stu-id="3cb15-145">Enumeration</span></span>|<span data-ttu-id="3cb15-146">Einer der folgenden Werte: LocalMachine oder CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="3cb15-146">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="3cb15-147">Der Standardwert lautet „CurrentUser“.</span><span class="sxs-lookup"><span data-stu-id="3cb15-147">The default is CurrentUser.</span></span> <span data-ttu-id="3cb15-148">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="3cb15-148">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="3cb15-149">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="3cb15-149">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cb15-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3cb15-150">Child Elements</span></span>  
 <span data-ttu-id="3cb15-151">Keine</span><span class="sxs-lookup"><span data-stu-id="3cb15-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cb15-152">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3cb15-152">Parent Elements</span></span>  
  
|<span data-ttu-id="3cb15-153">Element</span><span class="sxs-lookup"><span data-stu-id="3cb15-153">Element</span></span>|<span data-ttu-id="3cb15-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cb15-154">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="3cb15-155">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3cb15-155">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cb15-156">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3cb15-156">Remarks</span></span>  
 <span data-ttu-id="3cb15-157">Mit dem `certificateValidationMode`-Attribut dieses Konfigurationselements wird die Ebene der Vertrauenswürdigkeit angegeben, mit der Zertifikate authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="3cb15-157">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="3cb15-158">Standardmäßig wird die Ebene `ChainTrust` verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet.</span><span class="sxs-lookup"><span data-stu-id="3cb15-158">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="3cb15-159">Dies ist der sicherste Modus.</span><span class="sxs-lookup"><span data-stu-id="3cb15-159">This is the most secure mode.</span></span> <span data-ttu-id="3cb15-160">Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="3cb15-160">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="3cb15-161">Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3cb15-161">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="3cb15-162">Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="3cb15-162">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="3cb15-163">Sie können den Wert auch auf `Custom` oder `None` festlegen.</span><span class="sxs-lookup"><span data-stu-id="3cb15-163">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="3cb15-164">Wenn Sie den `Custom`-Wert verwenden möchten, müssen Sie auch das `customCertificateValidator`-Attribut auf eine Assembly und einen Typ festlegen, die zur Validierung des Zertifikats verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3cb15-164">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="3cb15-165">Wenn Sie eine eigene benutzerdefinierte Validierung erstellen möchten, müssen Sie von der abstrakten X509CertificateValidator-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="3cb15-165">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="3cb15-166">Weitere Informationen finden Sie unter Vorgehens [Weise: Erstellen eines Dienstanbieter, der ein benutzerdefiniertes zertifikatvalidator verwendet](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="3cb15-166">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="3cb15-167">Das `revocationMode`-Attribut gibt an, wie Zertifikate auf eine Sperre hin überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="3cb15-167">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="3cb15-168">Der Standardwert ist `online`, wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="3cb15-168">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="3cb15-169">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="3cb15-169">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cb15-170">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3cb15-170">Example</span></span>  
 <span data-ttu-id="3cb15-171">In folgendem Beispiel werden zwei Aufgaben ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3cb15-171">The following example does two tasks.</span></span> <span data-ttu-id="3cb15-172">Zuerst wird ein Dienst Zertifikat angegeben, das der Client bei der Kommunikation mit Endpunkten, deren Domänen Name sich über dem HTTP-Protokoll befindet, verwendet werden soll `www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="3cb15-172">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="3cb15-173">Danach gibt es den Sperrmodus und den Speicherort für die Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="3cb15-173">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3cb15-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3cb15-174">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="3cb15-175">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="3cb15-175">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3cb15-176">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="3cb15-176">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="3cb15-177">Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatsvalidierungssteuerelement verwendet</span><span class="sxs-lookup"><span data-stu-id="3cb15-177">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="3cb15-178">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="3cb15-178">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="3cb15-179">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="3cb15-179">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
