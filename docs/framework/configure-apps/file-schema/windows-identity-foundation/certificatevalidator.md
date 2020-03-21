---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152787"
---
# <a name="certificatevalidator"></a><span data-ttu-id="ef6cf-101">\<CertificateValidator></span><span class="sxs-lookup"><span data-stu-id="ef6cf-101">\<certificateValidator></span></span>
<span data-ttu-id="ef6cf-102">Gibt einen benutzerdefinierten Typ für die Zertifikatvalidierung an.</span><span class="sxs-lookup"><span data-stu-id="ef6cf-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="ef6cf-103">Dieser Typ wird nur `certificateValidationMode` verwendet, wenn das Attribut des [ \<certificateValidation>-Elements](certificatevalidation.md) auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ef6cf-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="ef6cf-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ef6cf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ef6cf-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="ef6cf-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="ef6cf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ef6cf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="ef6cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="ef6cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="ef6cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<CertificateValidator>**</span><span class="sxs-lookup"><span data-stu-id="ef6cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6cf-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef6cf-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef6cf-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ef6cf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ef6cf-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef6cf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef6cf-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="ef6cf-112">Attributes</span></span>  
  
|<span data-ttu-id="ef6cf-113">attribute</span><span class="sxs-lookup"><span data-stu-id="ef6cf-113">Attribute</span></span>|<span data-ttu-id="ef6cf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef6cf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef6cf-115">type</span><span class="sxs-lookup"><span data-stu-id="ef6cf-115">type</span></span>|<span data-ttu-id="ef6cf-116">Gibt einen benutzerdefinierten Typ an, <xref:System.IdentityModel.Selectors.X509CertificateValidator> der von der Klasse abstammt.</span><span class="sxs-lookup"><span data-stu-id="ef6cf-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="ef6cf-117">Legen `certificateValidationMode` Sie das Attribut des [ \<certificateValidation>-Elements](certificatevalidation.md) auf "Custom" fest, um diesen Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef6cf-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="ef6cf-118">Weitere Informationen zum Angeben `type` des Attributs finden Sie unter [Benutzerdefinierte Typreferenzen](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="ef6cf-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="ef6cf-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="ef6cf-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef6cf-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef6cf-120">Child Elements</span></span>  
 <span data-ttu-id="ef6cf-121">Keine</span><span class="sxs-lookup"><span data-stu-id="ef6cf-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef6cf-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef6cf-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ef6cf-123">Element</span><span class="sxs-lookup"><span data-stu-id="ef6cf-123">Element</span></span>|<span data-ttu-id="ef6cf-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef6cf-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef6cf-125">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="ef6cf-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="ef6cf-126">Steuert die Einstellungen, die Tokenhandler zum Überprüfen von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef6cf-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ef6cf-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef6cf-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
