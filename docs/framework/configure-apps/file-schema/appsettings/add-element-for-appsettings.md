---
title: '&lt;Hinzufügen&gt; -Element für &lt;"appSettings"&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 35a9fc08033d2b9cd1dae5a1f1f3ddcd361f03eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="3136b-102">\<Hinzufügen >-Element für \<"appSettings" ></span><span class="sxs-lookup"><span data-stu-id="3136b-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="3136b-103">Fügt eine benutzerdefinierte Anwendung-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="3136b-103">Adds a custom application setting.</span></span>

<span data-ttu-id="3136b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="3136b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="3136b-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="3136b-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="3136b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="3136b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3136b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3136b-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="3136b-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="3136b-108">Attributes</span></span>

|           | <span data-ttu-id="3136b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3136b-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="3136b-110">**key**</span><span class="sxs-lookup"><span data-stu-id="3136b-110">**key**</span></span>   | <span data-ttu-id="3136b-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="3136b-111">Required attribute.</span></span><br><br><span data-ttu-id="3136b-112">Gibt den Namen des hinzuzufügenden Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="3136b-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="3136b-113">**value**</span><span class="sxs-lookup"><span data-stu-id="3136b-113">**value**</span></span> | <span data-ttu-id="3136b-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="3136b-114">Required attribute.</span></span><br><br><span data-ttu-id="3136b-115">Gibt den Wert des hinzuzufügenden Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="3136b-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="3136b-116">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="3136b-116">Parent element</span></span>

|     | <span data-ttu-id="3136b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3136b-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3136b-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="3136b-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="3136b-119">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3136b-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3136b-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3136b-120">Child elements</span></span>

<span data-ttu-id="3136b-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="3136b-121">None</span></span>

## <a name="example"></a><span data-ttu-id="3136b-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3136b-122">Example</span></span>

<span data-ttu-id="3136b-123">Im folgende Beispiel wird gezeigt, wie eine benutzerdefinierte Einstellung für den Namen der Anwendung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="3136b-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="3136b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3136b-124">See also</span></span>

[<span data-ttu-id="3136b-125">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3136b-125">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
