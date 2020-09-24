---
title: <defaultCertificate>-Element
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 2eaec4f4296f90579ca32d817f0a20da4ccc9a37
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153897"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="8737d-102">\<defaultCertificate>-Element</span><span class="sxs-lookup"><span data-stu-id="8737d-102">\<defaultCertificate> Element</span></span>

<span data-ttu-id="8737d-103">Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8737d-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="8737d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8737d-104">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8737d-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8737d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8737d-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8737d-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8737d-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="8737d-107">Attributes</span></span>  
  
|<span data-ttu-id="8737d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="8737d-108">Attribute</span></span>|<span data-ttu-id="8737d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8737d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8737d-110">findValue</span><span class="sxs-lookup"><span data-stu-id="8737d-110">findValue</span></span>|<span data-ttu-id="8737d-111">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8737d-111">String.</span></span> <span data-ttu-id="8737d-112">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="8737d-112">The value to search for.</span></span>|  
|<span data-ttu-id="8737d-113">x509FindType</span><span class="sxs-lookup"><span data-stu-id="8737d-113">x509FindType</span></span>|<span data-ttu-id="8737d-114">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="8737d-114">Enumeration.</span></span> <span data-ttu-id="8737d-115">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="8737d-115">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="8737d-116">storeLocation</span><span class="sxs-lookup"><span data-stu-id="8737d-116">storeLocation</span></span>|<span data-ttu-id="8737d-117">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="8737d-117">Enumeration.</span></span> <span data-ttu-id="8737d-118">Einer der zwei zu durchsuchenden Systemspeicherorte.</span><span class="sxs-lookup"><span data-stu-id="8737d-118">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="8737d-119">storeName</span><span class="sxs-lookup"><span data-stu-id="8737d-119">storeName</span></span>|<span data-ttu-id="8737d-120">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="8737d-120">Enumeration.</span></span> <span data-ttu-id="8737d-121">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="8737d-121">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="8737d-122">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="8737d-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="8737d-123">Wert</span><span class="sxs-lookup"><span data-stu-id="8737d-123">Value</span></span>|<span data-ttu-id="8737d-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8737d-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8737d-125">String</span><span class="sxs-lookup"><span data-stu-id="8737d-125">String</span></span>|<span data-ttu-id="8737d-126">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="8737d-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="8737d-127">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="8737d-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="8737d-128">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="8737d-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="8737d-129">Wert</span><span class="sxs-lookup"><span data-stu-id="8737d-129">Value</span></span>|<span data-ttu-id="8737d-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8737d-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8737d-131">Enumeration</span><span class="sxs-lookup"><span data-stu-id="8737d-131">Enumeration</span></span>|<span data-ttu-id="8737d-132">Zu den gültigen Werten gehören: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="8737d-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="8737d-133">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="8737d-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="8737d-134">Wert</span><span class="sxs-lookup"><span data-stu-id="8737d-134">Value</span></span>|<span data-ttu-id="8737d-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8737d-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8737d-136">Enumeration</span><span class="sxs-lookup"><span data-stu-id="8737d-136">Enumeration</span></span>|<span data-ttu-id="8737d-137">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="8737d-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="8737d-138">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="8737d-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="8737d-139">Wert</span><span class="sxs-lookup"><span data-stu-id="8737d-139">Value</span></span>|<span data-ttu-id="8737d-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8737d-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8737d-141">Enumeration</span><span class="sxs-lookup"><span data-stu-id="8737d-141">Enumeration</span></span>|<span data-ttu-id="8737d-142">Zu den gültigen Werten gehören: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople und TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="8737d-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8737d-143">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8737d-143">Child Elements</span></span>  

 <span data-ttu-id="8737d-144">Keine</span><span class="sxs-lookup"><span data-stu-id="8737d-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8737d-145">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8737d-145">Parent Elements</span></span>  
  
|<span data-ttu-id="8737d-146">Element</span><span class="sxs-lookup"><span data-stu-id="8737d-146">Element</span></span>|<span data-ttu-id="8737d-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8737d-147">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="8737d-148">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8737d-148">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8737d-149">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8737d-149">Remarks</span></span>  

 <span data-ttu-id="8737d-150">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird das durch dieses Konfigurationselement angegebene Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="8737d-150">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="8737d-151">Es speichert ein einzelnes Zertifikat, das verwendent werden soll, wenn kein Zertifikat von einem Dienst angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8737d-151">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8737d-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8737d-152">Example</span></span>  

 <span data-ttu-id="8737d-153">Das folgende Beispiel gibt ein Zertifikat an, das für Endpunkte verwendet wird, deren URI mit beginnt, `http://www.contoso.com` und ein Zertifikat, das für alle anderen Endpunkte verwendet werden soll, die keine Zertifikats Aushandlung ausführen.</span><span class="sxs-lookup"><span data-stu-id="8737d-153">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8737d-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8737d-154">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="8737d-155">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="8737d-155">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="8737d-156">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="8737d-156">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="8737d-157">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="8737d-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
