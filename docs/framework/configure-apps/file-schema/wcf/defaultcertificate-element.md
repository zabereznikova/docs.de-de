---
title: <defaultCertificate>-Element
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400427"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="c8ac9-102">\<defaultCertificate-> Element</span><span class="sxs-lookup"><span data-stu-id="c8ac9-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="c8ac9-103">Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
<span data-ttu-id="c8ac9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8ac9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8ac9-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c8ac9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c8ac9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c8ac9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c8ac9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c8ac9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="c8ac9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c8ac9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="c8ac9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="c8ac9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="c8ac9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate->** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8ac9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="c8ac9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultCertificate->**</span><span class="sxs-lookup"><span data-stu-id="c8ac9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8ac9-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8ac9-112">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8ac9-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c8ac9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c8ac9-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8ac9-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="c8ac9-115">Attributes</span></span>  
  
|<span data-ttu-id="c8ac9-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="c8ac9-116">Attribute</span></span>|<span data-ttu-id="c8ac9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ac9-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8ac9-118">findValue</span><span class="sxs-lookup"><span data-stu-id="c8ac9-118">findValue</span></span>|<span data-ttu-id="c8ac9-119">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-119">String.</span></span> <span data-ttu-id="c8ac9-120">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-120">The value to search for.</span></span>|  
|<span data-ttu-id="c8ac9-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="c8ac9-121">x509FindType</span></span>|<span data-ttu-id="c8ac9-122">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-122">Enumeration.</span></span> <span data-ttu-id="c8ac9-123">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-123">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="c8ac9-124">storeLocation</span><span class="sxs-lookup"><span data-stu-id="c8ac9-124">storeLocation</span></span>|<span data-ttu-id="c8ac9-125">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-125">Enumeration.</span></span> <span data-ttu-id="c8ac9-126">Einer der zwei zu durchsuchenden Systemspeicherorte.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-126">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="c8ac9-127">storeName</span><span class="sxs-lookup"><span data-stu-id="c8ac9-127">storeName</span></span>|<span data-ttu-id="c8ac9-128">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-128">Enumeration.</span></span> <span data-ttu-id="c8ac9-129">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-129">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="c8ac9-130">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="c8ac9-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="c8ac9-131">Wert</span><span class="sxs-lookup"><span data-stu-id="c8ac9-131">Value</span></span>|<span data-ttu-id="c8ac9-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ac9-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c8ac9-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c8ac9-133">String</span></span>|<span data-ttu-id="c8ac9-134">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="c8ac9-135">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="c8ac9-136">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="c8ac9-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="c8ac9-137">Wert</span><span class="sxs-lookup"><span data-stu-id="c8ac9-137">Value</span></span>|<span data-ttu-id="c8ac9-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ac9-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c8ac9-139">Enumeration</span><span class="sxs-lookup"><span data-stu-id="c8ac9-139">Enumeration</span></span>|<span data-ttu-id="c8ac9-140">Mögliche Werte: FindByThumbprint, findbysubjetname, findbysubjetissushedname, FindByIssuerName, findbyissuererkennbar shedname, findbyserialnumber, FindByTimeValid, FindByTimeNotYetValid, findbyserialnumber, findbytimeabgelauf, findbytemplatename , Findbyapplicationpolicy, findbycertificatepolicy, findbyextension, findbykeyusage, findbysubjetkeyidentifier.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="c8ac9-141">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="c8ac9-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="c8ac9-142">Wert</span><span class="sxs-lookup"><span data-stu-id="c8ac9-142">Value</span></span>|<span data-ttu-id="c8ac9-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ac9-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c8ac9-144">Enumeration</span><span class="sxs-lookup"><span data-stu-id="c8ac9-144">Enumeration</span></span>|<span data-ttu-id="c8ac9-145">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="c8ac9-146">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="c8ac9-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="c8ac9-147">Wert</span><span class="sxs-lookup"><span data-stu-id="c8ac9-147">Value</span></span>|<span data-ttu-id="c8ac9-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ac9-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c8ac9-149">Enumeration</span><span class="sxs-lookup"><span data-stu-id="c8ac9-149">Enumeration</span></span>|<span data-ttu-id="c8ac9-150">Mögliche Werte: Addressbook, AuthRoot, CertificateAuthority, unallowed, my, root, treuhändpeople und Treuhänder Publisher.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8ac9-151">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8ac9-151">Child Elements</span></span>  
 <span data-ttu-id="c8ac9-152">Keine</span><span class="sxs-lookup"><span data-stu-id="c8ac9-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8ac9-153">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8ac9-153">Parent Elements</span></span>  
  
|<span data-ttu-id="c8ac9-154">Element</span><span class="sxs-lookup"><span data-stu-id="c8ac9-154">Element</span></span>|<span data-ttu-id="c8ac9-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ac9-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8ac9-156">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="c8ac9-156">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="c8ac9-157">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-157">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8ac9-158">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8ac9-158">Remarks</span></span>  
 <span data-ttu-id="c8ac9-159">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird das durch dieses Konfigurationselement angegebene Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-159">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="c8ac9-160">Es speichert ein einzelnes Zertifikat, das verwendent werden soll, wenn kein Zertifikat von einem Dienst angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-160">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8ac9-161">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8ac9-161">Example</span></span>  
 <span data-ttu-id="c8ac9-162">Das folgende Beispiel gibt ein Zertifikat an, das für Endpunkte verwendet wird, `http://www.contoso.com` deren URI mit beginnt, und ein Zertifikat, das für alle anderen Endpunkte verwendet werden soll, die keine Zertifikats Aushandlung ausführen.</span><span class="sxs-lookup"><span data-stu-id="c8ac9-162">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8ac9-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8ac9-163">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="c8ac9-164">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="c8ac9-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c8ac9-165">\<authentication></span><span class="sxs-lookup"><span data-stu-id="c8ac9-165">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="c8ac9-166">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="c8ac9-166">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="c8ac9-167">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="c8ac9-167">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
