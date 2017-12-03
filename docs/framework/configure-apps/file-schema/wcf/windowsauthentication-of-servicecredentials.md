---
title: '&lt;windowsAuthentication&gt; von &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8af7d89fdf09316594bc8ef3433e2b47e8fb0a7e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltwindowsauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="9d1e4-102">&lt;windowsAuthentication&gt; von &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="9d1e4-102">&lt;windowsAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="9d1e4-103">Gibt die Einstellungen der Windows-Dienstanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="9d1e4-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9d1e4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9d1e4-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="9d1e4-105">\<behaviors></span></span>  
<span data-ttu-id="9d1e4-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9d1e4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9d1e4-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="9d1e4-107">\<behavior></span></span>  
<span data-ttu-id="9d1e4-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="9d1e4-108">\<serviceCredentials></span></span>  
<span data-ttu-id="9d1e4-109">\<WindowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="9d1e4-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d1e4-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d1e4-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d1e4-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9d1e4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9d1e4-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d1e4-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="9d1e4-113">Attributes</span></span>  
  
|<span data-ttu-id="9d1e4-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="9d1e4-114">Attribute</span></span>|<span data-ttu-id="9d1e4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d1e4-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="9d1e4-116">Ein optionales boolesches Attribut, das angibt, ob das System im Sicherheitskontext Windows-Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="9d1e4-117">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="9d1e4-118">Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="9d1e4-119">Legen Sie dieses Attribut auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="9d1e4-120">Ein optionales boolesches Attribut, das angibt, ob anonyme, nicht authentifizierte Aufrufer zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="9d1e4-121">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="9d1e4-122">Wenn das `clientCredentialType`-Attribut einer Bindung auf `Windows` festgelegt ist, sind im System keine anonymen Aufrufer zulässig.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="9d1e4-123">Dies bedeutet, dass nur authentifizierte Domänen- oder Arbeitsgruppenaufrufer berechtigt sind, auf das System zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="9d1e4-124">Sie können dieses Verhalten mit diesem Attribut überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="9d1e4-125">Verwenden Sie daher diese Einstellung nur mit extremer Vorsicht.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d1e4-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d1e4-126">Child Elements</span></span>  
 <span data-ttu-id="9d1e4-127">Keine</span><span class="sxs-lookup"><span data-stu-id="9d1e4-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d1e4-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d1e4-128">Parent Elements</span></span>  
  
|<span data-ttu-id="9d1e4-129">Element</span><span class="sxs-lookup"><span data-stu-id="9d1e4-129">Element</span></span>|<span data-ttu-id="9d1e4-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d1e4-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d1e4-131">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="9d1e4-131">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="9d1e4-132">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d1e4-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d1e4-133">Remarks</span></span>  
 <span data-ttu-id="9d1e4-134">Verwenden Sie dieses Element, um anzugeben, ob anonyme Windows-Benutzer Zugriff haben, indem Sie das `allowAnonymousLogons`-Attribut festlegen.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="9d1e4-135">Weiterhin können Sie angeben, ob Informationen zu der Gruppe, der die Benutzer angehören, in den Autorisierungskontext eingeschlossen werden, indem Sie das `includeWindowsGroups`-Attribut festlegen.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="9d1e4-136">Wenn das Attribut auf `true` (Standardeinstellung) festgelegt ist, kann der Dienst die Windows-Gruppen ermitteln, zu denen der Client gehört.</span><span class="sxs-lookup"><span data-stu-id="9d1e4-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d1e4-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d1e4-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>
