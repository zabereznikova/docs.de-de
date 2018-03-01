---
title: "&lt;Deaktivieren Sie&gt; -Element für &lt;\"appSettings\"&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54479cab9abc2c1a107cd055341404c0fe1308fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="db36a-102">\<Deaktivieren Sie >-Element für \<"appSettings" ></span><span class="sxs-lookup"><span data-stu-id="db36a-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="db36a-103">Löscht die Einstellungen für die benutzerdefinierte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="db36a-103">Clears custom application settings.</span></span>

<span data-ttu-id="db36a-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="db36a-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="db36a-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="db36a-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="db36a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Deaktivieren Sie >**</span><span class="sxs-lookup"><span data-stu-id="db36a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="db36a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="db36a-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="db36a-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="db36a-108">Attributes</span></span>

<span data-ttu-id="db36a-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="db36a-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="db36a-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="db36a-110">Parent element</span></span>

|     | <span data-ttu-id="db36a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db36a-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="db36a-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="db36a-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="db36a-113">Enthält Einstellungen für die benutzerdefinierte Anwendung wie Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Anwendung-Konfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="db36a-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="db36a-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db36a-114">Child elements</span></span>

<span data-ttu-id="db36a-115">Keiner</span><span class="sxs-lookup"><span data-stu-id="db36a-115">None</span></span>

## <a name="example"></a><span data-ttu-id="db36a-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db36a-116">Example</span></span>

<span data-ttu-id="db36a-117">Im folgende Beispiel wird das Löschen von benutzerdefinierten Konfigurationseinstellungen veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="db36a-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="db36a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db36a-118">See also</span></span>

[<span data-ttu-id="db36a-119">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="db36a-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
