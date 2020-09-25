---
title: <windowsAuthentication> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: bda375959b535ce5f2996d594f719893164b0bd4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194998"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="1f124-102">\<windowsAuthentication> von \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1f124-102">\<windowsAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="1f124-103">Gibt die Einstellungen der Windows-Dienstanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1f124-103">Specifies the settings of a Windows service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="1f124-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f124-104">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f124-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1f124-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1f124-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1f124-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f124-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="1f124-107">Attributes</span></span>  
  
|<span data-ttu-id="1f124-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1f124-108">Attribute</span></span>|<span data-ttu-id="1f124-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f124-109">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="1f124-110">Ein optionales boolesches Attribut, das angibt, ob das System im Sicherheitskontext Windows-Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="1f124-110">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="1f124-111">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="1f124-111">The default is `true`.</span></span><br /><br /> <span data-ttu-id="1f124-112">Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1f124-112">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="1f124-113">Legen Sie dieses Attribut auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="1f124-113">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="1f124-114">Ein optionales boolesches Attribut, das angibt, ob anonyme, nicht authentifizierte Aufrufer zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="1f124-114">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="1f124-115">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="1f124-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="1f124-116">Wenn das `clientCredentialType`-Attribut einer Bindung auf `Windows` festgelegt ist, sind im System keine anonymen Aufrufer zulässig.</span><span class="sxs-lookup"><span data-stu-id="1f124-116">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="1f124-117">Dies bedeutet, dass nur authentifizierte Domänen- oder Arbeitsgruppenaufrufer berechtigt sind, auf das System zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1f124-117">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="1f124-118">Sie können dieses Verhalten mit diesem Attribut überschreiben.</span><span class="sxs-lookup"><span data-stu-id="1f124-118">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="1f124-119">Verwenden Sie daher diese Einstellung nur mit extremer Vorsicht.</span><span class="sxs-lookup"><span data-stu-id="1f124-119">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f124-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1f124-120">Child Elements</span></span>  

 <span data-ttu-id="1f124-121">Keine</span><span class="sxs-lookup"><span data-stu-id="1f124-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f124-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1f124-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1f124-123">Element</span><span class="sxs-lookup"><span data-stu-id="1f124-123">Element</span></span>|<span data-ttu-id="1f124-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f124-124">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="1f124-125">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="1f124-125">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f124-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1f124-126">Remarks</span></span>  

 <span data-ttu-id="1f124-127">Verwenden Sie dieses Element, um anzugeben, ob anonyme Windows-Benutzer Zugriff haben, indem Sie das `allowAnonymousLogons`-Attribut festlegen.</span><span class="sxs-lookup"><span data-stu-id="1f124-127">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="1f124-128">Weiterhin können Sie angeben, ob Informationen zu der Gruppe, der die Benutzer angehören, in den Autorisierungskontext eingeschlossen werden, indem Sie das `includeWindowsGroups`-Attribut festlegen.</span><span class="sxs-lookup"><span data-stu-id="1f124-128">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="1f124-129">Wenn das Attribut auf `true` (Standardeinstellung) festgelegt ist, kann der Dienst die Windows-Gruppen ermitteln, zu denen der Client gehört.</span><span class="sxs-lookup"><span data-stu-id="1f124-129">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f124-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f124-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
