---
title: '&lt;certificateReference&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c8acf4b6d6e6e8a0fcf7d73139a1d2c5ea03f063
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="a08da-102">&lt;certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="a08da-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="a08da-103">Gibt die Einstellungen, die zum finden und überprüfen ein x. 509-Zertifikat in keinem Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a08da-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="a08da-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="a08da-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="a08da-105">\<FederationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a08da-105">\<federationConfiguration></span></span>  
<span data-ttu-id="a08da-106">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a08da-106">\<serviceCertificate></span></span>  
<span data-ttu-id="a08da-107">\<CertificateReference ></span><span class="sxs-lookup"><span data-stu-id="a08da-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a08da-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a08da-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a08da-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a08da-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a08da-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a08da-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a08da-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a08da-111">Attributes</span></span>  
  
|<span data-ttu-id="a08da-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="a08da-112">Attribute</span></span>|<span data-ttu-id="a08da-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a08da-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a08da-114">storeName</span><span class="sxs-lookup"><span data-stu-id="a08da-114">storeName</span></span>|<span data-ttu-id="a08da-115">Der Name des x. 509-Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="a08da-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="a08da-116">Die Standardeinstellung ist "My".</span><span class="sxs-lookup"><span data-stu-id="a08da-116">The default is "My".</span></span> <span data-ttu-id="a08da-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a08da-117">Optional.</span></span>|  
|<span data-ttu-id="a08da-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="a08da-118">storeLocation</span></span>|<span data-ttu-id="a08da-119">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den Speicherort des x. 509-Zertifikatspeichers angibt.</span><span class="sxs-lookup"><span data-stu-id="a08da-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="a08da-120">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="a08da-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="a08da-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a08da-121">Optional.</span></span>|  
|<span data-ttu-id="a08da-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="a08da-122">x509FindType</span></span>|<span data-ttu-id="a08da-123">Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der Suche angibt, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a08da-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="a08da-124">Der Standardwert ist "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="a08da-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="a08da-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a08da-125">Optional.</span></span>|  
|<span data-ttu-id="a08da-126">findValue</span><span class="sxs-lookup"><span data-stu-id="a08da-126">findValue</span></span>|<span data-ttu-id="a08da-127">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="a08da-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a08da-128">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a08da-128">Optional.</span></span>|  
|<span data-ttu-id="a08da-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="a08da-129">isChainIncluded</span></span>|<span data-ttu-id="a08da-130">Gibt an, ob die Überprüfung der Zertifikatkette mit ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a08da-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="a08da-131">Der Standardwert ist "true" Überprüfung erfolgt über die Zertifikatkette.</span><span class="sxs-lookup"><span data-stu-id="a08da-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="a08da-132">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a08da-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a08da-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a08da-133">Child Elements</span></span>  
 <span data-ttu-id="a08da-134">Keine</span><span class="sxs-lookup"><span data-stu-id="a08da-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a08da-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a08da-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a08da-136">Element</span><span class="sxs-lookup"><span data-stu-id="a08da-136">Element</span></span>|<span data-ttu-id="a08da-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a08da-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a08da-138">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a08da-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="a08da-139">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a08da-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a08da-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a08da-140">Remarks</span></span>  
 <span data-ttu-id="a08da-141">Die `<certificateReference>` -Element gibt die Einstellungen, die zum finden und überprüfen ein x. 509-Zertifikat in keinem Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a08da-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="a08da-142">Wenn er angegeben wird als untergeordnetes Element von der `<serviceCertficate>` -Element, es gibt die Speicherort und die Überprüfung der Einstellungen des x. 509-Zertifikats, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a08da-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="a08da-143">Die `<certificateReference>` Element dargestellt ist, durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a08da-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
