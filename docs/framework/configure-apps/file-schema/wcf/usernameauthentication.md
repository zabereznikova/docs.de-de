---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 5a4cf8d429198b889f2bb362294ba3841c814b26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083139"
---
# <a name="usernameauthentication"></a><span data-ttu-id="ae9f8-101">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="ae9f8-101">\<userNameAuthentication></span></span>
<span data-ttu-id="ae9f8-102">Gibt die Anmeldeinformationen eines Diensts basierend auf Benutzername und Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-102">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="ae9f8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ae9f8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae9f8-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ae9f8-104">\<behaviors></span></span>  
<span data-ttu-id="ae9f8-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ae9f8-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="ae9f8-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ae9f8-106">\<behavior></span></span>  
<span data-ttu-id="ae9f8-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ae9f8-107">\<serviceCredentials></span></span>  
<span data-ttu-id="ae9f8-108">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="ae9f8-108">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9f8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae9f8-109">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae9f8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ae9f8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ae9f8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae9f8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="ae9f8-112">Attributes</span></span>  
  
|<span data-ttu-id="ae9f8-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="ae9f8-113">Attribute</span></span>|<span data-ttu-id="ae9f8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae9f8-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="ae9f8-115">Eine <xref:System.TimeSpan>, die angibt, wie lange ein Token maximal zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-115">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="ae9f8-116">Der Standardwert ist 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-116">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="ae9f8-117">Ein boolescher Wert, der angibt, ob Anmeldetoken zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-117">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="ae9f8-118">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-118">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="ae9f8-119">Eine Zeichenfolge, die angibt, welche benutzerdefinierte Prüfung für Benutzername und Kennwort verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-119">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="ae9f8-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-120">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="ae9f8-121">Ein boolescher Wert, der angibt, ob Windows-Gruppen im Sicherheitskontext enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-121">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="ae9f8-122">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-122">The default is `true`.</span></span><br /><br /> <span data-ttu-id="ae9f8-123">Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-123">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="ae9f8-124">Legen Sie diese Eigenschaft auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-124">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="ae9f8-125">Eine ganze Zahl, die die maximale Anzahl an Anmeldetoken angibt, die zwischengespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-125">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="ae9f8-126">Dieser Wert muss größer als null sein.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-126">This value should be larger than zero.</span></span> <span data-ttu-id="ae9f8-127">Der Standard ist 128.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-127">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="ae9f8-128">Wenn das `clientCredentialType`-Attribut einer Bindung auf `username` festgelegt ist, wird der Benutzername Windows-Konten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-128">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="ae9f8-129">Sie können dieses Verhalten mit diesem Attribut überschreiben. Bei dem Attribut handelt es sich um eine Zeichenfolge mit dem Namen des <xref:System.Web.Security.MembershipProvider>-Werts, der den relevanten Mechanismus zur Kennwortvalidierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-129">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="ae9f8-130">Gibt die Art und Weise an, in der der Benutzername und das Kennwort überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-130">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="ae9f8-131">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ae9f8-131">Valid values are:</span></span><br /><br /> <span data-ttu-id="ae9f8-132">-   Windows</span><span class="sxs-lookup"><span data-stu-id="ae9f8-132">-   Windows</span></span><br /><span data-ttu-id="ae9f8-133">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="ae9f8-133">-   MembershipProvider</span></span><br /><span data-ttu-id="ae9f8-134">-Custom</span><span class="sxs-lookup"><span data-stu-id="ae9f8-134">-   Custom</span></span><br /><br /> <span data-ttu-id="ae9f8-135">Der Standardwert ist Windows.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-135">The default is Windows.</span></span> <span data-ttu-id="ae9f8-136">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-136">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae9f8-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae9f8-137">Child Elements</span></span>  
 <span data-ttu-id="ae9f8-138">Keine</span><span class="sxs-lookup"><span data-stu-id="ae9f8-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae9f8-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae9f8-139">Parent Elements</span></span>  
  
|<span data-ttu-id="ae9f8-140">Element</span><span class="sxs-lookup"><span data-stu-id="ae9f8-140">Element</span></span>|<span data-ttu-id="ae9f8-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae9f8-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae9f8-142">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ae9f8-142">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="ae9f8-143">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-143">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae9f8-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae9f8-144">Remarks</span></span>  
 <span data-ttu-id="ae9f8-145">Wenn keine der von einem Dienst verwendeten Bindungen für die Benutzername/Kennwort-basierte Authentifizierung konfiguriert ist, werden die Attribute für dieses Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-145">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="ae9f8-146">Dazu gehören `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` und `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-146">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="ae9f8-147">Wenn keine der von einem Dienst verwendeten Bindungen für die Windows-Authentifizierung von Benutzername/Kennwort konfiguriert ist, werden die mit der Zwischenspeicherung von Anmeldetoken zusammenhängenden Eigenschaften ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-147">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="ae9f8-148">Dazu gehören `cacheLogonTokenLifetime`, `cacheLogonTokens` und `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="ae9f8-148">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9f8-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae9f8-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
