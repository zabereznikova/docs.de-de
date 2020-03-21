---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152813"
---
# <a name="certificatereference"></a><span data-ttu-id="59e2b-101">\<certificateReferenz></span><span class="sxs-lookup"><span data-stu-id="59e2b-101">\<certificateReference></span></span>
<span data-ttu-id="59e2b-102">Gibt Einstellungen an, die zum Suchen und Überprüfen eines X.509-Zertifikats in einem Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59e2b-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="59e2b-103">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="59e2b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="59e2b-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="59e2b-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="59e2b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<FederationConfiguration>**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="59e2b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="59e2b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="59e2b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="59e2b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReferenz>**</span><span class="sxs-lookup"><span data-stu-id="59e2b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e2b-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="59e2b-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59e2b-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="59e2b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59e2b-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="59e2b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59e2b-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="59e2b-111">Attributes</span></span>  
  
|<span data-ttu-id="59e2b-112">attribute</span><span class="sxs-lookup"><span data-stu-id="59e2b-112">Attribute</span></span>|<span data-ttu-id="59e2b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59e2b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59e2b-114">storeName</span><span class="sxs-lookup"><span data-stu-id="59e2b-114">storeName</span></span>|<span data-ttu-id="59e2b-115">Der Namen des X.509-Zertifikatsspeichers.</span><span class="sxs-lookup"><span data-stu-id="59e2b-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="59e2b-116">Der Standardwert ist "Mein".</span><span class="sxs-lookup"><span data-stu-id="59e2b-116">The default is "My".</span></span> <span data-ttu-id="59e2b-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="59e2b-117">Optional.</span></span>|  
|<span data-ttu-id="59e2b-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="59e2b-118">storeLocation</span></span>|<span data-ttu-id="59e2b-119">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den Speicherort des X.509-Zertifikatspeichers angibt.</span><span class="sxs-lookup"><span data-stu-id="59e2b-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="59e2b-120">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="59e2b-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="59e2b-121">Optional.</span><span class="sxs-lookup"><span data-stu-id="59e2b-121">Optional.</span></span>|  
|<span data-ttu-id="59e2b-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="59e2b-122">x509FindType</span></span>|<span data-ttu-id="59e2b-123">Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Suchtyp angibt, der ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="59e2b-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="59e2b-124">Der Standardwert ist "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="59e2b-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="59e2b-125">Optional.</span><span class="sxs-lookup"><span data-stu-id="59e2b-125">Optional.</span></span>|  
|<span data-ttu-id="59e2b-126">findValue</span><span class="sxs-lookup"><span data-stu-id="59e2b-126">findValue</span></span>|<span data-ttu-id="59e2b-127">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="59e2b-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="59e2b-128">Optional.</span><span class="sxs-lookup"><span data-stu-id="59e2b-128">Optional.</span></span>|  
|<span data-ttu-id="59e2b-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="59e2b-129">isChainIncluded</span></span>|<span data-ttu-id="59e2b-130">Gibt an, ob die Validierung mithilfe der Zertifikatkette durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="59e2b-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="59e2b-131">Der Standardwert ist "true"; Die Validierung wird mithilfe der Zertifikatkette durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="59e2b-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="59e2b-132">Optional.</span><span class="sxs-lookup"><span data-stu-id="59e2b-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59e2b-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59e2b-133">Child Elements</span></span>  
 <span data-ttu-id="59e2b-134">Keine</span><span class="sxs-lookup"><span data-stu-id="59e2b-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59e2b-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59e2b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="59e2b-136">Element</span><span class="sxs-lookup"><span data-stu-id="59e2b-136">Element</span></span>|<span data-ttu-id="59e2b-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59e2b-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59e2b-138">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="59e2b-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="59e2b-139">Konfiguriert das Zertifikat, das zum Ver- und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="59e2b-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59e2b-140">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="59e2b-140">Remarks</span></span>  
 <span data-ttu-id="59e2b-141">Das `<certificateReference>` Element gibt Einstellungen an, die zum Suchen und Überprüfen eines X.509-Zertifikats in einem Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59e2b-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="59e2b-142">Wenn es als untergeordnetes Element `<serviceCertificate>` des Elements angegeben wird, gibt es den Speicherort und die Überprüfungseinstellungen des X.509-Zertifikats an, das zum Ver- und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="59e2b-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="59e2b-143">Das `<certificateReference>` Element wird <xref:System.ServiceModel.Configuration.CertificateReferenceElement> durch die Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="59e2b-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
