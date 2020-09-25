---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c21e5186b8afdf8c72cbfc605af94c95bc2bc0d5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201375"
---
# \<certificateReference>

<span data-ttu-id="74ccc-101">Gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="74ccc-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="74ccc-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="74ccc-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74ccc-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="74ccc-103">Attributes and Elements</span></span>  

 <span data-ttu-id="74ccc-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74ccc-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74ccc-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="74ccc-105">Attributes</span></span>  
  
|<span data-ttu-id="74ccc-106">attribute</span><span class="sxs-lookup"><span data-stu-id="74ccc-106">Attribute</span></span>|<span data-ttu-id="74ccc-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74ccc-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74ccc-108">storeName</span><span class="sxs-lookup"><span data-stu-id="74ccc-108">storeName</span></span>|<span data-ttu-id="74ccc-109">Der Namen des X.509-Zertifikatsspeichers.</span><span class="sxs-lookup"><span data-stu-id="74ccc-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="74ccc-110">Der Standardwert ist "My".</span><span class="sxs-lookup"><span data-stu-id="74ccc-110">The default is "My".</span></span> <span data-ttu-id="74ccc-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="74ccc-111">Optional.</span></span>|  
|<span data-ttu-id="74ccc-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="74ccc-112">storeLocation</span></span>|<span data-ttu-id="74ccc-113">Ein- <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den Speicherort des X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="74ccc-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="74ccc-114">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="74ccc-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="74ccc-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="74ccc-115">Optional.</span></span>|  
|<span data-ttu-id="74ccc-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="74ccc-116">x509FindType</span></span>|<span data-ttu-id="74ccc-117">Ein- <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der auszuführenden Suche angibt.</span><span class="sxs-lookup"><span data-stu-id="74ccc-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="74ccc-118">Der Standardwert ist "findbysubjeterkennbare shedname".</span><span class="sxs-lookup"><span data-stu-id="74ccc-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="74ccc-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="74ccc-119">Optional.</span></span>|  
|<span data-ttu-id="74ccc-120">findValue</span><span class="sxs-lookup"><span data-stu-id="74ccc-120">findValue</span></span>|<span data-ttu-id="74ccc-121">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="74ccc-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="74ccc-122">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="74ccc-122">Optional.</span></span>|  
|<span data-ttu-id="74ccc-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="74ccc-123">isChainIncluded</span></span>|<span data-ttu-id="74ccc-124">Gibt an, ob die Überprüfung mithilfe der Zertifikat Kette durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="74ccc-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="74ccc-125">Der Standardwert ist "true". die Überprüfung erfolgt mithilfe der Zertifikat Kette.</span><span class="sxs-lookup"><span data-stu-id="74ccc-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="74ccc-126">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="74ccc-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74ccc-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74ccc-127">Child Elements</span></span>  

 <span data-ttu-id="74ccc-128">Keine</span><span class="sxs-lookup"><span data-stu-id="74ccc-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74ccc-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74ccc-129">Parent Elements</span></span>  
  
|<span data-ttu-id="74ccc-130">Element</span><span class="sxs-lookup"><span data-stu-id="74ccc-130">Element</span></span>|<span data-ttu-id="74ccc-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74ccc-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="74ccc-132">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="74ccc-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74ccc-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="74ccc-133">Remarks</span></span>  

 <span data-ttu-id="74ccc-134">Das- `<certificateReference>` Element gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="74ccc-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="74ccc-135">Wenn es als untergeordnetes Element des-Elements angegeben ist `<serviceCertificate>` , gibt es den Speicherort und die Überprüfungs Einstellungen des X. 509-Zertifikats an, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="74ccc-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="74ccc-136">Das- `<certificateReference>` Element wird durch die- <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="74ccc-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
