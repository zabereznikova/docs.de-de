---
title: Schema für Konfigurationsabschnitte
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: c7559a95099608ea462c838591ddb43e18d8f80c
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301232"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="b4b47-102">Schema für Konfigurationsabschnitte</span><span class="sxs-lookup"><span data-stu-id="b4b47-102">Configuration sections schema</span></span>

<span data-ttu-id="b4b47-103">Das Schema für Konfigurationsabschnitte enthält Elemente, die benutzerdefinierte Einstellungen in Konfigurationsdateien zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b4b47-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="b4b47-104">Allgemeine Informationen zu Konfigurationsdateien und Schemas finden Sie unter [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4b47-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="b4b47-105">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b4b47-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="b4b47-106">[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b4b47-106">[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="b4b47-107">[ **\<clear>** ](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="b4b47-107">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="b4b47-108">[ **\<remove>** ](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="b4b47-108">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="b4b47-109">[ **\<section>** ](~/docs/framework/configure-apps/file-schema/section-element.md) </span><span class="sxs-lookup"><span data-stu-id="b4b47-109">[**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) </span></span>  
[<span data-ttu-id="b4b47-110"> *\*\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="b4b47-110">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="b4b47-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4b47-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b4b47-112"> *\*\<Deaktivieren Sie >** für  *\*\<ConfigSections >** </span><span class="sxs-lookup"><span data-stu-id="b4b47-112">**\<clear>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="b4b47-113">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="b4b47-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="b4b47-114"> *\*\<clear>** </span><span class="sxs-lookup"><span data-stu-id="b4b47-114">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="b4b47-115">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="b4b47-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="b4b47-116"> *\*\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="b4b47-116">**\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="b4b47-117">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="b4b47-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="b4b47-118"> *\*\<Entfernen Sie >** für  *\*\<ConfigSections >** </span><span class="sxs-lookup"><span data-stu-id="b4b47-118">**\<remove>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="b4b47-119">Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="b4b47-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="b4b47-120"> *\*\<Abschnitt >** für  *\*\<ConfigSections >** und  *\*\<SectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="b4b47-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="b4b47-121">Enthält die Deklaration einer Konfigurations-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b4b47-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="b4b47-122"> *\*\<SectionGroup >** für  *\*\<ConfigSections >** </span><span class="sxs-lookup"><span data-stu-id="b4b47-122">**\<sectionGroup>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="b4b47-123">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="b4b47-123">Defines a namespace for configuration sections.</span></span> |
