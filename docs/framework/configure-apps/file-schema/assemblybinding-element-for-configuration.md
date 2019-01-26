---
title: '&lt;AssemblyBinding&gt; -Element für &lt;Konfiguration&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 12065d8bc484f7bbf77ae18c67df1de0845167b2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083898"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="8f19e-102">\<AssemblyBinding >-Element für \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="8f19e-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="8f19e-103">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="8f19e-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="8f19e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="8f19e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="8f19e-105">&nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="8f19e-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8f19e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f19e-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="8f19e-107">Attribut</span><span class="sxs-lookup"><span data-stu-id="8f19e-107">Attribute</span></span>

|           | <span data-ttu-id="8f19e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f19e-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8f19e-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="8f19e-109">**xmlns**</span></span> | <span data-ttu-id="8f19e-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="8f19e-110">Required attribute.</span></span><br><br><span data-ttu-id="8f19e-111">Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8f19e-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="8f19e-112">Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert.</span><span class="sxs-lookup"><span data-stu-id="8f19e-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="8f19e-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="8f19e-113">Parent element</span></span>

|     | <span data-ttu-id="8f19e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f19e-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8f19e-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="8f19e-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="8f19e-116">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8f19e-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="8f19e-117">Untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="8f19e-117">Child element</span></span>

|     | <span data-ttu-id="8f19e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f19e-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8f19e-119">**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="8f19e-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="8f19e-120">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="8f19e-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8f19e-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f19e-121">Remarks</span></span>

<span data-ttu-id="8f19e-122">Die [  **\<LinkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Element vereinfacht die Verwaltung von Komponentenassemblys-Konfigurationsrichtlinien Anwendungskonfigurationsdateien Assembly einschließen Konfigurationsdateien in bekannten Speicherorten, anstatt duplizieren Assembly-Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="8f19e-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="8f19e-123">Die  **\<LinkedConfiguration >** Element wird für Anwendungen mit Windows-Seite-an-Seite-Manifeste nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8f19e-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="8f19e-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f19e-124">Example</span></span>

<span data-ttu-id="8f19e-125">Das folgende Beispiel zeigt, wie Sie eine Konfigurationsdatei auf der lokalen Festplatte einschließen:</span><span class="sxs-lookup"><span data-stu-id="8f19e-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="8f19e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f19e-126">See also</span></span>

- [<span data-ttu-id="8f19e-127">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8f19e-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
