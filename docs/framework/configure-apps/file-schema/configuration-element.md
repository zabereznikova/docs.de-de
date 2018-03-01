---
title: '&lt;Konfiguration&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 3874a613879d099ede4968b5bce349aefa015a38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-element"></a><span data-ttu-id="c2180-102">\<Konfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="c2180-102">\<configuration> element</span></span>

<span data-ttu-id="c2180-103">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c2180-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="c2180-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="c2180-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c2180-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2180-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="c2180-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="c2180-106">Attributes</span></span>

<span data-ttu-id="c2180-107">Keiner</span><span class="sxs-lookup"><span data-stu-id="c2180-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="c2180-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="c2180-108">Parent element</span></span>

<span data-ttu-id="c2180-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="c2180-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="c2180-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c2180-110">Child elements</span></span>

|     | <span data-ttu-id="c2180-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2180-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c2180-112">**\<AssemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="c2180-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="c2180-113">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="c2180-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="c2180-114">**\<Start >** -Einstellungsschema</span><span class="sxs-lookup"><span data-stu-id="c2180-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="c2180-115">Alle Elemente in der Start-Einstellungsschema.</span><span class="sxs-lookup"><span data-stu-id="c2180-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="c2180-116">**\<Common Language Runtime >** -Einstellungsschema</span><span class="sxs-lookup"><span data-stu-id="c2180-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="c2180-117">Alle Elemente in der Common Language Runtime-Einstellungsschema.</span><span class="sxs-lookup"><span data-stu-id="c2180-117">All elements in the runtime settings schema.</span></span> |
| [<span data-ttu-id="c2180-118">**\<System.Runtime.Remoting >** -Einstellungsschema</span><span class="sxs-lookup"><span data-stu-id="c2180-118">**\<system.runtime.remoting>** Settings Schema</span></span>](http://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | <span data-ttu-id="c2180-119">Alle Elemente im Schema für Remoteeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="c2180-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="c2180-120">**\<system.Net >** -Einstellungsschema</span><span class="sxs-lookup"><span data-stu-id="c2180-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="c2180-121">Alle Elemente in der Netzwerk-Einstellungsschema.</span><span class="sxs-lookup"><span data-stu-id="c2180-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="c2180-122">**\<CryptographySettings >** -Einstellungsschema</span><span class="sxs-lookup"><span data-stu-id="c2180-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="c2180-123">Alle Elemente im Schema für Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="c2180-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="c2180-124">**\<Konfiguration >** Schema für Konfigurationsabschnitte</span><span class="sxs-lookup"><span data-stu-id="c2180-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="c2180-125">Alle Elemente in der Konfiguration im Abschnitt-Einstellungsschema.</span><span class="sxs-lookup"><span data-stu-id="c2180-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="c2180-126">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c2180-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="c2180-127">Alle Elemente in der Ablaufverfolgung und Debug-Einstellungsschema.</span><span class="sxs-lookup"><span data-stu-id="c2180-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="c2180-128">[ASP.NET Configuration-Einstellungsschema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="c2180-128">[ASP.NET Configuration Settings Schema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span></span> | <span data-ttu-id="c2180-129">Alle Elemente in dem ASP.NET-Konfiguration-Schema, das Elemente für die Konfiguration von ASP.NET Web Sites und Anwendungen enthält.</span><span class="sxs-lookup"><span data-stu-id="c2180-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="c2180-130">Verwendet *"Web.config"* Dateien.</span><span class="sxs-lookup"><span data-stu-id="c2180-130">Used in *Web.config* files.</span></span> |
| [<span data-ttu-id="c2180-131">**\<WebServices >** -Einstellungsschema</span><span class="sxs-lookup"><span data-stu-id="c2180-131">**\<webServices>** Settings Schema</span></span>](http://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | <span data-ttu-id="c2180-132">Alle Elemente in der Web-Services-Einstellungsschema.</span><span class="sxs-lookup"><span data-stu-id="c2180-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="c2180-133">Web Settings Schema (Schema für Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c2180-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="c2180-134">Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält.</span><span class="sxs-lookup"><span data-stu-id="c2180-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="c2180-135">Verwendet *aspnet.config* Dateien.</span><span class="sxs-lookup"><span data-stu-id="c2180-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c2180-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2180-136">Remarks</span></span>

<span data-ttu-id="c2180-137">Jede Konfigurationsdatei muss genau einen enthalten  **\<Configuration >** Element.</span><span class="sxs-lookup"><span data-stu-id="c2180-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2180-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2180-138">See also</span></span>

[<span data-ttu-id="c2180-139">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c2180-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
