---
title: 'Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen'
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 7757e8d1fd0258ab2d972b7321082e4afa37f710
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398646"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="306b1-102">Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen</span><span class="sxs-lookup"><span data-stu-id="306b1-102">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>

<span data-ttu-id="306b1-103">In Windows Forms-Apps für .NET Framework-Versionen ab .NET Framework 4.6.1 kann eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung Meldungen beim Aufrufen der Methode <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> sicher filtern, wenn die <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung:</span><span class="sxs-lookup"><span data-stu-id="306b1-103">In Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1, a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>

- <span data-ttu-id="306b1-104">Mindestens eine der folgenden Aktionen ausführt:</span><span class="sxs-lookup"><span data-stu-id="306b1-104">Does one or both of the following:</span></span>

  - <span data-ttu-id="306b1-105">Hinzufügen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.AddMessageFilter%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="306b1-105">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>

  - <span data-ttu-id="306b1-106">Entfernen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="306b1-106">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="306b1-107">-Methode.</span><span class="sxs-lookup"><span data-stu-id="306b1-107">method.</span></span>

- <span data-ttu-id="306b1-108">**Und** Nachrichten durch Aufrufen der <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>-Methode abruft.</span><span class="sxs-lookup"><span data-stu-id="306b1-108">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>

## <a name="impact"></a><span data-ttu-id="306b1-109">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="306b1-109">Impact</span></span>

<span data-ttu-id="306b1-110">Diese Änderung betrifft nur Windows Forms-Apps, die auf Versionen von .NET Framework ab .NET Framework 4.6.1 ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="306b1-110">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>

<span data-ttu-id="306b1-111">Für Windows Forms-Apps, die auf vorherige Versionen von .NET Framework ausgerichtet sind, lösen solche Implementierungen in einigen Fällen beim Aufrufen der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>-Methode eine <xref:System.IndexOutOfRangeException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="306b1-111">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>

## <a name="mitigation"></a><span data-ttu-id="306b1-112">Minderung</span><span class="sxs-lookup"><span data-stu-id="306b1-112">Mitigation</span></span>

<span data-ttu-id="306b1-113">Ist diese Änderung nicht erwünscht, kann sie für Apps, die für .NET Framework 4.6.1 oder höhere Versionen vorgesehen sind, deaktiviert werden. Dazu muss dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="306b1-113">If this change is undesirable, apps that target the .NET Framework 4.6.1 or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

<span data-ttu-id="306b1-114">Für Apps, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter .NET Framework 4.6.1 oder einer höheren Version ausgeführt werden, kann dieses Verhalten aktiviert werden, indem dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="306b1-114">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="306b1-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="306b1-115">See also</span></span>

- [<span data-ttu-id="306b1-116">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="306b1-116">Application compatibility</span></span>](application-compatibility.md)
