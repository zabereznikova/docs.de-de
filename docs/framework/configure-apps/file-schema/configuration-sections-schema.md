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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 120733873a7ea29303fe7f82c4c324d411532897
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921206"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="1ba4a-102">Schema für Konfigurations Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1ba4a-102">Configuration sections schema</span></span>

<span data-ttu-id="1ba4a-103">Das Schema für Konfigurations Abschnitte enthält Elemente, die benutzerdefinierte Einstellungen in Konfigurationsdateien definieren.</span><span class="sxs-lookup"><span data-stu-id="1ba4a-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="1ba4a-104">Allgemeine Informationen zu Konfigurationsdateien und-Schemas finden Sie unter [Schema der Konfigurationsdatei für die .NET Framework](index.md).</span><span class="sxs-lookup"><span data-stu-id="1ba4a-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="1ba4a-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="1ba4a-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="1ba4a-106">[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="1ba4a-106">[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="1ba4a-107">[ **\<Löschen >** ](clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="1ba4a-107">[**\<clear>**](clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="1ba4a-108">[ **\<entfernen >** ](remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="1ba4a-108">[**\<remove>**](remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="1ba4a-109">[ **\<Abschnitts >** ](section-element.md) </span><span class="sxs-lookup"><span data-stu-id="1ba4a-109">[**\<section>**](section-element.md) </span></span>  
[<span data-ttu-id="1ba4a-110"> **\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="1ba4a-110">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="1ba4a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ba4a-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1ba4a-112">Löschen Sie die > für  **\<**  **\<configabschnitts >** </span><span class="sxs-lookup"><span data-stu-id="1ba4a-112">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="1ba4a-113">Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen.</span><span class="sxs-lookup"><span data-stu-id="1ba4a-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="1ba4a-114"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="1ba4a-114">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="1ba4a-115">Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen.</span><span class="sxs-lookup"><span data-stu-id="1ba4a-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="1ba4a-116"> **\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="1ba4a-116">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="1ba4a-117">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="1ba4a-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="1ba4a-118">Entfernen Sie > für  **\<** configabschnitts  **\<>** </span><span class="sxs-lookup"><span data-stu-id="1ba4a-118">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="1ba4a-119">Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe.</span><span class="sxs-lookup"><span data-stu-id="1ba4a-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="1ba4a-120">Abschnitt > **für \<configabschnitts >** und  **\<sectionGroup >**  **\<** </span><span class="sxs-lookup"><span data-stu-id="1ba4a-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="1ba4a-121">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="1ba4a-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="1ba4a-122">SectionGroup-> für  **\<**  **\<configabschnitts >** </span><span class="sxs-lookup"><span data-stu-id="1ba4a-122">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="1ba4a-123">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="1ba4a-123">Defines a namespace for configuration sections.</span></span> |
