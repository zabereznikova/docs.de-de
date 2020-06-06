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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215492"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="cb263-102">\<remove>-Element für \<appSettings></span><span class="sxs-lookup"><span data-stu-id="cb263-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="cb263-103">Entfernt benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="cb263-103">Removes custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="cb263-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb263-104">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="cb263-105">attribute</span><span class="sxs-lookup"><span data-stu-id="cb263-105">Attribute</span></span>

|         | <span data-ttu-id="cb263-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cb263-106">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="cb263-107">**key**</span><span class="sxs-lookup"><span data-stu-id="cb263-107">**key**</span></span> | <span data-ttu-id="cb263-108">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="cb263-108">Required attribute.</span></span><br><br><span data-ttu-id="cb263-109">Gibt den Namen des zu entfernenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="cb263-109">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="cb263-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="cb263-110">Parent element</span></span>

|     | <span data-ttu-id="cb263-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cb263-111">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="cb263-112">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="cb263-112">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="cb263-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cb263-113">Child elements</span></span>

<span data-ttu-id="cb263-114">Keine</span><span class="sxs-lookup"><span data-stu-id="cb263-114">None</span></span>

## <a name="example"></a><span data-ttu-id="cb263-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb263-115">Example</span></span>

<span data-ttu-id="cb263-116">Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte Konfigurationseinstellung für entfernt wird `ApplicationName` :</span><span class="sxs-lookup"><span data-stu-id="cb263-116">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="cb263-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb263-117">See also</span></span>

- [<span data-ttu-id="cb263-118">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cb263-118">Configuration file schema for the .NET Framework</span></span>](../index.md)
