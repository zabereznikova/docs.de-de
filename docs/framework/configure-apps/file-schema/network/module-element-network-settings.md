---
title: <module>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 78f6418160b80096214c6e37268a5a90498d6d4d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089240"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="64f1b-102">\<Module > Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="64f1b-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="64f1b-103">Fügt der Anwendung ein neues Proxymodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="64f1b-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="64f1b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="64f1b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="64f1b-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="64f1b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="64f1b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="64f1b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="64f1b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Modul >**</span><span class="sxs-lookup"><span data-stu-id="64f1b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="64f1b-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="64f1b-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64f1b-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="64f1b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="64f1b-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64f1b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64f1b-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="64f1b-111">Attributes</span></span>  
  
|<span data-ttu-id="64f1b-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="64f1b-112">**Attribute**</span></span>|<span data-ttu-id="64f1b-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="64f1b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="64f1b-114">Der voll qualifizierte Typname (angegeben durch die <xref:System.Type.FullName%2A>-Eigenschaft) und der AssemblyName (angegeben durch die <xref:System.Reflection.Assembly.FullName%2A>-Eigenschaft), getrennt durch ein Komma, das den Proxy implementiert.</span><span class="sxs-lookup"><span data-stu-id="64f1b-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64f1b-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64f1b-115">Child Elements</span></span>  
 <span data-ttu-id="64f1b-116">Keine</span><span class="sxs-lookup"><span data-stu-id="64f1b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64f1b-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64f1b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="64f1b-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="64f1b-118">**Element**</span></span>|<span data-ttu-id="64f1b-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="64f1b-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="64f1b-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="64f1b-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="64f1b-121">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="64f1b-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64f1b-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64f1b-122">Remarks</span></span>  
 <span data-ttu-id="64f1b-123">Das `module`-Element registriert Proxy Klassen, die die <xref:System.Net.IWebProxy>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="64f1b-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="64f1b-124">Nach dem Registrieren der Proxy Klasse können `module` zum Anfordern von Informationen über den unterstützten Proxy verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64f1b-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="64f1b-125">Der Wert für das `type` Attribut sollte der Klassenname des Moduls und der Name der entsprechenden DLL (Dynamic Link Library) sein.</span><span class="sxs-lookup"><span data-stu-id="64f1b-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="64f1b-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="64f1b-126">Configuration Files</span></span>  
 <span data-ttu-id="64f1b-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64f1b-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="64f1b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64f1b-128">Example</span></span>  
 <span data-ttu-id="64f1b-129">Im folgenden Beispiel wird eine benutzerdefinierte Proxy Klasse registriert.</span><span class="sxs-lookup"><span data-stu-id="64f1b-129">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="64f1b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64f1b-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="64f1b-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="64f1b-131">Network Settings Schema</span></span>](index.md)
