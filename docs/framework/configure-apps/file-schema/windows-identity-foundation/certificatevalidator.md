---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 30f81dd5948a7d366c1116cffd347c85a396f5ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252124"
---
# <a name="certificatevalidator"></a><span data-ttu-id="7dad4-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="7dad4-101">\<certificateValidator></span></span>
<span data-ttu-id="7dad4-102">Gibt einen benutzerdefinierten Typ für die Zertifikats Überprüfung an.</span><span class="sxs-lookup"><span data-stu-id="7dad4-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="7dad4-103">Dieser Typ wird nur verwendet, wenn `certificateValidationMode` das-Attribut [ \<des certifiinitievalidation->](certificatevalidation.md) -Elements auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7dad4-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="7dad4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7dad4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7dad4-105">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="7dad4-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="7dad4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="7dad4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="7dad4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<certifialievalidation->** ](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="7dad4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="7dad4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certifialievalidator->**</span><span class="sxs-lookup"><span data-stu-id="7dad4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dad4-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dad4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dad4-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7dad4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7dad4-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7dad4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dad4-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7dad4-112">Attributes</span></span>  
  
|<span data-ttu-id="7dad4-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7dad4-113">Attribute</span></span>|<span data-ttu-id="7dad4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dad4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7dad4-115">Typ</span><span class="sxs-lookup"><span data-stu-id="7dad4-115">type</span></span>|<span data-ttu-id="7dad4-116">Gibt einen benutzerdefinierten Typ an, der <xref:System.IdentityModel.Selectors.X509CertificateValidator> von der-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="7dad4-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="7dad4-117">Legen Sie `certificateValidationMode` das-Attribut [ \<des certifialievalidation->](certificatevalidation.md) Elements auf "Custom" fest, um diesen Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7dad4-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="7dad4-118">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="7dad4-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="7dad4-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="7dad4-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dad4-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dad4-120">Child Elements</span></span>  
 <span data-ttu-id="7dad4-121">None</span><span class="sxs-lookup"><span data-stu-id="7dad4-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7dad4-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dad4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7dad4-123">Element</span><span class="sxs-lookup"><span data-stu-id="7dad4-123">Element</span></span>|<span data-ttu-id="7dad4-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dad4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dad4-125">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="7dad4-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="7dad4-126">Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dad4-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7dad4-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dad4-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
