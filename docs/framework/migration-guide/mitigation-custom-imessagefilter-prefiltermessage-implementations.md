---
title: 'Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen'
description: In diesem Artikel erfahren Sie mehr über die benutzerdefinierte Implementierung der Methode „IMessageFilter.PreFilterMessage“ in Windows Forms-Apps, die auf .NET Framework 4.6.1 oder höher ausgerichtet sind.
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 5fe7500d3ed6ff293514495df150a747e7946dda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475254"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="bc678-103">Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen</span><span class="sxs-lookup"><span data-stu-id="bc678-103">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>

<span data-ttu-id="bc678-104">In Windows Forms-Apps für .NET Framework-Versionen ab .NET Framework 4.6.1 kann eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung Meldungen beim Aufrufen der Methode <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> sicher filtern, wenn die <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung:</span><span class="sxs-lookup"><span data-stu-id="bc678-104">In Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1, a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>

- <span data-ttu-id="bc678-105">Mindestens eine der folgenden Aktionen ausführt:</span><span class="sxs-lookup"><span data-stu-id="bc678-105">Does one or both of the following:</span></span>

  - <span data-ttu-id="bc678-106">Hinzufügen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.AddMessageFilter%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc678-106">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>

  - <span data-ttu-id="bc678-107">Entfernen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc678-107">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="bc678-108">-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc678-108">method.</span></span>

- <span data-ttu-id="bc678-109">**Und** Nachrichten durch Aufrufen der <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>-Methode abruft.</span><span class="sxs-lookup"><span data-stu-id="bc678-109">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>

## <a name="impact"></a><span data-ttu-id="bc678-110">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="bc678-110">Impact</span></span>

<span data-ttu-id="bc678-111">Diese Änderung betrifft nur Windows Forms-Apps, die auf Versionen von .NET Framework ab .NET Framework 4.6.1 ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="bc678-111">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>

<span data-ttu-id="bc678-112">Für Windows Forms-Apps, die auf vorherige Versionen von .NET Framework ausgerichtet sind, lösen solche Implementierungen in einigen Fällen beim Aufrufen der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>-Methode eine <xref:System.IndexOutOfRangeException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="bc678-112">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>

## <a name="mitigation"></a><span data-ttu-id="bc678-113">Minderung</span><span class="sxs-lookup"><span data-stu-id="bc678-113">Mitigation</span></span>

<span data-ttu-id="bc678-114">Ist diese Änderung nicht erwünscht, kann sie in Apps, die für .NET Framework 4.6.1 oder höher konzipiert sind, deaktiviert werden. Dazu muss dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="bc678-114">If this change is undesirable, apps that target the .NET Framework 4.6.1 or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

<span data-ttu-id="bc678-115">Für Apps, die für frühere Versionen des .NET Framework vorgesehen sind, aber unter .NET Framework 4.6.1 oder einer höheren Version ausgeführt werden, kann dieses Verhalten aktiviert werden, indem dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="bc678-115">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="bc678-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc678-116">See also</span></span>

- [<span data-ttu-id="bc678-117">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="bc678-117">Application compatibility</span></span>](application-compatibility.md)
