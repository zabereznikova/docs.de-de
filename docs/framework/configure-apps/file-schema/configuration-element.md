---
title: <configuration>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 9a7b25c74763c020c0e19c3f6099db9001acf773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705414"
---
# <a name="configuration-element"></a><span data-ttu-id="60088-102">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="60088-102">\<configuration> element</span></span>

<span data-ttu-id="60088-103">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="60088-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="60088-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="60088-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="60088-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="60088-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="60088-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="60088-106">Attributes</span></span>

<span data-ttu-id="60088-107">Keiner</span><span class="sxs-lookup"><span data-stu-id="60088-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="60088-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="60088-108">Parent element</span></span>

<span data-ttu-id="60088-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="60088-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="60088-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60088-110">Child elements</span></span>

|     | <span data-ttu-id="60088-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60088-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="60088-112"> *\*\<assemblyBinding>** </span><span class="sxs-lookup"><span data-stu-id="60088-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="60088-113">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="60088-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="60088-114"> *\*\<Startup >** Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="60088-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="60088-115">Alle Elemente in das Schema für starteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="60088-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="60088-116"> *\*\<Common Language Runtime >** Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="60088-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="60088-117">Alle Elemente in das Schema für Laufzeiteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="60088-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="60088-118">[ **\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="60088-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="60088-119">Alle Elemente im Schema für Remoteeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="60088-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="60088-120"> *\*\<system.Net >** Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="60088-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="60088-121">Alle Elemente in der netzwerkeinstellungsschema.</span><span class="sxs-lookup"><span data-stu-id="60088-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="60088-122"> *\*\<cryptographySettings>** Settings Schema</span><span class="sxs-lookup"><span data-stu-id="60088-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="60088-123">Alle Elemente im Schema für Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="60088-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="60088-124"> *\*\<Konfiguration >** Schema für Konfigurationsabschnitte</span><span class="sxs-lookup"><span data-stu-id="60088-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="60088-125">Alle Elemente in den Einstellungen des Konfigurationsschemas-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="60088-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="60088-126">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="60088-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="60088-127">Alle Elemente im Einstellungsschema für Ablaufverfolgung und Debuggen.</span><span class="sxs-lookup"><span data-stu-id="60088-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="60088-128">[Einstellungen für die ASP.NET-Konfigurationsschema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="60088-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="60088-129">Alle Elemente in die ASP.NET-Konfigurationsschema, die Elemente für die Konfiguration von ASP.NET-Websites und-Anwendungen enthält.</span><span class="sxs-lookup"><span data-stu-id="60088-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="60088-130">Verwendet *"Web.config"* Dateien.</span><span class="sxs-lookup"><span data-stu-id="60088-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="60088-131">[ **\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="60088-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="60088-132">Alle Elemente in das Einstellungsschema für Webdienste.</span><span class="sxs-lookup"><span data-stu-id="60088-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="60088-133">Web Settings Schema (Schema für Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="60088-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="60088-134">Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält.</span><span class="sxs-lookup"><span data-stu-id="60088-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="60088-135">Verwendet *aspnet.config* Dateien.</span><span class="sxs-lookup"><span data-stu-id="60088-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="60088-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60088-136">Remarks</span></span>

<span data-ttu-id="60088-137">Jede der Konfigurationsdateien muss genau einen enthalten  **\<Configuration >** Element.</span><span class="sxs-lookup"><span data-stu-id="60088-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="60088-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60088-138">See also</span></span>

- [<span data-ttu-id="60088-139">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="60088-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
