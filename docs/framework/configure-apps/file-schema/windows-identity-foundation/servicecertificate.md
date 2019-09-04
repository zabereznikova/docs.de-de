---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251859"
---
# <a name="servicecertificate"></a><span data-ttu-id="c03c7-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="c03c7-101">\<serviceCertificate></span></span>
<span data-ttu-id="c03c7-102">Konfiguriert das X. 509-Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c03c7-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
<span data-ttu-id="c03c7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c03c7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c03c7-104">&nbsp;&nbsp;[ **\<System. IdentityModel. Services->** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="c03c7-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="c03c7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationconfiguration->** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c03c7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="c03c7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate->**</span><span class="sxs-lookup"><span data-stu-id="c03c7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c03c7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c03c7-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c03c7-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c03c7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c03c7-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c03c7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c03c7-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c03c7-110">Attributes</span></span>  
 <span data-ttu-id="c03c7-111">None</span><span class="sxs-lookup"><span data-stu-id="c03c7-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c03c7-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c03c7-112">Child Elements</span></span>  
  
|<span data-ttu-id="c03c7-113">Element</span><span class="sxs-lookup"><span data-stu-id="c03c7-113">Element</span></span>|<span data-ttu-id="c03c7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c03c7-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c03c7-115">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="c03c7-115">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="c03c7-116">Gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c03c7-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c03c7-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c03c7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c03c7-118">Element</span><span class="sxs-lookup"><span data-stu-id="c03c7-118">Element</span></span>|<span data-ttu-id="c03c7-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c03c7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c03c7-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="c03c7-120">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="c03c7-121">Enthält die Einstellungen, mit denen <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule> und (Sam) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c03c7-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c03c7-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c03c7-122">Example</span></span>  
 <span data-ttu-id="c03c7-123">Der folgende XML-Code zeigt die Verwendung \<des serviceCertificate->-Elements.</span><span class="sxs-lookup"><span data-stu-id="c03c7-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="c03c7-124">Der XML-Code stammt aus `CustomToken` dem Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c03c7-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
