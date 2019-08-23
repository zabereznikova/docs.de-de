---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: da8ea128466457409334cd0b4ee3246a923f969a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941933"
---
# <a name="certificatereference"></a><span data-ttu-id="8225c-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="8225c-101">\<certificateReference></span></span>
<span data-ttu-id="8225c-102">Gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8225c-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="8225c-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="8225c-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="8225c-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="8225c-104">\<federationConfiguration></span></span>  
<span data-ttu-id="8225c-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="8225c-105">\<serviceCertificate></span></span>  
<span data-ttu-id="8225c-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="8225c-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8225c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8225c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8225c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8225c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8225c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8225c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8225c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="8225c-110">Attributes</span></span>  
  
|<span data-ttu-id="8225c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="8225c-111">Attribute</span></span>|<span data-ttu-id="8225c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8225c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8225c-113">storeName</span><span class="sxs-lookup"><span data-stu-id="8225c-113">storeName</span></span>|<span data-ttu-id="8225c-114">Der Name des X. 509-Zertifikats Speicher.</span><span class="sxs-lookup"><span data-stu-id="8225c-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="8225c-115">Der Standardwert ist "My".</span><span class="sxs-lookup"><span data-stu-id="8225c-115">The default is "My".</span></span> <span data-ttu-id="8225c-116">Optional.</span><span class="sxs-lookup"><span data-stu-id="8225c-116">Optional.</span></span>|  
|<span data-ttu-id="8225c-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="8225c-117">storeLocation</span></span>|<span data-ttu-id="8225c-118">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den Speicherort des X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="8225c-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="8225c-119">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="8225c-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="8225c-120">Optional.</span><span class="sxs-lookup"><span data-stu-id="8225c-120">Optional.</span></span>|  
|<span data-ttu-id="8225c-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="8225c-121">x509FindType</span></span>|<span data-ttu-id="8225c-122">Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> -Wert, der den Typ der auszuführenden Suche angibt.</span><span class="sxs-lookup"><span data-stu-id="8225c-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="8225c-123">Der Standardwert ist "findbysubjeterkennbare shedname".</span><span class="sxs-lookup"><span data-stu-id="8225c-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="8225c-124">Optional.</span><span class="sxs-lookup"><span data-stu-id="8225c-124">Optional.</span></span>|  
|<span data-ttu-id="8225c-125">findValue</span><span class="sxs-lookup"><span data-stu-id="8225c-125">findValue</span></span>|<span data-ttu-id="8225c-126">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8225c-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="8225c-127">Optional.</span><span class="sxs-lookup"><span data-stu-id="8225c-127">Optional.</span></span>|  
|<span data-ttu-id="8225c-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="8225c-128">isChainIncluded</span></span>|<span data-ttu-id="8225c-129">Gibt an, ob die Überprüfung mithilfe der Zertifikat Kette durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8225c-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="8225c-130">Der Standardwert ist "true". die Überprüfung erfolgt mithilfe der Zertifikat Kette.</span><span class="sxs-lookup"><span data-stu-id="8225c-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="8225c-131">Optional.</span><span class="sxs-lookup"><span data-stu-id="8225c-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8225c-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8225c-132">Child Elements</span></span>  
 <span data-ttu-id="8225c-133">None</span><span class="sxs-lookup"><span data-stu-id="8225c-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8225c-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8225c-134">Parent Elements</span></span>  
  
|<span data-ttu-id="8225c-135">Element</span><span class="sxs-lookup"><span data-stu-id="8225c-135">Element</span></span>|<span data-ttu-id="8225c-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8225c-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8225c-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="8225c-137">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="8225c-138">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8225c-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8225c-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8225c-139">Remarks</span></span>  
 <span data-ttu-id="8225c-140">Das `<certificateReference>` -Element gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8225c-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="8225c-141">Wenn es als untergeordnetes Element des `<serviceCertificate>` -Elements angegeben ist, gibt es den Speicherort und die Überprüfungs Einstellungen des X. 509-Zertifikats an, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8225c-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="8225c-142">Das `<certificateReference>` -Element wird durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8225c-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
