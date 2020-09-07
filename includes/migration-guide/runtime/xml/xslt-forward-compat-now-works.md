---
ms.openlocfilehash: 8c8477ae3719cfcc2060459ba85bcc9e76f11c41
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497836"
---
### <a name="xslt-forward-compat-now-works"></a><span data-ttu-id="551d4-101">Die Vorwärtskompatibilität für XSLT funktioniert jetzt</span><span class="sxs-lookup"><span data-stu-id="551d4-101">XSLT forward compat now works</span></span>

#### <a name="details"></a><span data-ttu-id="551d4-102">Details</span><span class="sxs-lookup"><span data-stu-id="551d4-102">Details</span></span>

<span data-ttu-id="551d4-103">In .NET Framework 4 verursachte die XSLT 1.0-Vorwärtskompatibilität die folgenden Probleme:</span><span class="sxs-lookup"><span data-stu-id="551d4-103">In the .NET Framework 4, XSLT 1.0 forward compatibility had the following issues:</span></span><ul><li><span data-ttu-id="551d4-104">Beim Laden eines Stylesheets trat ein Fehler auf, wenn die Version auf 2.0 festgelegt war und der Parser ein unbekanntes XSLT 1.0-Konstrukt feststellte.</span><span class="sxs-lookup"><span data-stu-id="551d4-104">Loading a style sheet failed if its version was set to 2.0 and the parser encountered an unrecognized XSLT 1.0 construct.</span></span></li><li><span data-ttu-id="551d4-105">Das <code>xsl:sort</code>-Konstrukt konnte keine Daten sortieren, wenn die Stylesheetversion auf 1.1 festgelegt war.</span><span class="sxs-lookup"><span data-stu-id="551d4-105">The <code>xsl:sort</code> construct failed to sort data if the style sheet version was set to 1.1.</span></span></li></ul><span data-ttu-id="551d4-106">In .NET Framework 4.5 wurden diese Probleme behoben, und der XSLT 1.0-Vorwärtskompatibilitätsmodus funktioniert ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="551d4-106">In the .NET Framework 4.5, these issues have been fixed, and XSLT 1.0 forward compatibility mode works properly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="551d4-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="551d4-107">Suggestion</span></span>

<span data-ttu-id="551d4-108">Die meisten Apps sollten zwar davon nicht betroffen sind, aber die Daten werden teilweise unterschiedlich sortiert, da das xsl:sort-Element jetzt berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="551d4-108">Most apps should be unaffected, however data will be sorted differently in some cases now that xsl:sort is respected.</span></span> <span data-ttu-id="551d4-109">Wenn <code>xsl:sort</code> in 1.1-Stylesheets verwendet wird, sollten Sie sicherstellen, dass die Apps nicht von der unsortierten Reihenfolge von Daten abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="551d4-109">If <code>xsl:sort</code> is used in 1.1 style sheets, confirm that apps were not depending on the unsorted order of data.</span></span> <span data-ttu-id="551d4-110">Wenn Apps von dem in Version 4.0 enthaltenen Sortierverhalten abhängig ist, sollten Sie <code>xsl:sort</code> aus dem Stylesheet entfernen.</span><span class="sxs-lookup"><span data-stu-id="551d4-110">If apps rely on the 4.0 sorting behavior, remove <code>xsl:sort</code> from the style sheet.</span></span>

| <span data-ttu-id="551d4-111">name</span><span class="sxs-lookup"><span data-stu-id="551d4-111">Name</span></span>    | <span data-ttu-id="551d4-112">Wert</span><span class="sxs-lookup"><span data-stu-id="551d4-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="551d4-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="551d4-113">Scope</span></span>   |<span data-ttu-id="551d4-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="551d4-114">Edge</span></span>|
|<span data-ttu-id="551d4-115">Version</span><span class="sxs-lookup"><span data-stu-id="551d4-115">Version</span></span>|<span data-ttu-id="551d4-116">4.5</span><span class="sxs-lookup"><span data-stu-id="551d4-116">4.5</span></span>|
|<span data-ttu-id="551d4-117">Typ</span><span class="sxs-lookup"><span data-stu-id="551d4-117">Type</span></span>|<span data-ttu-id="551d4-118">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="551d4-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="551d4-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="551d4-119">Affected APIs</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Xml.Xsl.XslCompiledTransform`

-->
