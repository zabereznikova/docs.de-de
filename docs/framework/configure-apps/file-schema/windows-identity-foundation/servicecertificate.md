---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: a3aba5618855f7225dc8a427516eaa72b45f6e8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942409"
---
# <a name="servicecertificate"></a><span data-ttu-id="eb170-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="eb170-101">\<serviceCertificate></span></span>
<span data-ttu-id="eb170-102">Konfiguriert das X. 509-Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eb170-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="eb170-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="eb170-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="eb170-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="eb170-104">\<federationConfiguration></span></span>  
<span data-ttu-id="eb170-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="eb170-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb170-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb170-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb170-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb170-107">Attributes and Elements</span></span>  
 <span data-ttu-id="eb170-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb170-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb170-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb170-109">Attributes</span></span>  
 <span data-ttu-id="eb170-110">None</span><span class="sxs-lookup"><span data-stu-id="eb170-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb170-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb170-111">Child Elements</span></span>  
  
|<span data-ttu-id="eb170-112">Element</span><span class="sxs-lookup"><span data-stu-id="eb170-112">Element</span></span>|<span data-ttu-id="eb170-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb170-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb170-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="eb170-114">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="eb170-115">Gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eb170-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb170-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb170-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eb170-117">Element</span><span class="sxs-lookup"><span data-stu-id="eb170-117">Element</span></span>|<span data-ttu-id="eb170-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb170-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb170-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="eb170-119">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="eb170-120">Enthält die Einstellungen, mit denen <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule> und (Sam) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="eb170-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eb170-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb170-121">Example</span></span>  
 <span data-ttu-id="eb170-122">Der folgende XML-Code zeigt die Verwendung \<des serviceCertificate->-Elements.</span><span class="sxs-lookup"><span data-stu-id="eb170-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="eb170-123">Der XML-Code stammt aus `CustomToken` dem Beispiel.</span><span class="sxs-lookup"><span data-stu-id="eb170-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
