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
ms.openlocfilehash: ad641f93e93f627dae1c7d0bda4620093c4567b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205047"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="4c640-102">\<module>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4c640-102">\<module> Element (Network Settings)</span></span>

<span data-ttu-id="4c640-103">Fügt der Anwendung ein neues Proxymodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="4c640-103">Adds a new proxy module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**

## <a name="syntax"></a><span data-ttu-id="4c640-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c640-104">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c640-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4c640-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4c640-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c640-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c640-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4c640-107">Attributes</span></span>  
  
|<span data-ttu-id="4c640-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="4c640-108">**Attribute**</span></span>|<span data-ttu-id="4c640-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4c640-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="4c640-110">Der voll qualifizierte Typname (angegeben durch die- <xref:System.Type.FullName%2A> Eigenschaft) und der AssemblyName (angegeben durch die- <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, das den Proxy implementiert.</span><span class="sxs-lookup"><span data-stu-id="4c640-110">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c640-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c640-111">Child Elements</span></span>  

 <span data-ttu-id="4c640-112">Keine</span><span class="sxs-lookup"><span data-stu-id="4c640-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c640-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c640-113">Parent Elements</span></span>  
  
|<span data-ttu-id="4c640-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="4c640-114">**Element**</span></span>|<span data-ttu-id="4c640-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4c640-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4c640-116">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="4c640-116">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="4c640-117">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="4c640-117">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c640-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4c640-118">Remarks</span></span>  

 <span data-ttu-id="4c640-119">Das- `module` Element registriert Proxy Klassen, die die- <xref:System.Net.IWebProxy> Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="4c640-119">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="4c640-120">Nach dem Registrieren der Proxy Klasse `module` kann verwendet werden, um Informationen über den unterstützten Proxy anzufordern.</span><span class="sxs-lookup"><span data-stu-id="4c640-120">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="4c640-121">Der Wert für das- `type` Attribut muss der Klassenname des Moduls und der Name der entsprechenden Dynamic Link Library (dll) sein.</span><span class="sxs-lookup"><span data-stu-id="4c640-121">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4c640-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="4c640-122">Configuration Files</span></span>  

 <span data-ttu-id="4c640-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c640-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c640-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c640-124">Example</span></span>  

 <span data-ttu-id="4c640-125">Im folgenden Beispiel wird eine benutzerdefinierte Proxy Klasse registriert.</span><span class="sxs-lookup"><span data-stu-id="4c640-125">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c640-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c640-126">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="4c640-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4c640-127">Network Settings Schema</span></span>](index.md)
