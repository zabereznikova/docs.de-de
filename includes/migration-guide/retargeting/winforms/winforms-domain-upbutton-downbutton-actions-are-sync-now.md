---
ms.openlocfilehash: c64431fd651fd7d53fb46231c6acc10c5cb43fff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606772"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a><span data-ttu-id="10d6c-101">Die UpButton- und DownButton-Aktionen der Domäne von WinForm sind jetzt synchronisiert</span><span class="sxs-lookup"><span data-stu-id="10d6c-101">WinForm's Domain upbutton and downbutton actions are in sync now</span></span>

#### <a name="details"></a><span data-ttu-id="10d6c-102">Details</span><span class="sxs-lookup"><span data-stu-id="10d6c-102">Details</span></span>

<span data-ttu-id="10d6c-103">In .NET Framework 4.7.1 und früheren Versionen wird die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>-Aktion des <xref:System.Windows.Forms.DomainUpDown>-Steuerelements ignoriert, wenn Steuerelementtext vorhanden ist, und der Entwickler muss die <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>-Aktion für das Steuerelement vor der <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>-Aktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="10d6c-103">In the .NET Framework 4.7.1 and previous versions the <xref:System.Windows.Forms.DomainUpDown> control's <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action is ignored when control text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before using <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="10d6c-104">Ab .NET Framework 4.7.2 funktionieren die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>- und <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>-Aktionen unabhängig voneinander in diesem Szenario und bleiben synchron.</span><span class="sxs-lookup"><span data-stu-id="10d6c-104">Starting with the .NET Framework 4.7.2 both the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> actions work independently in this scenario and remain in sync.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="10d6c-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="10d6c-105">Suggestion</span></span>

<span data-ttu-id="10d6c-106">Damit eine Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="10d6c-106">In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="10d6c-107">Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="10d6c-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="10d6c-108">Kompilieren Sie diese erneut, um .NET Framework 4.7.2 als Ziel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="10d6c-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="10d6c-109">Diese Änderung wird standardmäßig für Windows Forms-Anwendungen aktiviert, die für .NET Framework 4.7.2 oder höher ausgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="10d6c-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="10d6c-110">Veraltetes Scrollingverhalten wird deaktiviert, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="10d6c-110">It opts out of the legacy scrolling behavior by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="10d6c-111">name</span><span class="sxs-lookup"><span data-stu-id="10d6c-111">Name</span></span>    | <span data-ttu-id="10d6c-112">Wert</span><span class="sxs-lookup"><span data-stu-id="10d6c-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="10d6c-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="10d6c-113">Scope</span></span>   | <span data-ttu-id="10d6c-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="10d6c-114">Edge</span></span>        |
| <span data-ttu-id="10d6c-115">Version</span><span class="sxs-lookup"><span data-stu-id="10d6c-115">Version</span></span> | <span data-ttu-id="10d6c-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="10d6c-116">4.7.2</span></span>       |
| <span data-ttu-id="10d6c-117">Typ</span><span class="sxs-lookup"><span data-stu-id="10d6c-117">Type</span></span>    | <span data-ttu-id="10d6c-118">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="10d6c-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="10d6c-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="10d6c-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
