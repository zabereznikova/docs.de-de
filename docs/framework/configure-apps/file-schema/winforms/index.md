---
title: "Konfigurationsabschnitt für Windows Forms | Microsoft-Dokumentation"
ms.custom: 
ms.date: 04/07/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
ms.translationtype: Human Translation
ms.sourcegitcommit: 39e8e757a446b30ab18914465853138e1c239e40
ms.openlocfilehash: dedf9497a684c4b11f84b60de21ec73b563c6d19
ms.contentlocale: de-de
ms.lasthandoff: 05/03/2017

---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="7d303-102">Konfigurationsabschnitt für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7d303-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="7d303-103">Konfigurationseinstellungen für Windows Forms ermöglichen einer Windows Forms-App das Speichern und Abrufen von Informationen über benutzerdefinierte Anwendungseinstellungen wie z.B. Unterstützung mehrerer Monitore, Unterstützung für hohe DPI-Werte sowie weitere vorab definierte Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="7d303-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="7d303-104">Windows Forms-Anwendungskonfigurationseinstellungen werden im `System.Windows.Forms.ConfigurationSection`-Element der Anwendungskonfigurationsdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7d303-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d303-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d303-105">Syntax</span></span>

```xml
<configuration>
  \<System.Windows.Forms.ConfigurationSection>
  ...
  \</System.Windows.Forms.ConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7d303-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7d303-106">Attributes and elements</span></span>

<span data-ttu-id="7d303-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d303-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d303-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d303-108">Attributes</span></span>

<span data-ttu-id="7d303-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="7d303-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7d303-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d303-110">Child elements</span></span>

<span data-ttu-id="7d303-111">Element</span><span class="sxs-lookup"><span data-stu-id="7d303-111">Element</span></span>  |<span data-ttu-id="7d303-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d303-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="7d303-113">Fügt einen Konfigurationseinstellungsschlüssel mit einem angegebenen Wert hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d303-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="7d303-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d303-114">Parent elements</span></span>

<span data-ttu-id="7d303-115">Element</span><span class="sxs-lookup"><span data-stu-id="7d303-115">Element</span></span>  |<span data-ttu-id="7d303-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d303-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="7d303-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7d303-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="7d303-118">Das Stammelement in jeder von der Common Language Runtime und Windows Forms-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7d303-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="7d303-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d303-119">Remarks</span></span>

<span data-ttu-id="7d303-120">Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7d303-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="7d303-121">Das `<System.Windows.Forms.ConfigurationSection>`-Element kann ein oder mehrere [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)-Elemente enthalten, die jeweils eine bestimmte Konfigurationseinstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="7d303-121">The `<System.Windows.Forms.ConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d303-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d303-122">See also</span></span>

<span data-ttu-id="7d303-123">[Schema der Konfigurationsdatei](../index.md)
[Unterstützung für hohe DPI-Werte in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="7d303-123">[Configuration File Schema](../index.md)
[High DPI Support in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)</span></span>

