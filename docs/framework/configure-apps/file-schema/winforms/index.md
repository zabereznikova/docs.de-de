---
title: Konfigurationsabschnitt für Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18d8e1e24af73c9521b3a5bb45f1c86fc52ff1e9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755551"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="a006d-102">Konfigurationsabschnitt für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a006d-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="a006d-103">Konfigurationseinstellungen für Windows Forms ermöglichen einer Windows Forms-App das Speichern und Abrufen von Informationen über benutzerdefinierte Anwendungseinstellungen wie z.B. Unterstützung mehrerer Monitore, Unterstützung für hohe DPI-Werte sowie weitere vorab definierte Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a006d-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="a006d-104">Windows Forms-Anwendungskonfigurationseinstellungen werden im `System.Windows.Forms.ApplicationConfigurationSection`-Element der Anwendungskonfigurationsdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a006d-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="a006d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a006d-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a006d-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a006d-106">Attributes and elements</span></span>

<span data-ttu-id="a006d-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a006d-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a006d-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="a006d-108">Attributes</span></span>

<span data-ttu-id="a006d-109">Keine</span><span class="sxs-lookup"><span data-stu-id="a006d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a006d-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a006d-110">Child elements</span></span>

<span data-ttu-id="a006d-111">Element</span><span class="sxs-lookup"><span data-stu-id="a006d-111">Element</span></span>  |<span data-ttu-id="a006d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a006d-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="a006d-113">Fügt einen Konfigurationseinstellungsschlüssel mit einem angegebenen Wert hinzu.</span><span class="sxs-lookup"><span data-stu-id="a006d-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="a006d-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a006d-114">Parent elements</span></span>

<span data-ttu-id="a006d-115">Element</span><span class="sxs-lookup"><span data-stu-id="a006d-115">Element</span></span>  |<span data-ttu-id="a006d-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a006d-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="a006d-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a006d-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="a006d-118">Das Stammelement in jeder von der Common Language Runtime und Windows Forms-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a006d-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="a006d-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a006d-119">Remarks</span></span>

<span data-ttu-id="a006d-120">Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a006d-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="a006d-121">Das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element kann ein oder mehrere [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)-Elemente enthalten, die jeweils eine bestimmte Konfigurationseinstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="a006d-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="a006d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a006d-122">See also</span></span>

<span data-ttu-id="a006d-123">[Konfigurationsdateischema](../index.md) </span><span class="sxs-lookup"><span data-stu-id="a006d-123">[Configuration File Schema](../index.md) </span></span>  
[<span data-ttu-id="a006d-124">High DPI Support in Windows Forms (Unterstützung für hohe DPI-Werte in Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a006d-124">High DPI Support in Windows Forms</span></span>](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
