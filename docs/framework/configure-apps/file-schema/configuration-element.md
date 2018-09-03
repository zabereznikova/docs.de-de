---
title: '&lt;Konfiguration&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c5146ed8326b12e90d0fe6247b0c4aba3a69dd77
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485780"
---
# <a name="configuration-element"></a><span data-ttu-id="969ad-102">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="969ad-102">\<configuration> element</span></span>

<span data-ttu-id="969ad-103">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="969ad-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="969ad-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="969ad-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="969ad-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="969ad-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="969ad-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="969ad-106">Attributes</span></span>

<span data-ttu-id="969ad-107">Keiner</span><span class="sxs-lookup"><span data-stu-id="969ad-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="969ad-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="969ad-108">Parent element</span></span>

<span data-ttu-id="969ad-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="969ad-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="969ad-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="969ad-110">Child elements</span></span>

|     | <span data-ttu-id="969ad-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="969ad-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="969ad-112">**\<AssemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="969ad-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="969ad-113">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="969ad-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="969ad-114">**\<Startup >** Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="969ad-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="969ad-115">Alle Elemente in das Schema für starteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="969ad-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="969ad-116">**\<Common Language Runtime >** Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="969ad-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="969ad-117">Alle Elemente in das Schema für Laufzeiteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="969ad-117">All elements in the runtime settings schema.</span></span> |
| [<span data-ttu-id="969ad-118">**\<System.Runtime.Remoting >** Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="969ad-118">**\<system.runtime.remoting>** Settings Schema</span></span>](https://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | <span data-ttu-id="969ad-119">Alle Elemente im Schema für Remoteeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="969ad-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="969ad-120">**\<system.Net >** Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="969ad-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="969ad-121">Alle Elemente in der netzwerkeinstellungsschema.</span><span class="sxs-lookup"><span data-stu-id="969ad-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="969ad-122">**\<CryptographySettings >** Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="969ad-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="969ad-123">Alle Elemente im Schema für Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="969ad-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="969ad-124">**\<Konfiguration >** Schema für Konfigurationsabschnitte</span><span class="sxs-lookup"><span data-stu-id="969ad-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="969ad-125">Alle Elemente in den Einstellungen des Konfigurationsschemas-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="969ad-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="969ad-126">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="969ad-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="969ad-127">Alle Elemente im Einstellungsschema für Ablaufverfolgung und Debuggen.</span><span class="sxs-lookup"><span data-stu-id="969ad-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="969ad-128">[Einstellungen für die ASP.NET-Konfigurationsschema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="969ad-128">[ASP.NET Configuration Settings Schema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span></span> | <span data-ttu-id="969ad-129">Alle Elemente in die ASP.NET-Konfigurationsschema, die Elemente für die Konfiguration von ASP.NET-Websites und-Anwendungen enthält.</span><span class="sxs-lookup"><span data-stu-id="969ad-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="969ad-130">Verwendet *"Web.config"* Dateien.</span><span class="sxs-lookup"><span data-stu-id="969ad-130">Used in *Web.config* files.</span></span> |
| [<span data-ttu-id="969ad-131">**\<WebServices >** Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="969ad-131">**\<webServices>** Settings Schema</span></span>](https://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | <span data-ttu-id="969ad-132">Alle Elemente in das Einstellungsschema für Webdienste.</span><span class="sxs-lookup"><span data-stu-id="969ad-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="969ad-133">Web Settings Schema (Schema für Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="969ad-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="969ad-134">Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält.</span><span class="sxs-lookup"><span data-stu-id="969ad-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="969ad-135">Verwendet *aspnet.config* Dateien.</span><span class="sxs-lookup"><span data-stu-id="969ad-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="969ad-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="969ad-136">Remarks</span></span>

<span data-ttu-id="969ad-137">Jede der Konfigurationsdateien muss genau einen enthalten  **\<Configuration >** Element.</span><span class="sxs-lookup"><span data-stu-id="969ad-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="969ad-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="969ad-138">See also</span></span>

[<span data-ttu-id="969ad-139">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="969ad-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
