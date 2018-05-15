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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: edd2b2e11b02d69b7bba7c3cc7d8a9a0814e0c51
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="f1de6-102">Schema für Konfigurationsabschnitte</span><span class="sxs-lookup"><span data-stu-id="f1de6-102">Configuration sections schema</span></span>

<span data-ttu-id="f1de6-103">Das Schema für Konfigurationsabschnitte enthält Elemente, die benutzerdefinierte Einstellungen in Konfigurationsdateien zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f1de6-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="f1de6-104">Allgemeine Informationen zu Konfigurationsdateien und Schemas finden Sie unter [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="f1de6-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="f1de6-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f1de6-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="f1de6-106">[**\<ConfigSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f1de6-106">[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="f1de6-107">[**\<Deaktivieren Sie >**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="f1de6-107">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="f1de6-108">[**\<Entfernen >**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="f1de6-108">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="f1de6-109">[**\<Abschnitt >**](~/docs/framework/configure-apps/file-schema/section-element.md) </span><span class="sxs-lookup"><span data-stu-id="f1de6-109">[**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) </span></span>  
[<span data-ttu-id="f1de6-110">**\<SectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="f1de6-110">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="f1de6-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1de6-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f1de6-112">**\<Deaktivieren Sie >** für  **\<ConfigSections >**</span><span class="sxs-lookup"><span data-stu-id="f1de6-112">**\<clear>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="f1de6-113">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="f1de6-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="f1de6-114">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="f1de6-114">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="f1de6-115">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="f1de6-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="f1de6-116">**\<ConfigSections >**</span><span class="sxs-lookup"><span data-stu-id="f1de6-116">**\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="f1de6-117">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="f1de6-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="f1de6-118">**\<Entfernen Sie >** für  **\<ConfigSections >**</span><span class="sxs-lookup"><span data-stu-id="f1de6-118">**\<remove>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="f1de6-119">Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="f1de6-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="f1de6-120">**\<Abschnitt >** für  **\<ConfigSections >** und  **\<SectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="f1de6-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="f1de6-121">Enthält eine Deklaration der Konfiguration im Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f1de6-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="f1de6-122">**\<SectionGroup >** für  **\<ConfigSections >**</span><span class="sxs-lookup"><span data-stu-id="f1de6-122">**\<sectionGroup>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="f1de6-123">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="f1de6-123">Defines a namespace for configuration sections.</span></span> |
