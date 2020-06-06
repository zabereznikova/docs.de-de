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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69921251"
---
# <a name="configuration-element"></a><span data-ttu-id="d1dd5-102">\<configuration>-Element</span><span class="sxs-lookup"><span data-stu-id="d1dd5-102">\<configuration> element</span></span>

<span data-ttu-id="d1dd5-103">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="d1dd5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1dd5-104">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="d1dd5-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="d1dd5-105">Attributes</span></span>

<span data-ttu-id="d1dd5-106">Keine</span><span class="sxs-lookup"><span data-stu-id="d1dd5-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="d1dd5-107">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="d1dd5-107">Parent element</span></span>

<span data-ttu-id="d1dd5-108">Keine</span><span class="sxs-lookup"><span data-stu-id="d1dd5-108">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="d1dd5-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d1dd5-109">Child elements</span></span>

|     | <span data-ttu-id="d1dd5-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d1dd5-110">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="d1dd5-111">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-111">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="d1dd5-112">**\<startup>** Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="d1dd5-112">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="d1dd5-113">Alle Elemente im Start Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-113">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="d1dd5-114">**\<runtime>** Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="d1dd5-114">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="d1dd5-115">Alle Elemente im Lauf Zeit Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-115">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="d1dd5-116">[**\<system.runtime.remoting>** Einstellungs Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d1dd5-116">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="d1dd5-117">Alle Elemente im Remoting-Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-117">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="d1dd5-118">**\<system.Net>** Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="d1dd5-118">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="d1dd5-119">Alle Elemente im Netzwerk Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-119">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="d1dd5-120">**\<cryptographySettings>** Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="d1dd5-120">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="d1dd5-121">Alle Elemente im kryptografieeinstellungs-Schema.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-121">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="d1dd5-122">**\<configuration>** Abschnitts Schema</span><span class="sxs-lookup"><span data-stu-id="d1dd5-122">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="d1dd5-123">Alle Elemente im Konfigurations Abschnitts Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-123">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="d1dd5-124">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="d1dd5-124">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="d1dd5-125">Alle Elemente im Ablauf Verfolgungs-und debugeinstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-125">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="d1dd5-126">[Schema der ASP.NET-Konfigurationseinstellungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d1dd5-126">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="d1dd5-127">Alle Elemente im ASP.NET-Konfigurations Schema, die Elemente zum Konfigurieren von ASP.NET-Websites und-Anwendungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-127">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="d1dd5-128">Wird in *Web. config* -Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-128">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="d1dd5-129">[**\<webServices>** Einstellungs Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d1dd5-129">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="d1dd5-130">Alle Elemente im Webdienst-Einstellungs Schema.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-130">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="d1dd5-131">Webeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="d1dd5-131">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="d1dd5-132">Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-132">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="d1dd5-133">Wird in *ASPNET. config* -Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-133">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d1dd5-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d1dd5-134">Remarks</span></span>

<span data-ttu-id="d1dd5-135">Jede Konfigurationsdatei muss genau ein **\<configuration>** Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1dd5-135">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1dd5-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1dd5-136">See also</span></span>

- [<span data-ttu-id="d1dd5-137">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1dd5-137">Configuration file schema for the .NET Framework</span></span>](index.md)
