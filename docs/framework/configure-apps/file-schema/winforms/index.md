---
title: Konfigurationsabschnitt für Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 4de61ae3cb5eb8a3fc226881e2b7f842030dfddf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151831"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="b12aa-102">Konfigurationsabschnitt für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b12aa-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="b12aa-103">Konfigurationseinstellungen für Windows Forms ermöglichen einer Windows Forms-App das Speichern und Abrufen von Informationen über benutzerdefinierte Anwendungseinstellungen wie z.B. Unterstützung mehrerer Monitore, Unterstützung für hohe DPI-Werte sowie weitere vorab definierte Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="b12aa-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="b12aa-104">Windows Forms-Anwendungskonfigurationseinstellungen werden im `System.Windows.Forms.ApplicationConfigurationSection`-Element der Anwendungskonfigurationsdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b12aa-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="b12aa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b12aa-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b12aa-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b12aa-106">Attributes and elements</span></span>

<span data-ttu-id="b12aa-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b12aa-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b12aa-108">Attributes</span><span class="sxs-lookup"><span data-stu-id="b12aa-108">Attributes</span></span>

<span data-ttu-id="b12aa-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="b12aa-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b12aa-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b12aa-110">Child elements</span></span>

<span data-ttu-id="b12aa-111">Element</span><span class="sxs-lookup"><span data-stu-id="b12aa-111">Element</span></span>  |<span data-ttu-id="b12aa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b12aa-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="b12aa-113">Fügt einen Konfigurationseinstellungsschlüssel mit einem angegebenen Wert hinzu.</span><span class="sxs-lookup"><span data-stu-id="b12aa-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="b12aa-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b12aa-114">Parent elements</span></span>

<span data-ttu-id="b12aa-115">Element</span><span class="sxs-lookup"><span data-stu-id="b12aa-115">Element</span></span>  |<span data-ttu-id="b12aa-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b12aa-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="b12aa-117">\<Konfiguration></span><span class="sxs-lookup"><span data-stu-id="b12aa-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="b12aa-118">Das Stammelement in jeder von der Common Language Runtime und Windows Forms-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b12aa-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="b12aa-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b12aa-119">Remarks</span></span>

<span data-ttu-id="b12aa-120">Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b12aa-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span>

<span data-ttu-id="b12aa-121">Das `<System.Windows.Forms.ApplicationConfigurationSection>` Element kann ein [`<add>`](windows-forms-add-configuration-element.md) oder mehrere untergeordnete Elemente enthalten, von denen jedes eine bestimmte Konfigurationseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="b12aa-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="b12aa-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b12aa-122">See also</span></span>

- [<span data-ttu-id="b12aa-123">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b12aa-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b12aa-124">High DPI Support in Windows Forms (Unterstützung für hohe DPI-Werte in Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b12aa-124">High DPI Support in Windows Forms</span></span>](../../../winforms/high-dpi-support-in-windows-forms.md)
