---
title: "&lt;Entfernen Sie&gt; -Element für &lt;\"appSettings\"&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 10202a38d54e4c9744dbd20fb5f226fa41f5dab5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="a4c54-102">\<Entfernen Sie >-Element für \<"appSettings" ></span><span class="sxs-lookup"><span data-stu-id="a4c54-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="a4c54-103">Entfernt die benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a4c54-103">Removes custom application settings.</span></span>

<span data-ttu-id="a4c54-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="a4c54-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="a4c54-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="a4c54-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="a4c54-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Entfernen >**</span><span class="sxs-lookup"><span data-stu-id="a4c54-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a4c54-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4c54-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="a4c54-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="a4c54-108">Attribute</span></span>

|         | <span data-ttu-id="a4c54-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4c54-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="a4c54-110">**key**</span><span class="sxs-lookup"><span data-stu-id="a4c54-110">**key**</span></span> | <span data-ttu-id="a4c54-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a4c54-111">Required attribute.</span></span><br><br><span data-ttu-id="a4c54-112">Gibt den Namen des Schlüssels zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a4c54-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="a4c54-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="a4c54-113">Parent element</span></span>

|     | <span data-ttu-id="a4c54-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4c54-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a4c54-115">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="a4c54-115">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="a4c54-116">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a4c54-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a4c54-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4c54-117">Child elements</span></span>

<span data-ttu-id="a4c54-118">Keine</span><span class="sxs-lookup"><span data-stu-id="a4c54-118">None</span></span>

## <a name="example"></a><span data-ttu-id="a4c54-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a4c54-119">Example</span></span>

<span data-ttu-id="a4c54-120">Das folgende Beispiel zeigt die Vorgehensweise beim Entfernen einer benutzerdefinierten Konfigurationseinstellung für `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="a4c54-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="a4c54-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4c54-121">See also</span></span>

[<span data-ttu-id="a4c54-122">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a4c54-122">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
