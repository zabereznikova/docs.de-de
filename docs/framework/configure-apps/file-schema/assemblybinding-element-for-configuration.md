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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155478"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="b4bd5-102">\<assemblyBinding>-Element für \<Konfiguration></span><span class="sxs-lookup"><span data-stu-id="b4bd5-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="b4bd5-103">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="b4bd5-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="b4bd5-104">Konfiguration &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) \*\* \<AssemblyBinding>\*\*</span><span class="sxs-lookup"><span data-stu-id="b4bd5-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b4bd5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4bd5-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="b4bd5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b4bd5-106">Attribute</span></span>

|           | <span data-ttu-id="b4bd5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4bd5-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b4bd5-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="b4bd5-108">**xmlns**</span></span> | <span data-ttu-id="b4bd5-109">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b4bd5-109">Required attribute.</span></span><br><br><span data-ttu-id="b4bd5-110">Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b4bd5-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="b4bd5-111">Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert.</span><span class="sxs-lookup"><span data-stu-id="b4bd5-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b4bd5-112">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b4bd5-112">Parent element</span></span>

|     | <span data-ttu-id="b4bd5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4bd5-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b4bd5-114">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="b4bd5-114">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="b4bd5-115">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b4bd5-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="b4bd5-116">Untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b4bd5-116">Child element</span></span>

|     | <span data-ttu-id="b4bd5-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4bd5-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b4bd5-118">**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="b4bd5-118">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="b4bd5-119">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="b4bd5-119">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b4bd5-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4bd5-120">Remarks</span></span>

<span data-ttu-id="b4bd5-121">Das [\*\* \<linkedConfiguration>-Element\*\*](linkedconfiguration-element.md) vereinfacht die Verwaltung von Komponentenassemblys, indem Anwendungskonfigurationsdateien Assemblykonfigurationsdateien an bekannten Speicherorten einschließen können, anstatt die Konfigurationseinstellungen der Assembly zu duplizieren.</span><span class="sxs-lookup"><span data-stu-id="b4bd5-121">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd5-122">Das \*\* \<linkedConfiguration>-Element\*\* wird für Anwendungen mit Windows-Manifesten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4bd5-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="b4bd5-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4bd5-123">Example</span></span>

<span data-ttu-id="b4bd5-124">Das folgende Beispiel zeigt, wie eine Konfigurationsdatei auf der lokalen Festplatte eingeschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="b4bd5-124">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b4bd5-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4bd5-125">See also</span></span>

- [<span data-ttu-id="b4bd5-126">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b4bd5-126">Configuration file schema for the .NET Framework</span></span>](index.md)
