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
ms.openlocfilehash: 5d4d96143dbd1db440de2247a7dc2f0c66f20403
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301299"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="d563a-102">\<clear >-Element für \<AppSettings ></span><span class="sxs-lookup"><span data-stu-id="d563a-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="d563a-103">Löscht die benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="d563a-103">Clears custom application settings.</span></span>

<span data-ttu-id="d563a-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d563a-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="d563a-105">&nbsp;&nbsp;[ **\<appSettings>** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d563a-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="d563a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="d563a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d563a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d563a-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="d563a-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="d563a-108">Attributes</span></span>

<span data-ttu-id="d563a-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="d563a-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="d563a-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="d563a-110">Parent element</span></span>

|     | <span data-ttu-id="d563a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d563a-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d563a-112"> *\*\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="d563a-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="d563a-113">Enthält benutzerdefinierte anwendungseinstellung, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Anwendung-Konfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="d563a-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d563a-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d563a-114">Child elements</span></span>

<span data-ttu-id="d563a-115">Keiner</span><span class="sxs-lookup"><span data-stu-id="d563a-115">None</span></span>

## <a name="example"></a><span data-ttu-id="d563a-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d563a-116">Example</span></span>

<span data-ttu-id="d563a-117">Das folgende Beispiel zeigt, wie Sie benutzerdefinierte Konfigurationseinstellungen deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="d563a-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="d563a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d563a-118">See also</span></span>

- [<span data-ttu-id="d563a-119">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d563a-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
