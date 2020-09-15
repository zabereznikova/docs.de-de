---
ms.openlocfilehash: 811b1a91169eeebfa056d9ecdb07d342d3b32d85
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615716"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a><span data-ttu-id="409b7-101">Icon.ToBitmap konvertiert Symbole mit PNG-Frames erfolgreich in Bitmap-Objekte</span><span class="sxs-lookup"><span data-stu-id="409b7-101">Icon.ToBitmap successfully converts icons with PNG frames into Bitmap objects</span></span>

#### <a name="details"></a><span data-ttu-id="409b7-102">Details</span><span class="sxs-lookup"><span data-stu-id="409b7-102">Details</span></span>

<span data-ttu-id="409b7-103">Beginnend mit den Apps für .NET Framework 4.6 konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>-Methode Symbole mit PNG-Bildern erfolgreich in „Bitmap“-Objekte.</span><span class="sxs-lookup"><span data-stu-id="409b7-103">Starting with the apps that target the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into Bitmap objects.</span></span><p/><span data-ttu-id="409b7-104">In Apps, die auf .NET Framework 4.5.2 und frühere Versionen ausgelegt sind, löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>-Methode eine <xref:System.ArgumentOutOfRangeException>-Ausnahme aus, wenn das „Icon“-Objekt PNG-Bilder aufweist.</span><span class="sxs-lookup"><span data-stu-id="409b7-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the  <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the Icon object has PNG frames.</span></span><p/><span data-ttu-id="409b7-105">Diese Änderung betrifft Apps, die für .NET Framework 4.6 neu kompiliert werden und eine spezielle Behandlung für die <xref:System.ArgumentOutOfRangeException> implementieren, die ausgelöst wird, wenn ein „Icon“-Objekt PNG-Bilder aufweist.</span><span class="sxs-lookup"><span data-stu-id="409b7-105">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an Icon object has PNG frames.</span></span> <span data-ttu-id="409b7-106">Bei der Ausführung unter .NET Framework 4.6 wird die Konvertierung erfolgreich durchgeführt und eine <xref:System.ArgumentOutOfRangeException> wird nicht mehr ausgelöst. Daher wird der Ausnahmehandler nicht mehr aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="409b7-106">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="409b7-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="409b7-107">Suggestion</span></span>

<span data-ttu-id="409b7-108">Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten beibehalten, indem Sie das folgende Element zum `<runtime>`-Abschnitt Ihrer app.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="409b7-108">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the `<runtime>` section of your app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>

<span data-ttu-id="409b7-109">Wenn die Datei „app.config“ bereits das `AppContextSwitchOverrides`-Element enthält, muss der neue Wert wie folgt mit dem Attribut zusammengeführt werden:</span><span class="sxs-lookup"><span data-stu-id="409b7-109">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the value attribute like this:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="409b7-110">name</span><span class="sxs-lookup"><span data-stu-id="409b7-110">Name</span></span>    | <span data-ttu-id="409b7-111">Wert</span><span class="sxs-lookup"><span data-stu-id="409b7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="409b7-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="409b7-112">Scope</span></span>   | <span data-ttu-id="409b7-113">Gering</span><span class="sxs-lookup"><span data-stu-id="409b7-113">Minor</span></span>       |
| <span data-ttu-id="409b7-114">Version</span><span class="sxs-lookup"><span data-stu-id="409b7-114">Version</span></span> | <span data-ttu-id="409b7-115">4.6</span><span class="sxs-lookup"><span data-stu-id="409b7-115">4.6</span></span>         |
| <span data-ttu-id="409b7-116">Typ</span><span class="sxs-lookup"><span data-stu-id="409b7-116">Type</span></span>    | <span data-ttu-id="409b7-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="409b7-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="409b7-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="409b7-118">Affected APIs</span></span>

- <xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType>
