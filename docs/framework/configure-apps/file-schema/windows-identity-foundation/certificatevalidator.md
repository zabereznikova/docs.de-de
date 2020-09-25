---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 8476600769b6099bb885566de4c908c78a2dbbda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201372"
---
# \<certificateValidator>

<span data-ttu-id="61944-101">Gibt einen benutzerdefinierten Typ für die Zertifikats Überprüfung an.</span><span class="sxs-lookup"><span data-stu-id="61944-101">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="61944-102">Dieser Typ wird nur verwendet, wenn das- `certificateValidationMode` Attribut des- [\<certificateValidation>](certificatevalidation.md) Elements auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="61944-102">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**  
  
## <a name="syntax"></a><span data-ttu-id="61944-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="61944-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61944-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="61944-104">Attributes and Elements</span></span>  

 <span data-ttu-id="61944-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61944-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61944-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="61944-106">Attributes</span></span>  
  
|<span data-ttu-id="61944-107">attribute</span><span class="sxs-lookup"><span data-stu-id="61944-107">Attribute</span></span>|<span data-ttu-id="61944-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="61944-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61944-109">type</span><span class="sxs-lookup"><span data-stu-id="61944-109">type</span></span>|<span data-ttu-id="61944-110">Gibt einen benutzerdefinierten Typ an, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="61944-110">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="61944-111">Legen Sie das- `certificateValidationMode` Attribut des- [\<certificateValidation>](certificatevalidation.md) Elements auf "Custom" fest, um diesen Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="61944-111">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="61944-112">Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="61944-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="61944-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="61944-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61944-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61944-114">Child Elements</span></span>  

 <span data-ttu-id="61944-115">Keine</span><span class="sxs-lookup"><span data-stu-id="61944-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61944-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61944-116">Parent Elements</span></span>  
  
|<span data-ttu-id="61944-117">Element</span><span class="sxs-lookup"><span data-stu-id="61944-117">Element</span></span>|<span data-ttu-id="61944-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61944-118">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="61944-119">Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61944-119">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="61944-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61944-120">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
