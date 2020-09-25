---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 30fd78d6c56e8b22e0e744a38f18ac076dc70162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178033"
---
# \<userNameAuthentication>

<span data-ttu-id="7c18f-101">Gibt die Anmeldeinformationen eines Diensts basierend auf Benutzername und Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="7c18f-101">Specifies a service's credentials based on user name and password.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="7c18f-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c18f-102">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c18f-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7c18f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="7c18f-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7c18f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c18f-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="7c18f-105">Attributes</span></span>  
  
|<span data-ttu-id="7c18f-106">attribute</span><span class="sxs-lookup"><span data-stu-id="7c18f-106">Attribute</span></span>|<span data-ttu-id="7c18f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c18f-107">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="7c18f-108">Eine <xref:System.TimeSpan>, die angibt, wie lange ein Token maximal zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="7c18f-108">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="7c18f-109">Der Standardwert ist 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="7c18f-109">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="7c18f-110">Ein boolescher Wert, der angibt, ob Anmeldetoken zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="7c18f-110">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="7c18f-111">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="7c18f-111">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="7c18f-112">Eine Zeichenfolge, die angibt, welche benutzerdefinierte Prüfung für Benutzername und Kennwort verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c18f-112">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="7c18f-113">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7c18f-113">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="7c18f-114">Ein boolescher Wert, der angibt, ob Windows-Gruppen im Sicherheitskontext enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7c18f-114">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="7c18f-115">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="7c18f-115">The default is `true`.</span></span><br /><br /> <span data-ttu-id="7c18f-116">Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7c18f-116">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="7c18f-117">Legen Sie diese Eigenschaft auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="7c18f-117">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="7c18f-118">Eine ganze Zahl, die die maximale Anzahl an Anmeldetoken angibt, die zwischengespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="7c18f-118">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="7c18f-119">Dieser Wert muss größer als null sein.</span><span class="sxs-lookup"><span data-stu-id="7c18f-119">This value should be larger than zero.</span></span> <span data-ttu-id="7c18f-120">Der Standardwert ist 128.</span><span class="sxs-lookup"><span data-stu-id="7c18f-120">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="7c18f-121">Wenn das `clientCredentialType`-Attribut einer Bindung auf `username` festgelegt ist, wird der Benutzername Windows-Konten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7c18f-121">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="7c18f-122">Sie können dieses Verhalten mit diesem Attribut überschreiben. Bei dem Attribut handelt es sich um eine Zeichenfolge mit dem Namen des <xref:System.Web.Security.MembershipProvider>-Werts, der den relevanten Mechanismus zur Kennwortvalidierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7c18f-122">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="7c18f-123">Gibt die Art und Weise an, in der der Benutzername und das Kennwort überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="7c18f-123">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="7c18f-124">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7c18f-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="7c18f-125">-Windows</span><span class="sxs-lookup"><span data-stu-id="7c18f-125">-   Windows</span></span><br /><span data-ttu-id="7c18f-126">-Mitgliedshipprovider</span><span class="sxs-lookup"><span data-stu-id="7c18f-126">-   MembershipProvider</span></span><br /><span data-ttu-id="7c18f-127">-Benutzer definiert</span><span class="sxs-lookup"><span data-stu-id="7c18f-127">-   Custom</span></span><br /><br /> <span data-ttu-id="7c18f-128">Der Standardwert ist Windows.</span><span class="sxs-lookup"><span data-stu-id="7c18f-128">The default is Windows.</span></span> <span data-ttu-id="7c18f-129">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="7c18f-129">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c18f-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c18f-130">Child Elements</span></span>  

 <span data-ttu-id="7c18f-131">Keine</span><span class="sxs-lookup"><span data-stu-id="7c18f-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c18f-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c18f-132">Parent Elements</span></span>  
  
|<span data-ttu-id="7c18f-133">Element</span><span class="sxs-lookup"><span data-stu-id="7c18f-133">Element</span></span>|<span data-ttu-id="7c18f-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c18f-134">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="7c18f-135">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="7c18f-135">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c18f-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7c18f-136">Remarks</span></span>  

 <span data-ttu-id="7c18f-137">Wenn keine der von einem Dienst verwendeten Bindungen für die Benutzername/Kennwort-basierte Authentifizierung konfiguriert ist, werden die Attribute für dieses Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7c18f-137">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="7c18f-138">Dazu gehören `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` und `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="7c18f-138">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="7c18f-139">Wenn keine der von einem Dienst verwendeten Bindungen für die Windows-Authentifizierung von Benutzername/Kennwort konfiguriert ist, werden die mit der Zwischenspeicherung von Anmeldetoken zusammenhängenden Eigenschaften ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7c18f-139">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="7c18f-140">Dazu gehören `cacheLogonTokenLifetime`, `cacheLogonTokens` und `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="7c18f-140">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c18f-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c18f-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
