---
title: '&lt;certificateValidator&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 98112b3f13ff0b8e4be50f158ce40b048b213248
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="1df96-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="1df96-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="1df96-103">Gibt einen benutzerdefinierten Typ für die Überprüfung des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="1df96-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="1df96-104">Dieser Typ wird nur verwendet, wenn die `certificateValidationMode` Attribut von der [ \<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element auf "Benutzerdefiniert" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1df96-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="1df96-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="1df96-105">\<system.identityModel></span></span>  
<span data-ttu-id="1df96-106">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="1df96-106">\<identityConfiguration></span></span>  
<span data-ttu-id="1df96-107">\<CertificateValidation ></span><span class="sxs-lookup"><span data-stu-id="1df96-107">\<certificateValidation></span></span>  
<span data-ttu-id="1df96-108">\<CertificateValidator ></span><span class="sxs-lookup"><span data-stu-id="1df96-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df96-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1df96-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1df96-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1df96-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1df96-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1df96-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1df96-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="1df96-112">Attributes</span></span>  
  
|<span data-ttu-id="1df96-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="1df96-113">Attribute</span></span>|<span data-ttu-id="1df96-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1df96-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1df96-115">Typ</span><span class="sxs-lookup"><span data-stu-id="1df96-115">type</span></span>|<span data-ttu-id="1df96-116">Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Selectors.X509CertificateValidator> Klasse.</span><span class="sxs-lookup"><span data-stu-id="1df96-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="1df96-117">Legen Sie die `certificateValidationMode` Attribut des der [ \<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element auf "Custom", um diesen Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="1df96-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="1df96-118">Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="1df96-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="1df96-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1df96-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1df96-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1df96-120">Child Elements</span></span>  
 <span data-ttu-id="1df96-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="1df96-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1df96-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1df96-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1df96-123">Element</span><span class="sxs-lookup"><span data-stu-id="1df96-123">Element</span></span>|<span data-ttu-id="1df96-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1df96-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1df96-125">\<CertificateValidation ></span><span class="sxs-lookup"><span data-stu-id="1df96-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="1df96-126">Steuert die Einstellungen, die Tokenhandler verwenden, um Zertifikate zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1df96-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1df96-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1df96-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
