---
ms.openlocfilehash: f75a652f15be6b0d184db20dc5cd8aafd80539fe
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614584"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a><span data-ttu-id="80a81-101">Die UpButton- und DownButton-Aktionen der Domäne von WinForm sind jetzt synchronisiert</span><span class="sxs-lookup"><span data-stu-id="80a81-101">WinForm's Domain upbutton and downbutton actions are in sync now</span></span>

#### <a name="details"></a><span data-ttu-id="80a81-102">Details</span><span class="sxs-lookup"><span data-stu-id="80a81-102">Details</span></span>

<span data-ttu-id="80a81-103">In .NET Framework 4.7.1 und früheren Versionen wird die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>-Aktion des <xref:System.Windows.Forms.DomainUpDown>-Steuerelements ignoriert, wenn Steuerelementtext vorhanden ist, und der Entwickler muss die <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>-Aktion für das Steuerelement vor der <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>-Aktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="80a81-103">In the .NET Framework 4.7.1 and previous versions the <xref:System.Windows.Forms.DomainUpDown> control's <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action is ignored when control text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before using <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="80a81-104">Ab .NET Framework 4.7.2 funktionieren die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>- und <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>-Aktionen unabhängig voneinander in diesem Szenario und bleiben synchron.</span><span class="sxs-lookup"><span data-stu-id="80a81-104">Starting with the .NET Framework 4.7.2 both the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> actions work independently in this scenario and remain in sync.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80a81-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="80a81-105">Suggestion</span></span>

<span data-ttu-id="80a81-106">Damit eine Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="80a81-106">In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="80a81-107">Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="80a81-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="80a81-108">Kompilieren Sie diese erneut, um .NET Framework 4.7.2 als Ziel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="80a81-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="80a81-109">Diese Änderung wird standardmäßig für Windows Forms-Anwendungen aktiviert, die für .NET Framework 4.7.2 oder höher ausgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="80a81-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="80a81-110">Veraltetes Scrollingverhalten wird deaktiviert, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) dem Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="80a81-110">It opts out of the legacy scrolling behavior by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="80a81-111">name</span><span class="sxs-lookup"><span data-stu-id="80a81-111">Name</span></span>    | <span data-ttu-id="80a81-112">Wert</span><span class="sxs-lookup"><span data-stu-id="80a81-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80a81-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="80a81-113">Scope</span></span>   | <span data-ttu-id="80a81-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="80a81-114">Edge</span></span>        |
| <span data-ttu-id="80a81-115">Version</span><span class="sxs-lookup"><span data-stu-id="80a81-115">Version</span></span> | <span data-ttu-id="80a81-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="80a81-116">4.7.2</span></span>       |
| <span data-ttu-id="80a81-117">Typ</span><span class="sxs-lookup"><span data-stu-id="80a81-117">Type</span></span>    | <span data-ttu-id="80a81-118">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="80a81-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="80a81-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="80a81-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
