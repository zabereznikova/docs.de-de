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
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921251"
---
# <a name="configuration-element"></a><span data-ttu-id="cf798-102">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="cf798-102">\<configuration> element</span></span>

<span data-ttu-id="cf798-103">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cf798-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="cf798-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="cf798-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="cf798-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf798-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="cf798-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="cf798-106">Attributes</span></span>

<span data-ttu-id="cf798-107">None</span><span class="sxs-lookup"><span data-stu-id="cf798-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="cf798-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="cf798-108">Parent element</span></span>

<span data-ttu-id="cf798-109">None</span><span class="sxs-lookup"><span data-stu-id="cf798-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="cf798-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf798-110">Child elements</span></span>

|     | <span data-ttu-id="cf798-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf798-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="cf798-112"> **\<assemblyBinding>** </span><span class="sxs-lookup"><span data-stu-id="cf798-112">**\<assemblyBinding>**</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="cf798-113">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="cf798-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="cf798-114">Schema für Start > Einstellungen  **\<** </span><span class="sxs-lookup"><span data-stu-id="cf798-114">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="cf798-115">Alle Elemente im Start Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="cf798-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="cf798-116">Schema für Lauf Zeit > Einstellungen  **\<** </span><span class="sxs-lookup"><span data-stu-id="cf798-116">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="cf798-117">Alle Elemente im Lauf Zeit Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="cf798-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="cf798-118">[Schema für **System. Runtime. Remoting > Einstellungen \<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cf798-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="cf798-119">Alle Elemente im Remoting-Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="cf798-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="cf798-120">Schema für **System .net-> Einstellungen \<** </span><span class="sxs-lookup"><span data-stu-id="cf798-120">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="cf798-121">Alle Elemente im Netzwerk Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="cf798-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="cf798-122">cryptographySettings > Einstellungs Schema  **\<** </span><span class="sxs-lookup"><span data-stu-id="cf798-122">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="cf798-123">Alle Elemente im kryptografieeinstellungs-Schema.</span><span class="sxs-lookup"><span data-stu-id="cf798-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="cf798-124">Schema der Konfigurations > Abschnitte  **\<** </span><span class="sxs-lookup"><span data-stu-id="cf798-124">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="cf798-125">Alle Elemente im Konfigurations Abschnitts Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="cf798-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="cf798-126">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="cf798-126">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="cf798-127">Alle Elemente im Ablauf Verfolgungs-und debugeinstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="cf798-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="cf798-128">[Schema der ASP.NET-Konfigurationseinstellungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cf798-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="cf798-129">Alle Elemente im ASP.NET-Konfigurations Schema, die Elemente zum Konfigurieren von ASP.NET-Websites und-Anwendungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="cf798-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="cf798-130">Wird in *Web. config* -Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf798-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="cf798-131">[Schema für Webservices-> Einstellungen  **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cf798-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="cf798-132">Alle Elemente im Webdienst-Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="cf798-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="cf798-133">Web Settings Schema (Schema für Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="cf798-133">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="cf798-134">Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält.</span><span class="sxs-lookup"><span data-stu-id="cf798-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="cf798-135">Wird in *ASPNET. config* -Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf798-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cf798-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf798-136">Remarks</span></span>

<span data-ttu-id="cf798-137">Jede Konfigurationsdatei muss genau ein  **\<Konfigurations >** Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="cf798-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf798-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf798-138">See also</span></span>

- [<span data-ttu-id="cf798-139">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cf798-139">Configuration file schema for the .NET Framework</span></span>](index.md)
