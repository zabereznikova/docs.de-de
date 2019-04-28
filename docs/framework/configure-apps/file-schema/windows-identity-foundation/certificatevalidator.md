---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: df52212305e0865b8c03fdd49068cb7c7da4fa38
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667365"
---
# <a name="certificatevalidator"></a><span data-ttu-id="771ba-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="771ba-101">\<certificateValidator></span></span>
<span data-ttu-id="771ba-102">Gibt einen benutzerdefinierten Typ für die Überprüfung des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="771ba-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="771ba-103">Dieser Typ wird verwendet, nur dann, wenn die `certificateValidationMode` Attribut der [ \<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element in "Benutzerdefiniert" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="771ba-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="771ba-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="771ba-104">\<system.identityModel></span></span>  
<span data-ttu-id="771ba-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="771ba-105">\<identityConfiguration></span></span>  
<span data-ttu-id="771ba-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="771ba-106">\<certificateValidation></span></span>  
<span data-ttu-id="771ba-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="771ba-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="771ba-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="771ba-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="771ba-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="771ba-109">Attributes and Elements</span></span>  
 <span data-ttu-id="771ba-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="771ba-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="771ba-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="771ba-111">Attributes</span></span>  
  
|<span data-ttu-id="771ba-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="771ba-112">Attribute</span></span>|<span data-ttu-id="771ba-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="771ba-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="771ba-114">Typ</span><span class="sxs-lookup"><span data-stu-id="771ba-114">type</span></span>|<span data-ttu-id="771ba-115">Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Selectors.X509CertificateValidator> Klasse.</span><span class="sxs-lookup"><span data-stu-id="771ba-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="771ba-116">Legen Sie die `certificateValidationMode` Attribut der [ \<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element auf "Custom" zum Verwenden dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="771ba-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="771ba-117">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="771ba-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="771ba-118">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="771ba-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="771ba-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="771ba-119">Child Elements</span></span>  
 <span data-ttu-id="771ba-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="771ba-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="771ba-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="771ba-121">Parent Elements</span></span>  
  
|<span data-ttu-id="771ba-122">Element</span><span class="sxs-lookup"><span data-stu-id="771ba-122">Element</span></span>|<span data-ttu-id="771ba-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="771ba-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="771ba-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="771ba-124">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="771ba-125">Steuert die Einstellungen, die token-Handler zum Überprüfen von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="771ba-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="771ba-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="771ba-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
