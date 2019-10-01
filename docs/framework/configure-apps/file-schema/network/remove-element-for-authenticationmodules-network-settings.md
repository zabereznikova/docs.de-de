---
title: <remove>-Element für authenticationModules (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 9b73c0dc1fe161616c08ef0501241d55e9fea9bc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697929"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="13c3b-102">\<remove >-Element für authenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="13c3b-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="13c3b-103">Entfernt ein Authentifizierungs Modul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="13c3b-103">Removes an authentication module from the application.</span></span>  
  
[<span data-ttu-id="13c3b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="13c3b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="13c3b-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="13c3b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="13c3b-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<authenticationmodules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="13c3b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="13c3b-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="13c3b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c3b-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="13c3b-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13c3b-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="13c3b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="13c3b-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13c3b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13c3b-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="13c3b-111">Attributes</span></span>  
  
|<span data-ttu-id="13c3b-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="13c3b-112">**Attribute**</span></span>|<span data-ttu-id="13c3b-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="13c3b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="13c3b-114">**Typ**</span><span class="sxs-lookup"><span data-stu-id="13c3b-114">**type**</span></span>|<span data-ttu-id="13c3b-115">Der Name des zu entfernenden Authentifizierungs Moduls.</span><span class="sxs-lookup"><span data-stu-id="13c3b-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13c3b-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13c3b-116">Child Elements</span></span>  
 <span data-ttu-id="13c3b-117">Keine</span><span class="sxs-lookup"><span data-stu-id="13c3b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13c3b-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13c3b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="13c3b-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="13c3b-119">**Element**</span></span>|<span data-ttu-id="13c3b-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="13c3b-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="13c3b-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="13c3b-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="13c3b-122">Gibt Module an, die zum Authentifizieren von Netzwerk Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13c3b-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13c3b-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13c3b-123">Remarks</span></span>  
 <span data-ttu-id="13c3b-124">Das `remove`-Element entfernt Authentifizierungs Module, die zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurations Hierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="13c3b-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="13c3b-125">Der Wert für das `type`-Attribut muss ein gültiger Klassenname sein.</span><span class="sxs-lookup"><span data-stu-id="13c3b-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="13c3b-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="13c3b-126">Configuration Files</span></span>  
 <span data-ttu-id="13c3b-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13c3b-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c3b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13c3b-128">Example</span></span>  
 <span data-ttu-id="13c3b-129">Im folgenden Beispiel wird ein Authentifizierungs Modul entfernt.</span><span class="sxs-lookup"><span data-stu-id="13c3b-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="13c3b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13c3b-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="13c3b-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="13c3b-131">Network Settings Schema</span></span>](index.md)
