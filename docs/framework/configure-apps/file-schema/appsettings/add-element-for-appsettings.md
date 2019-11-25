---
title: <add>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 865c693bf8f23bf050064ac097b72aa6fa3b371e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088749"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="ac1e0-102">\<> Element für \<appSettings hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="ac1e0-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="ac1e0-103">Fügt eine benutzerdefinierte Anwendungs Einstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac1e0-103">Adds a custom application setting.</span></span>

<span data-ttu-id="ac1e0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac1e0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ac1e0-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="ac1e0-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="ac1e0-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="ac1e0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ac1e0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac1e0-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="ac1e0-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="ac1e0-108">Attributes</span></span>

|           | <span data-ttu-id="ac1e0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac1e0-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ac1e0-110">**key**</span><span class="sxs-lookup"><span data-stu-id="ac1e0-110">**key**</span></span>   | <span data-ttu-id="ac1e0-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ac1e0-111">Required attribute.</span></span><br><br><span data-ttu-id="ac1e0-112">Gibt den Namen des hinzu zufügenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="ac1e0-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="ac1e0-113">**Wert**</span><span class="sxs-lookup"><span data-stu-id="ac1e0-113">**value**</span></span> | <span data-ttu-id="ac1e0-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ac1e0-114">Required attribute.</span></span><br><br><span data-ttu-id="ac1e0-115">Gibt den Wert des hinzu zufügenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="ac1e0-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ac1e0-116">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="ac1e0-116">Parent element</span></span>

|     | <span data-ttu-id="ac1e0-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac1e0-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ac1e0-118"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="ac1e0-118">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="ac1e0-119">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ac1e0-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ac1e0-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac1e0-120">Child elements</span></span>

<span data-ttu-id="ac1e0-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="ac1e0-121">None</span></span>

## <a name="example"></a><span data-ttu-id="ac1e0-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac1e0-122">Example</span></span>

<span data-ttu-id="ac1e0-123">Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte Konfigurationseinstellung für den Namen der Anwendung hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="ac1e0-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="ac1e0-124">Im folgenden Beispiel wird das `<add>`-Element verwendet, um zwei Kompatibilitäts Einstellungen in einer ASP.NET-Anwendung zu definieren:</span><span class="sxs-lookup"><span data-stu-id="ac1e0-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="ac1e0-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac1e0-125">See also</span></span>

- [<span data-ttu-id="ac1e0-126">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ac1e0-126">Configuration file schema for the .NET Framework</span></span>](../index.md)
