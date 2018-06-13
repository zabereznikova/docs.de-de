---
title: '&lt;serviceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af59562dbf6c13970526f1665a9ba2c57c4f32ee
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766776"
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="5a898-102">&lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="5a898-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="5a898-103">Konfiguriert das x. 509-Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5a898-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="5a898-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="5a898-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="5a898-105">\<FederationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5a898-105">\<federationConfiguration></span></span>  
<span data-ttu-id="5a898-106">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="5a898-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a898-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a898-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a898-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5a898-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5a898-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a898-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a898-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="5a898-110">Attributes</span></span>  
 <span data-ttu-id="5a898-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="5a898-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a898-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a898-112">Child Elements</span></span>  
  
|<span data-ttu-id="5a898-113">Element</span><span class="sxs-lookup"><span data-stu-id="5a898-113">Element</span></span>|<span data-ttu-id="5a898-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a898-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a898-115">\<CertificateReference ></span><span class="sxs-lookup"><span data-stu-id="5a898-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="5a898-116">Gibt die Einstellungen, die zum finden und überprüfen ein x. 509-Zertifikat in keinem Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a898-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a898-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a898-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5a898-118">Element</span><span class="sxs-lookup"><span data-stu-id="5a898-118">Element</span></span>|<span data-ttu-id="5a898-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a898-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a898-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="5a898-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="5a898-121">Enthält die Einstellungen zur Konfiguration der <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="5a898-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5a898-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a898-122">Example</span></span>  
 <span data-ttu-id="5a898-123">Das folgende XML zeigt die Verwendung der \<ServiceCertificate >-Element.</span><span class="sxs-lookup"><span data-stu-id="5a898-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="5a898-124">Der XML-Code stammt aus dem `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5a898-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
