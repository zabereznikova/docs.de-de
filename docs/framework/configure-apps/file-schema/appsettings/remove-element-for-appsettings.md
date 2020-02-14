---
title: <remove>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: 83abbdbf0d3e4dfd16c0e8c649200c4ecc7329f7
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215492"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="3e0cc-102">\<> Element für \<appSettings entfernen ></span><span class="sxs-lookup"><span data-stu-id="3e0cc-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="3e0cc-103">Entfernt benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3e0cc-103">Removes custom application settings.</span></span>

<span data-ttu-id="3e0cc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3e0cc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3e0cc-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="3e0cc-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="3e0cc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**</span><span class="sxs-lookup"><span data-stu-id="3e0cc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3e0cc-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e0cc-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="3e0cc-108">attribute</span><span class="sxs-lookup"><span data-stu-id="3e0cc-108">Attribute</span></span>

|         | <span data-ttu-id="3e0cc-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3e0cc-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="3e0cc-110">**key**</span><span class="sxs-lookup"><span data-stu-id="3e0cc-110">**key**</span></span> | <span data-ttu-id="3e0cc-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="3e0cc-111">Required attribute.</span></span><br><br><span data-ttu-id="3e0cc-112">Gibt den Namen des zu entfernenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="3e0cc-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="3e0cc-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="3e0cc-113">Parent element</span></span>

|     | <span data-ttu-id="3e0cc-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3e0cc-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3e0cc-115"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="3e0cc-115">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="3e0cc-116">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3e0cc-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3e0cc-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e0cc-117">Child elements</span></span>

<span data-ttu-id="3e0cc-118">Keine</span><span class="sxs-lookup"><span data-stu-id="3e0cc-118">None</span></span>

## <a name="example"></a><span data-ttu-id="3e0cc-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e0cc-119">Example</span></span>

<span data-ttu-id="3e0cc-120">Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte Konfigurationseinstellung für `ApplicationName`entfernt wird:</span><span class="sxs-lookup"><span data-stu-id="3e0cc-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="3e0cc-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e0cc-121">See also</span></span>

- [<span data-ttu-id="3e0cc-122">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3e0cc-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
