---
title: <clear>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 0b6a48d1fdab3cbccf40aaa77731a658f533eeba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705401"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="83299-102">\<clear >-Element für \<AppSettings ></span><span class="sxs-lookup"><span data-stu-id="83299-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="83299-103">Löscht die benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="83299-103">Clears custom application settings.</span></span>

<span data-ttu-id="83299-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="83299-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="83299-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="83299-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="83299-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="83299-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="83299-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="83299-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="83299-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="83299-108">Attributes</span></span>

<span data-ttu-id="83299-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="83299-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="83299-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="83299-110">Parent element</span></span>

|     | <span data-ttu-id="83299-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83299-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="83299-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="83299-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="83299-113">Enthält benutzerdefinierte anwendungseinstellung, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Anwendung-Konfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="83299-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="83299-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="83299-114">Child elements</span></span>

<span data-ttu-id="83299-115">Keiner</span><span class="sxs-lookup"><span data-stu-id="83299-115">None</span></span>

## <a name="example"></a><span data-ttu-id="83299-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="83299-116">Example</span></span>

<span data-ttu-id="83299-117">Das folgende Beispiel zeigt, wie Sie benutzerdefinierte Konfigurationseinstellungen deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="83299-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="83299-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83299-118">See also</span></span>

- [<span data-ttu-id="83299-119">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="83299-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
