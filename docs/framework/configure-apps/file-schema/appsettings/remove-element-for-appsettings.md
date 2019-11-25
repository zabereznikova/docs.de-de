---
title: <remove>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0fcdb75aa733a9d7634ec1c3b31dcbbb87e090e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088720"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="b71c2-102">\<> Element für \<appSettings entfernen ></span><span class="sxs-lookup"><span data-stu-id="b71c2-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="b71c2-103">Entfernt benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="b71c2-103">Removes custom application settings.</span></span>

<span data-ttu-id="b71c2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b71c2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b71c2-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b71c2-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="b71c2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**</span><span class="sxs-lookup"><span data-stu-id="b71c2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b71c2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b71c2-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="b71c2-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="b71c2-108">Attribute</span></span>

|         | <span data-ttu-id="b71c2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b71c2-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="b71c2-110">**key**</span><span class="sxs-lookup"><span data-stu-id="b71c2-110">**key**</span></span> | <span data-ttu-id="b71c2-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b71c2-111">Required attribute.</span></span><br><br><span data-ttu-id="b71c2-112">Gibt den Namen des zu entfernenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="b71c2-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="b71c2-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b71c2-113">Parent element</span></span>

|     | <span data-ttu-id="b71c2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b71c2-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b71c2-115"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="b71c2-115">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="b71c2-116">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b71c2-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b71c2-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b71c2-117">Child elements</span></span>

<span data-ttu-id="b71c2-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="b71c2-118">None</span></span>

## <a name="example"></a><span data-ttu-id="b71c2-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b71c2-119">Example</span></span>

<span data-ttu-id="b71c2-120">Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte Konfigurationseinstellung für `ApplicationName`entfernt wird:</span><span class="sxs-lookup"><span data-stu-id="b71c2-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="b71c2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b71c2-121">See also</span></span>

- [<span data-ttu-id="b71c2-122">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b71c2-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
