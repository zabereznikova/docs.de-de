---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 65b8aa6fa4422579ce0d1c5e33d3418ea051612a
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48776882"
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="eb3d8-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="eb3d8-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="eb3d8-103">Gibt einen benutzerdefinierten Typ für die Überprüfung des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="eb3d8-104">Dieser Typ wird verwendet, nur dann, wenn die `certificateValidationMode` Attribut der [ \<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element in "Benutzerdefiniert" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="eb3d8-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="eb3d8-105">\<system.identityModel></span></span>  
<span data-ttu-id="eb3d8-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="eb3d8-106">\<identityConfiguration></span></span>  
<span data-ttu-id="eb3d8-107">\<CertificateValidation ></span><span class="sxs-lookup"><span data-stu-id="eb3d8-107">\<certificateValidation></span></span>  
<span data-ttu-id="eb3d8-108">\<CertificateValidator ></span><span class="sxs-lookup"><span data-stu-id="eb3d8-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3d8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb3d8-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb3d8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb3d8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eb3d8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb3d8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb3d8-112">Attributes</span></span>  
  
|<span data-ttu-id="eb3d8-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="eb3d8-113">Attribute</span></span>|<span data-ttu-id="eb3d8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb3d8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb3d8-115">Typ</span><span class="sxs-lookup"><span data-stu-id="eb3d8-115">type</span></span>|<span data-ttu-id="eb3d8-116">Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Selectors.X509CertificateValidator> Klasse.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="eb3d8-117">Legen Sie die `certificateValidationMode` Attribut der [ \<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element auf "Custom" zum Verwenden dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="eb3d8-118">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="eb3d8-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="eb3d8-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb3d8-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb3d8-120">Child Elements</span></span>  
 <span data-ttu-id="eb3d8-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="eb3d8-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb3d8-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb3d8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="eb3d8-123">Element</span><span class="sxs-lookup"><span data-stu-id="eb3d8-123">Element</span></span>|<span data-ttu-id="eb3d8-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb3d8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb3d8-125">\<CertificateValidation ></span><span class="sxs-lookup"><span data-stu-id="eb3d8-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="eb3d8-126">Steuert die Einstellungen, die token-Handler zum Überprüfen von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eb3d8-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb3d8-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
