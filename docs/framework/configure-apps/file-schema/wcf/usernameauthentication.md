---
title: '&lt;userNameAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 1b8a85a3b2699aa88db24d1f7afee3de67dbf39b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656641"
---
# <a name="ltusernameauthenticationgt"></a><span data-ttu-id="1d5b8-102">&lt;userNameAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="1d5b8-102">&lt;userNameAuthentication&gt;</span></span>
<span data-ttu-id="1d5b8-103">Gibt die Anmeldeinformationen eines Diensts basierend auf Benutzername und Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-103">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="1d5b8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1d5b8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1d5b8-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="1d5b8-105">\<behaviors></span></span>  
<span data-ttu-id="1d5b8-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1d5b8-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1d5b8-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1d5b8-107">\<behavior></span></span>  
<span data-ttu-id="1d5b8-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1d5b8-108">\<serviceCredentials></span></span>  
<span data-ttu-id="1d5b8-109">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="1d5b8-109">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d5b8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d5b8-110">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d5b8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1d5b8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1d5b8-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d5b8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="1d5b8-113">Attributes</span></span>  
  
|<span data-ttu-id="1d5b8-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="1d5b8-114">Attribute</span></span>|<span data-ttu-id="1d5b8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d5b8-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="1d5b8-116">Eine <xref:System.TimeSpan>, die angibt, wie lange ein Token maximal zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-116">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="1d5b8-117">Der Standardwert ist 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-117">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="1d5b8-118">Ein boolescher Wert, der angibt, ob Anmeldetoken zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-118">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="1d5b8-119">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-119">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="1d5b8-120">Eine Zeichenfolge, die angibt, welche benutzerdefinierte Prüfung für Benutzername und Kennwort verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-120">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="1d5b8-121">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-121">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="1d5b8-122">Ein boolescher Wert, der angibt, ob Windows-Gruppen im Sicherheitskontext enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-122">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="1d5b8-123">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-123">The default is `true`.</span></span><br /><br /> <span data-ttu-id="1d5b8-124">Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-124">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="1d5b8-125">Legen Sie diese Eigenschaft auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-125">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="1d5b8-126">Eine ganze Zahl, die die maximale Anzahl an Anmeldetoken angibt, die zwischengespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-126">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="1d5b8-127">Dieser Wert muss größer als null sein.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-127">This value should be larger than zero.</span></span> <span data-ttu-id="1d5b8-128">Der Standard ist 128.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-128">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="1d5b8-129">Wenn das `clientCredentialType`-Attribut einer Bindung auf `username` festgelegt ist, wird der Benutzername Windows-Konten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-129">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="1d5b8-130">Sie können dieses Verhalten mit diesem Attribut überschreiben. Bei dem Attribut handelt es sich um eine Zeichenfolge mit dem Namen des <xref:System.Web.Security.MembershipProvider>-Werts, der den relevanten Mechanismus zur Kennwortprüfung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-130">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="1d5b8-131">Gibt die Art und Weise an, in der der Benutzername und das Kennwort überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-131">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="1d5b8-132">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="1d5b8-132">Valid values are:</span></span><br /><br /> <span data-ttu-id="1d5b8-133">-   Windows</span><span class="sxs-lookup"><span data-stu-id="1d5b8-133">-   Windows</span></span><br /><span data-ttu-id="1d5b8-134">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="1d5b8-134">-   MembershipProvider</span></span><br /><span data-ttu-id="1d5b8-135">-Custom</span><span class="sxs-lookup"><span data-stu-id="1d5b8-135">-   Custom</span></span><br /><br /> <span data-ttu-id="1d5b8-136">Der Standardwert ist Windows.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-136">The default is Windows.</span></span> <span data-ttu-id="1d5b8-137">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-137">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d5b8-138">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d5b8-138">Child Elements</span></span>  
 <span data-ttu-id="1d5b8-139">Keine</span><span class="sxs-lookup"><span data-stu-id="1d5b8-139">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d5b8-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d5b8-140">Parent Elements</span></span>  
  
|<span data-ttu-id="1d5b8-141">Element</span><span class="sxs-lookup"><span data-stu-id="1d5b8-141">Element</span></span>|<span data-ttu-id="1d5b8-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d5b8-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d5b8-143">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1d5b8-143">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="1d5b8-144">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-144">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d5b8-145">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d5b8-145">Remarks</span></span>  
 <span data-ttu-id="1d5b8-146">Wenn keine der von einem Dienst verwendeten Bindungen für die Benutzername/Kennwort-basierte Authentifizierung konfiguriert ist, werden die Attribute für dieses Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-146">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="1d5b8-147">Dazu gehören `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` und `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-147">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="1d5b8-148">Wenn keine der von einem Dienst verwendeten Bindungen für die Windows-Authentifizierung von Benutzername/Kennwort konfiguriert ist, werden die mit der Zwischenspeicherung von Anmeldetoken zusammenhängenden Eigenschaften ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-148">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="1d5b8-149">Dazu gehören `cacheLogonTokenLifetime`, `cacheLogonTokens` und `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="1d5b8-149">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d5b8-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d5b8-150">See also</span></span>
- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
