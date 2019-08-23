---
title: <assemblyBinding>-Element für <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: e0b83c4b3573ab6819654e72cac1bf3e4a0ba637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921274"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="b0aaa-102">\<assemblyBinding-> Element \<für die Konfigurations ></span><span class="sxs-lookup"><span data-stu-id="b0aaa-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="b0aaa-103">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="b0aaa-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b0aaa-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="b0aaa-105">&nbsp;&nbsp; **\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="b0aaa-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b0aaa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0aaa-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="b0aaa-107">Attribut</span><span class="sxs-lookup"><span data-stu-id="b0aaa-107">Attribute</span></span>

|           | <span data-ttu-id="b0aaa-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0aaa-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b0aaa-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="b0aaa-109">**xmlns**</span></span> | <span data-ttu-id="b0aaa-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-110">Required attribute.</span></span><br><br><span data-ttu-id="b0aaa-111">Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="b0aaa-112">Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b0aaa-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b0aaa-113">Parent element</span></span>

|     | <span data-ttu-id="b0aaa-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0aaa-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b0aaa-115"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b0aaa-115">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="b0aaa-116">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="b0aaa-117">Untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b0aaa-117">Child element</span></span>

|     | <span data-ttu-id="b0aaa-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0aaa-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b0aaa-119"> **\<linkedConfiguration>** </span><span class="sxs-lookup"><span data-stu-id="b0aaa-119">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="b0aaa-120">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b0aaa-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0aaa-121">Remarks</span></span>

<span data-ttu-id="b0aaa-122">[ **Das\<linkedconfiguration->** ](linkedconfiguration-element.md) Element vereinfacht die Verwaltung von Komponentenassemblys, indem es Anwendungs Konfigurationsdateien ermöglicht, Assemblykonfigurationsdateien an bekannten Speicherorten einzufügen, anstatt eine Assembly zu duplizieren. Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-122">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="b0aaa-123">**Das\<linkedconfiguration->** Element wird nicht für Anwendungen mit parallelen Windows-Manifesten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="b0aaa-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0aaa-124">Example</span></span>

<span data-ttu-id="b0aaa-125">Das folgende Beispiel zeigt, wie Sie eine Konfigurationsdatei auf der lokalen Festplatte einschließen:</span><span class="sxs-lookup"><span data-stu-id="b0aaa-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b0aaa-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0aaa-126">See also</span></span>

- [<span data-ttu-id="b0aaa-127">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b0aaa-127">Configuration file schema for the .NET Framework</span></span>](index.md)
