---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614553"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a><span data-ttu-id="a38ac-101">NullReferenceException im Ausnahmebehandlungscode von ImageSourceConverter.ConvertFrom</span><span class="sxs-lookup"><span data-stu-id="a38ac-101">NullReferenceException in exception handling code from ImageSourceConverter.ConvertFrom</span></span>

#### <a name="details"></a><span data-ttu-id="a38ac-102">Details</span><span class="sxs-lookup"><span data-stu-id="a38ac-102">Details</span></span>

<span data-ttu-id="a38ac-103">Ein Fehler im Ausnahmebehandlungscode für <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> löste einen inkorrekten <xref:System.NullReferenceException?displayProperty=fullName> anstelle der beabsichtigten Ausnahme (<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> oder <xref:System.IO.FileNotFoundException?displayProperty=fullName>) aus.</span><span class="sxs-lookup"><span data-stu-id="a38ac-103">An error in the exception handling code for <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> caused an incorrect <xref:System.NullReferenceException?displayProperty=fullName> to be thrown instead of the intended exception ( <xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> or <xref:System.IO.FileNotFoundException?displayProperty=fullName>).</span></span> <span data-ttu-id="a38ac-104">Diese Änderung korrigiert diesen Fehler, damit die Methode nun die richtige Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="a38ac-104">This change corrects that error so that the method now throws the right exception.</span></span> <p/><span data-ttu-id="a38ac-105">In der Standardeinstellung lösen Anwendungen mit dem Ziel .NET Framework 4.6.2 und früher der Kompatibilität wegen weiterhin <xref:System.NullReferenceException?displayProperty=fullName> aus.</span><span class="sxs-lookup"><span data-stu-id="a38ac-105">By default all applications targeting .NET Framework 4.6.2 and earlier continue to throw <xref:System.NullReferenceException?displayProperty=fullName> for compatibility.</span></span> <span data-ttu-id="a38ac-106">Entwickler, die .NET Framework 4.7 und höher anzielen, sollten die richtigen Ausnahmen angezeigt bekommen.</span><span class="sxs-lookup"><span data-stu-id="a38ac-106">Developers targeting .NET Framework 4.7 and above should see the right exceptions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a38ac-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a38ac-107">Suggestion</span></span>

<span data-ttu-id="a38ac-108">Entwickler, die wieder <xref:System.NullReferenceException?displayProperty=fullName> erhalten möchten, wenn Sie .NET Framework 4.7 oder höher als Zielplattform verwenden, können der Datei „app.config“ ihrer Anwendung Folgendes hinzufügen oder die entsprechenden Angaben zusammenführen:</span><span class="sxs-lookup"><span data-stu-id="a38ac-108">Developers who wish to revert to getting <xref:System.NullReferenceException?displayProperty=fullName> when targeting .NET Framework 4.7 or later can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="a38ac-109">name</span><span class="sxs-lookup"><span data-stu-id="a38ac-109">Name</span></span>    | <span data-ttu-id="a38ac-110">Wert</span><span class="sxs-lookup"><span data-stu-id="a38ac-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a38ac-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="a38ac-111">Scope</span></span>   | <span data-ttu-id="a38ac-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a38ac-112">Edge</span></span>        |
| <span data-ttu-id="a38ac-113">Version</span><span class="sxs-lookup"><span data-stu-id="a38ac-113">Version</span></span> | <span data-ttu-id="a38ac-114">4.7</span><span class="sxs-lookup"><span data-stu-id="a38ac-114">4.7</span></span>         |
| <span data-ttu-id="a38ac-115">Typ</span><span class="sxs-lookup"><span data-stu-id="a38ac-115">Type</span></span>    | <span data-ttu-id="a38ac-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="a38ac-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a38ac-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a38ac-117">Affected APIs</span></span>

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>
