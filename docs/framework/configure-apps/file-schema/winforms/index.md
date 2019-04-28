---
title: Konfigurationsabschnitt für Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbb2c4157ba702182056c98c959a60569e8c3d1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786411"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="f15c2-102">Konfigurationsabschnitt für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f15c2-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="f15c2-103">Konfigurationseinstellungen für Windows Forms ermöglichen einer Windows Forms-App das Speichern und Abrufen von Informationen über benutzerdefinierte Anwendungseinstellungen wie z.B. Unterstützung mehrerer Monitore, Unterstützung für hohe DPI-Werte sowie weitere vorab definierte Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f15c2-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="f15c2-104">Windows Forms-Anwendungskonfigurationseinstellungen werden im `System.Windows.Forms.ApplicationConfigurationSection`-Element der Anwendungskonfigurationsdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f15c2-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="f15c2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f15c2-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f15c2-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f15c2-106">Attributes and elements</span></span>

<span data-ttu-id="f15c2-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f15c2-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f15c2-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="f15c2-108">Attributes</span></span>

<span data-ttu-id="f15c2-109">Keine</span><span class="sxs-lookup"><span data-stu-id="f15c2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f15c2-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f15c2-110">Child elements</span></span>

<span data-ttu-id="f15c2-111">Element</span><span class="sxs-lookup"><span data-stu-id="f15c2-111">Element</span></span>  |<span data-ttu-id="f15c2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f15c2-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="f15c2-113">Fügt einen Konfigurationseinstellungsschlüssel mit einem angegebenen Wert hinzu.</span><span class="sxs-lookup"><span data-stu-id="f15c2-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="f15c2-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f15c2-114">Parent elements</span></span>

<span data-ttu-id="f15c2-115">Element</span><span class="sxs-lookup"><span data-stu-id="f15c2-115">Element</span></span>  |<span data-ttu-id="f15c2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f15c2-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="f15c2-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f15c2-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="f15c2-118">Das Stammelement in jeder von der Common Language Runtime und Windows Forms-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f15c2-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="f15c2-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f15c2-119">Remarks</span></span>

<span data-ttu-id="f15c2-120">Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f15c2-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="f15c2-121">Das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element kann ein oder mehrere [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)-Elemente enthalten, die jeweils eine bestimmte Konfigurationseinstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="f15c2-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="f15c2-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f15c2-122">See also</span></span>

- [<span data-ttu-id="f15c2-123">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f15c2-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f15c2-124">High DPI Support in Windows Forms (Unterstützung für hohe DPI-Werte in Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f15c2-124">High DPI Support in Windows Forms</span></span>](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
