---
title: Schema für Konfigurations Abschnitte
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
ms.openlocfilehash: fc43a9c32ba33629b6e89120cf57f6d212ab3a56
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441660"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="fd180-102">Schema für Konfigurations Abschnitte</span><span class="sxs-lookup"><span data-stu-id="fd180-102">Configuration sections schema</span></span>

<span data-ttu-id="fd180-103">Das Schema für Konfigurations Abschnitte enthält Elemente, die benutzerdefinierte Einstellungen in Konfigurationsdateien definieren.</span><span class="sxs-lookup"><span data-stu-id="fd180-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="fd180-104">Allgemeine Informationen zu Konfigurationsdateien und-Schemas finden Sie unter [Schema der Konfigurationsdatei für die .NET Framework](index.md).</span><span class="sxs-lookup"><span data-stu-id="fd180-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="fd180-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd180-105">Description</span></span> |
| --- | ----------- |
| [**\<configSections>**](configsections-element-for-configuration.md) | <span data-ttu-id="fd180-106">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="fd180-106">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="fd180-107">**\<section>** für **\<configSections>** und**\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="fd180-107">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="fd180-108">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="fd180-108">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="fd180-109">**\<sectionGroup>** damit**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="fd180-109">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="fd180-110">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="fd180-110">Defines a namespace for configuration sections.</span></span> |

<a name="dep"></a>

## <a name="unimplemented-elements"></a><span data-ttu-id="fd180-111">Nicht implementierte Elemente</span><span class="sxs-lookup"><span data-stu-id="fd180-111">Unimplemented elements</span></span>

<span data-ttu-id="fd180-112">Die folgenden Elemente haben keine Auswirkung und sollten nicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="fd180-112">The following elements have no impact and should not be used:</span></span>

* **\<clear>**
* **\<remove>**
