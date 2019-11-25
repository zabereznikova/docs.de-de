---
title: <clear>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d321f3169344e9aa40d65b1722a533549de5315a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088735"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="e70da-102">\<> Element für \<appSettings löschen ></span><span class="sxs-lookup"><span data-stu-id="e70da-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="e70da-103">Löscht benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e70da-103">Clears custom application settings.</span></span>

<span data-ttu-id="e70da-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e70da-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e70da-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="e70da-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="e70da-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<löschen >**</span><span class="sxs-lookup"><span data-stu-id="e70da-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e70da-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e70da-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="e70da-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="e70da-108">Attributes</span></span>

<span data-ttu-id="e70da-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="e70da-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="e70da-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="e70da-110">Parent element</span></span>

|     | <span data-ttu-id="e70da-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e70da-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e70da-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="e70da-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="e70da-113">Enthält benutzerdefinierte Anwendungseinstellungen, z. b. Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e70da-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e70da-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e70da-114">Child elements</span></span>

<span data-ttu-id="e70da-115">Keiner</span><span class="sxs-lookup"><span data-stu-id="e70da-115">None</span></span>

## <a name="example"></a><span data-ttu-id="e70da-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e70da-116">Example</span></span>

<span data-ttu-id="e70da-117">Im folgenden Beispiel wird gezeigt, wie benutzerdefinierte Konfigurationseinstellungen gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="e70da-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="e70da-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e70da-118">See also</span></span>

- [<span data-ttu-id="e70da-119">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e70da-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
