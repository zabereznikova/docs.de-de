---
title: <assemblyBinding>-Element für <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155478"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="f2cd2-102">\<assemblyBinding>-Element für \<configuration></span><span class="sxs-lookup"><span data-stu-id="f2cd2-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="f2cd2-103">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="f2cd2-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="f2cd2-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="f2cd2-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f2cd2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2cd2-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="f2cd2-106">attribute</span><span class="sxs-lookup"><span data-stu-id="f2cd2-106">Attribute</span></span>

|           | <span data-ttu-id="f2cd2-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f2cd2-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f2cd2-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="f2cd2-108">**xmlns**</span></span> | <span data-ttu-id="f2cd2-109">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f2cd2-109">Required attribute.</span></span><br><br><span data-ttu-id="f2cd2-110">Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f2cd2-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="f2cd2-111">Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert.</span><span class="sxs-lookup"><span data-stu-id="f2cd2-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f2cd2-112">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="f2cd2-112">Parent element</span></span>

|     | <span data-ttu-id="f2cd2-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f2cd2-113">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="f2cd2-114">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f2cd2-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="f2cd2-115">Untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="f2cd2-115">Child element</span></span>

|     | <span data-ttu-id="f2cd2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2cd2-116">Description</span></span> |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | <span data-ttu-id="f2cd2-117">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="f2cd2-117">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f2cd2-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f2cd2-118">Remarks</span></span>

<span data-ttu-id="f2cd2-119">Das- [**\<linkedConfiguration>**](linkedconfiguration-element.md) Element vereinfacht die Verwaltung von Komponentenassemblys, indem es Anwendungs Konfigurationsdateien ermöglicht, Assemblykonfigurationsdateien an bekannten Speicherorten einzufügen, anstatt Assemblykonfigurationseinstellungen zu duplizieren</span><span class="sxs-lookup"><span data-stu-id="f2cd2-119">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="f2cd2-120">Das- **\<linkedConfiguration>** Element wird nicht für Anwendungen mit parallelen Windows-Manifesten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2cd2-120">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="f2cd2-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f2cd2-121">Example</span></span>

<span data-ttu-id="f2cd2-122">Das folgende Beispiel zeigt, wie Sie eine Konfigurationsdatei auf der lokalen Festplatte einschließen:</span><span class="sxs-lookup"><span data-stu-id="f2cd2-122">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f2cd2-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2cd2-123">See also</span></span>

- [<span data-ttu-id="f2cd2-124">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f2cd2-124">Configuration file schema for the .NET Framework</span></span>](index.md)
