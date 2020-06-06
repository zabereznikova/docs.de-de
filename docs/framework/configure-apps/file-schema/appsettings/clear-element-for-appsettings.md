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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214808"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="4dea6-102">\<clear>-Element für \<appSettings></span><span class="sxs-lookup"><span data-stu-id="4dea6-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="4dea6-103">Löscht benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4dea6-103">Clears custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="4dea6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4dea6-104">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="4dea6-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="4dea6-105">Attributes</span></span>

<span data-ttu-id="4dea6-106">Keine</span><span class="sxs-lookup"><span data-stu-id="4dea6-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="4dea6-107">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="4dea6-107">Parent element</span></span>

|     | <span data-ttu-id="4dea6-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4dea6-108">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="4dea6-109">Enthält benutzerdefinierte Anwendungseinstellungen, z. b. Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4dea6-109">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4dea6-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4dea6-110">Child elements</span></span>

<span data-ttu-id="4dea6-111">Keine</span><span class="sxs-lookup"><span data-stu-id="4dea6-111">None</span></span>

## <a name="example"></a><span data-ttu-id="4dea6-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4dea6-112">Example</span></span>

<span data-ttu-id="4dea6-113">Im folgenden Beispiel wird gezeigt, wie benutzerdefinierte Konfigurationseinstellungen gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="4dea6-113">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="4dea6-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4dea6-114">See also</span></span>

- [<span data-ttu-id="4dea6-115">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4dea6-115">Configuration file schema for the .NET Framework</span></span>](../index.md)
