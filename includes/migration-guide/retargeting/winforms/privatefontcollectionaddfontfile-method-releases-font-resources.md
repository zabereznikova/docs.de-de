---
ms.openlocfilehash: 53ded5ae6e5a025fc7992da099c3481587bb6f31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614577"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a><span data-ttu-id="1539d-101">PrivateFontCollection.AddFontFile-Methode gibt Schriftartenressourcen frei</span><span class="sxs-lookup"><span data-stu-id="1539d-101">PrivateFontCollection.AddFontFile method releases Font resources</span></span>

#### <a name="details"></a><span data-ttu-id="1539d-102">Details</span><span class="sxs-lookup"><span data-stu-id="1539d-102">Details</span></span>

<span data-ttu-id="1539d-103">In .NET Framework 4.7.1 und früheren Versionen gibt die <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType>-Klasse keine GDI+-Schriftartenressourcen frei, nachdem <xref:System.Drawing.Text.PrivateFontCollection> für <xref:System.Drawing.Font>-Objekte verworfen wird, die dieser Sammlung mit der <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)>-Methode hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1539d-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> class does not release the GDI+ font resources after the <xref:System.Drawing.Text.PrivateFontCollection> is disposed for <xref:System.Drawing.Font> objects that are added to this collection using the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> method.</span></span> <span data-ttu-id="1539d-104">In .NET Framework 4.7.2 oder höher gibt <xref:System.Drawing.Text.FontCollection.Dispose%2A> die GDI+-Schriftarten frei, die der Sammlung als Dateien hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="1539d-104">In the .NET Framework 4.7.2 and later <xref:System.Drawing.Text.FontCollection.Dispose%2A> releases the GDI+ fonts that were added to the collection as files.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1539d-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1539d-105">Suggestion</span></span>

<span data-ttu-id="1539d-106">**Aktivieren oder Deaktivieren dieser Änderungen:** Damit eine Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1539d-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="1539d-107">Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="1539d-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="1539d-108">Kompilieren Sie diese erneut, um .NET Framework 4.7.2 als Ziel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1539d-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="1539d-109">Diese Änderung wird standardmäßig für Windows Forms-Anwendungen aktiviert, die für .NET Framework 4.7.2 oder höher ausgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="1539d-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="1539d-110">Die Anwendung ist für .NET Framework 4.7.1 oder eine frühere Version ausgelegt und deaktiviert veraltete Verhaltensweisen der Barrierefreiheit, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1539d-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="1539d-111">Bei Anwendungen, die für .NET Framework 4.7.2 oder höher ausgelegt sind und das Legacyverhalten beibehalten sollen, können Sie die Nichtfreigabe von Schriftartenressourcen aktivieren, indem dieser AppContext-Schalter ausdrücklich auf `true` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1539d-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to not release font resources by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="1539d-112">name</span><span class="sxs-lookup"><span data-stu-id="1539d-112">Name</span></span>    | <span data-ttu-id="1539d-113">Wert</span><span class="sxs-lookup"><span data-stu-id="1539d-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1539d-114">Bereich</span><span class="sxs-lookup"><span data-stu-id="1539d-114">Scope</span></span>   | <span data-ttu-id="1539d-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1539d-115">Edge</span></span>        |
| <span data-ttu-id="1539d-116">Version</span><span class="sxs-lookup"><span data-stu-id="1539d-116">Version</span></span> | <span data-ttu-id="1539d-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="1539d-117">4.7.2</span></span>       |
| <span data-ttu-id="1539d-118">Typ</span><span class="sxs-lookup"><span data-stu-id="1539d-118">Type</span></span>    | <span data-ttu-id="1539d-119">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="1539d-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1539d-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1539d-120">Affected APIs</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
