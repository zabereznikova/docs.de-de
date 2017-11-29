---
title: '&lt;Modul&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a039f6ed985997c5557659abd299fe0fc7699a1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltmodulegt-element-network-settings"></a><span data-ttu-id="dd45f-102">&lt;Modul&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="dd45f-102">&lt;module&gt; Element (Network Settings)</span></span>
<span data-ttu-id="dd45f-103">Fügt der Anwendung ein neues Proxymodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd45f-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="dd45f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dd45f-104">\<configuration></span></span>  
<span data-ttu-id="dd45f-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="dd45f-105">\<system.net></span></span>  
<span data-ttu-id="dd45f-106">\<DefaultProxy ></span><span class="sxs-lookup"><span data-stu-id="dd45f-106">\<defaultProxy></span></span>  
<span data-ttu-id="dd45f-107">\<Modul ></span><span class="sxs-lookup"><span data-stu-id="dd45f-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd45f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd45f-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd45f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dd45f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dd45f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd45f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd45f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="dd45f-111">Attributes</span></span>  
  
|<span data-ttu-id="dd45f-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="dd45f-112">**Attribute**</span></span>|<span data-ttu-id="dd45f-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dd45f-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="dd45f-114">Den vollqualifizierten Typnamen (erkennbar die <xref:System.Type.FullName%2A> Eigenschaft) und der Name der Assembly (angegeben durch die <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, die den Proxy implementiert.</span><span class="sxs-lookup"><span data-stu-id="dd45f-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd45f-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dd45f-115">Child Elements</span></span>  
 <span data-ttu-id="dd45f-116">Keine</span><span class="sxs-lookup"><span data-stu-id="dd45f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd45f-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dd45f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="dd45f-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="dd45f-118">**Element**</span></span>|<span data-ttu-id="dd45f-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dd45f-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dd45f-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="dd45f-120">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="dd45f-121">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="dd45f-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd45f-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd45f-122">Remarks</span></span>  
 <span data-ttu-id="dd45f-123">Die `module` -Element registriert Proxyklassen, implementieren die <xref:System.Net.IWebProxy> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dd45f-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="dd45f-124">Nach dem Registrieren der Proxyklasse `module` kann zum Anfordern von Informationen über den unterstützten Proxy verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd45f-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="dd45f-125">Der Wert für die `type` Attribut muss der Klassenname des Moduls und den Namen der entsprechenden Dynamic Link Library (DLL).</span><span class="sxs-lookup"><span data-stu-id="dd45f-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="dd45f-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="dd45f-126">Configuration Files</span></span>  
 <span data-ttu-id="dd45f-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd45f-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd45f-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd45f-128">Example</span></span>  
 <span data-ttu-id="dd45f-129">Im folgende Beispiel wird eine benutzerdefinierte Proxyklasse registriert.</span><span class="sxs-lookup"><span data-stu-id="dd45f-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd45f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd45f-130">See Also</span></span>  
 <xref:System.Net.IWebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="dd45f-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="dd45f-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
