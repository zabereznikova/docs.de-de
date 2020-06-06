---
title: <add>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: 5c7de79ec626966e71d461dd3865b294a8979db2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214813"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="21bd9-102">\<add>-Element für \<appSettings></span><span class="sxs-lookup"><span data-stu-id="21bd9-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="21bd9-103">Fügt eine benutzerdefinierte Anwendungs Einstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="21bd9-103">Adds a custom application setting.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="21bd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21bd9-104">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="21bd9-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="21bd9-105">Attributes</span></span>

|           | <span data-ttu-id="21bd9-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="21bd9-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="21bd9-107">**key**</span><span class="sxs-lookup"><span data-stu-id="21bd9-107">**key**</span></span>   | <span data-ttu-id="21bd9-108">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="21bd9-108">Required attribute.</span></span><br><br><span data-ttu-id="21bd9-109">Gibt den Namen des hinzu zufügenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="21bd9-109">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="21bd9-110">**value**</span><span class="sxs-lookup"><span data-stu-id="21bd9-110">**value**</span></span> | <span data-ttu-id="21bd9-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="21bd9-111">Required attribute.</span></span><br><br><span data-ttu-id="21bd9-112">Gibt den Wert des hinzu zufügenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="21bd9-112">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="21bd9-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="21bd9-113">Parent element</span></span>

|     | <span data-ttu-id="21bd9-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="21bd9-114">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="21bd9-115">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="21bd9-115">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="21bd9-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21bd9-116">Child elements</span></span>

<span data-ttu-id="21bd9-117">Keine</span><span class="sxs-lookup"><span data-stu-id="21bd9-117">None</span></span>

## <a name="example"></a><span data-ttu-id="21bd9-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21bd9-118">Example</span></span>

<span data-ttu-id="21bd9-119">Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte Konfigurationseinstellung für den Namen der Anwendung hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="21bd9-119">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="21bd9-120">Im folgenden Beispiel wird das- `<add>` Element verwendet, um zwei Kompatibilitäts Einstellungen in einer ASP.NET-Anwendung zu definieren:</span><span class="sxs-lookup"><span data-stu-id="21bd9-120">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="21bd9-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21bd9-121">See also</span></span>

- [<span data-ttu-id="21bd9-122">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="21bd9-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
