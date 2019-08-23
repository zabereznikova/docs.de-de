---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: c25f183679f41f51ffee4f482bfe7a64763647d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941902"
---
# <a name="certificatevalidator"></a><span data-ttu-id="78100-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="78100-101">\<certificateValidator></span></span>
<span data-ttu-id="78100-102">Gibt einen benutzerdefinierten Typ für die Zertifikats Überprüfung an.</span><span class="sxs-lookup"><span data-stu-id="78100-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="78100-103">Dieser Typ wird nur verwendet, wenn `certificateValidationMode` das-Attribut [ \<des certifiinitievalidation->](certificatevalidation.md) -Elements auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="78100-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="78100-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="78100-104">\<system.identityModel></span></span>  
<span data-ttu-id="78100-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="78100-105">\<identityConfiguration></span></span>  
<span data-ttu-id="78100-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="78100-106">\<certificateValidation></span></span>  
<span data-ttu-id="78100-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="78100-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78100-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="78100-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78100-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="78100-109">Attributes and Elements</span></span>  
 <span data-ttu-id="78100-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="78100-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78100-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="78100-111">Attributes</span></span>  
  
|<span data-ttu-id="78100-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="78100-112">Attribute</span></span>|<span data-ttu-id="78100-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78100-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78100-114">Typ</span><span class="sxs-lookup"><span data-stu-id="78100-114">type</span></span>|<span data-ttu-id="78100-115">Gibt einen benutzerdefinierten Typ an, der <xref:System.IdentityModel.Selectors.X509CertificateValidator> von der-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="78100-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="78100-116">Legen Sie `certificateValidationMode` das-Attribut [ \<des certifialievalidation->](certificatevalidation.md) Elements auf "Custom" fest, um diesen Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="78100-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="78100-117">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="78100-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="78100-118">Optional.</span><span class="sxs-lookup"><span data-stu-id="78100-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78100-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="78100-119">Child Elements</span></span>  
 <span data-ttu-id="78100-120">None</span><span class="sxs-lookup"><span data-stu-id="78100-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78100-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="78100-121">Parent Elements</span></span>  
  
|<span data-ttu-id="78100-122">Element</span><span class="sxs-lookup"><span data-stu-id="78100-122">Element</span></span>|<span data-ttu-id="78100-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78100-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78100-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="78100-124">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="78100-125">Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="78100-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="78100-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="78100-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
