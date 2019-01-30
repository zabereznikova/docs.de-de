---
title: <assemblyBinding>-Element für <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: f5992a6085c32d37f56319cf8b2c361542c441e7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257329"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="03b73-102">\<AssemblyBinding >-Element für \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="03b73-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="03b73-103">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="03b73-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="03b73-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="03b73-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="03b73-105">&nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="03b73-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="03b73-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="03b73-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="03b73-107">Attribut</span><span class="sxs-lookup"><span data-stu-id="03b73-107">Attribute</span></span>

|           | <span data-ttu-id="03b73-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03b73-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="03b73-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="03b73-109">**xmlns**</span></span> | <span data-ttu-id="03b73-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="03b73-110">Required attribute.</span></span><br><br><span data-ttu-id="03b73-111">Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="03b73-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="03b73-112">Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert.</span><span class="sxs-lookup"><span data-stu-id="03b73-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="03b73-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="03b73-113">Parent element</span></span>

|     | <span data-ttu-id="03b73-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03b73-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="03b73-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="03b73-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="03b73-116">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="03b73-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="03b73-117">Untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="03b73-117">Child element</span></span>

|     | <span data-ttu-id="03b73-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03b73-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="03b73-119">**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="03b73-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="03b73-120">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="03b73-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="03b73-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03b73-121">Remarks</span></span>

<span data-ttu-id="03b73-122">Die [  **\<LinkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Element vereinfacht die Verwaltung von Komponentenassemblys-Konfigurationsrichtlinien Anwendungskonfigurationsdateien Assembly einschließen Konfigurationsdateien in bekannten Speicherorten, anstatt duplizieren Assembly-Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="03b73-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="03b73-123">Die  **\<LinkedConfiguration >** Element wird für Anwendungen mit Windows-Seite-an-Seite-Manifeste nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="03b73-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="03b73-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03b73-124">Example</span></span>

<span data-ttu-id="03b73-125">Das folgende Beispiel zeigt, wie Sie eine Konfigurationsdatei auf der lokalen Festplatte einschließen:</span><span class="sxs-lookup"><span data-stu-id="03b73-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="03b73-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03b73-126">See also</span></span>

- [<span data-ttu-id="03b73-127">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="03b73-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
