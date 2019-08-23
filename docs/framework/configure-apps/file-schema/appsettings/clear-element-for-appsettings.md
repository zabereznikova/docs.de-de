---
title: <clear>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d5da531bff3a0e9e198ba9b5ab6cf2b52bf36b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921313"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="9bf93-102">\<> Element für \<appSettings löschen ></span><span class="sxs-lookup"><span data-stu-id="9bf93-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="9bf93-103">Löscht benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9bf93-103">Clears custom application settings.</span></span>

<span data-ttu-id="9bf93-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="9bf93-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="9bf93-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="9bf93-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="9bf93-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Löschen >**</span><span class="sxs-lookup"><span data-stu-id="9bf93-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9bf93-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9bf93-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="9bf93-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="9bf93-108">Attributes</span></span>

<span data-ttu-id="9bf93-109">None</span><span class="sxs-lookup"><span data-stu-id="9bf93-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="9bf93-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9bf93-110">Parent element</span></span>

|     | <span data-ttu-id="9bf93-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9bf93-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9bf93-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="9bf93-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="9bf93-113">Enthält benutzerdefinierte Anwendungseinstellungen, z. b. Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9bf93-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9bf93-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9bf93-114">Child elements</span></span>

<span data-ttu-id="9bf93-115">None</span><span class="sxs-lookup"><span data-stu-id="9bf93-115">None</span></span>

## <a name="example"></a><span data-ttu-id="9bf93-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bf93-116">Example</span></span>

<span data-ttu-id="9bf93-117">Im folgenden Beispiel wird gezeigt, wie benutzerdefinierte Konfigurationseinstellungen gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="9bf93-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="9bf93-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bf93-118">See also</span></span>

- [<span data-ttu-id="9bf93-119">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9bf93-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
