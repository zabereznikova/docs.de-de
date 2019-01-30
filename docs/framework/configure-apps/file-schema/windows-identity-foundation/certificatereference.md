---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 6c9c77f96ff6032de43d9b5a257bc0796a19b858
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269340"
---
# <a name="certificatereference"></a><span data-ttu-id="34e58-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="34e58-101">\<certificateReference></span></span>
<span data-ttu-id="34e58-102">Gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34e58-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="34e58-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="34e58-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="34e58-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="34e58-104">\<federationConfiguration></span></span>  
<span data-ttu-id="34e58-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="34e58-105">\<serviceCertificate></span></span>  
<span data-ttu-id="34e58-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="34e58-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e58-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="34e58-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34e58-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34e58-108">Attributes and Elements</span></span>  
 <span data-ttu-id="34e58-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34e58-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34e58-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="34e58-110">Attributes</span></span>  
  
|<span data-ttu-id="34e58-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="34e58-111">Attribute</span></span>|<span data-ttu-id="34e58-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34e58-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34e58-113">storeName</span><span class="sxs-lookup"><span data-stu-id="34e58-113">storeName</span></span>|<span data-ttu-id="34e58-114">Der Name des x. 509-Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="34e58-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="34e58-115">Der Standardwert ist "My".</span><span class="sxs-lookup"><span data-stu-id="34e58-115">The default is "My".</span></span> <span data-ttu-id="34e58-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="34e58-116">Optional.</span></span>|  
|<span data-ttu-id="34e58-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="34e58-117">storeLocation</span></span>|<span data-ttu-id="34e58-118">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den Speicherort des x. 509-Zertifikatspeichers angibt.</span><span class="sxs-lookup"><span data-stu-id="34e58-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="34e58-119">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="34e58-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="34e58-120">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="34e58-120">Optional.</span></span>|  
|<span data-ttu-id="34e58-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="34e58-121">x509FindType</span></span>|<span data-ttu-id="34e58-122">Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der Suche angibt, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34e58-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="34e58-123">Der Standardwert ist "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="34e58-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="34e58-124">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="34e58-124">Optional.</span></span>|  
|<span data-ttu-id="34e58-125">findValue</span><span class="sxs-lookup"><span data-stu-id="34e58-125">findValue</span></span>|<span data-ttu-id="34e58-126">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="34e58-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="34e58-127">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="34e58-127">Optional.</span></span>|  
|<span data-ttu-id="34e58-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="34e58-128">isChainIncluded</span></span>|<span data-ttu-id="34e58-129">Gibt an, ob die Validierung mithilfe der Zertifikatskette ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34e58-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="34e58-130">Der Standardwert ist "true"; Mithilfe der Zertifikatskette erfolgt die Validierung.</span><span class="sxs-lookup"><span data-stu-id="34e58-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="34e58-131">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="34e58-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34e58-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34e58-132">Child Elements</span></span>  
 <span data-ttu-id="34e58-133">Keine</span><span class="sxs-lookup"><span data-stu-id="34e58-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34e58-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34e58-134">Parent Elements</span></span>  
  
|<span data-ttu-id="34e58-135">Element</span><span class="sxs-lookup"><span data-stu-id="34e58-135">Element</span></span>|<span data-ttu-id="34e58-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34e58-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34e58-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="34e58-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="34e58-138">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="34e58-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34e58-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34e58-139">Remarks</span></span>  
 <span data-ttu-id="34e58-140">Die `<certificateReference>` Element gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34e58-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="34e58-141">Wenn er angegeben wird als untergeordnetes Element von der `<serviceCertficate>` -Element, es gibt die Speicherort und die Überprüfung der Einstellungen des x. 509-Zertifikats, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="34e58-141">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="34e58-142">Die `<certificateReference>` Element wird dargestellt, durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="34e58-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
