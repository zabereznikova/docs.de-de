---
title: <clear>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214808"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="4166d-102">\<> Element für \<appSettings löschen ></span><span class="sxs-lookup"><span data-stu-id="4166d-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="4166d-103">Löscht benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4166d-103">Clears custom application settings.</span></span>

<span data-ttu-id="4166d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4166d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4166d-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="4166d-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="4166d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<löschen >**</span><span class="sxs-lookup"><span data-stu-id="4166d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4166d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4166d-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="4166d-108">Attributes</span><span class="sxs-lookup"><span data-stu-id="4166d-108">Attributes</span></span>

<span data-ttu-id="4166d-109">Keine</span><span class="sxs-lookup"><span data-stu-id="4166d-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="4166d-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="4166d-110">Parent element</span></span>

|     | <span data-ttu-id="4166d-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4166d-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4166d-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="4166d-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="4166d-113">Enthält benutzerdefinierte Anwendungseinstellungen, z. b. Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4166d-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4166d-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4166d-114">Child elements</span></span>

<span data-ttu-id="4166d-115">Keine</span><span class="sxs-lookup"><span data-stu-id="4166d-115">None</span></span>

## <a name="example"></a><span data-ttu-id="4166d-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4166d-116">Example</span></span>

<span data-ttu-id="4166d-117">Im folgenden Beispiel wird gezeigt, wie benutzerdefinierte Konfigurationseinstellungen gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="4166d-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="4166d-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4166d-118">See also</span></span>

- [<span data-ttu-id="4166d-119">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4166d-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
