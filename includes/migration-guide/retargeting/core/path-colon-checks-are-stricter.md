---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614482"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="a1497-101">Die Überprüfung von Pfaden auf Doppelpunkte ist genauer</span><span class="sxs-lookup"><span data-stu-id="a1497-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="a1497-102">Details</span><span class="sxs-lookup"><span data-stu-id="a1497-102">Details</span></span>

<span data-ttu-id="a1497-103">In .NET Framework 4.6.2 wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (hinsichtlich Länge und Format).</span><span class="sxs-lookup"><span data-stu-id="a1497-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="a1497-104">Die Überprüfung auf eine korrekte Syntax bei der Verwendung von Laufwerkstrennzeichen (Doppelpunkt) wurde verbessert. Als Nebenwirkung wurden mehrere URI-Pfade in einigen ausgewählten Pfad-APIs blockiert, in denen sie vorher toleriert wurden.</span><span class="sxs-lookup"><span data-stu-id="a1497-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they used to be tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a1497-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a1497-105">Suggestion</span></span>

<span data-ttu-id="a1497-106">Wenn ein URI an betroffene APIs übergeben wird, sollten Sie zunächst die Zeichenfolge in einen gültigen Pfad ändern.</span><span class="sxs-lookup"><span data-stu-id="a1497-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span><ul><li><span data-ttu-id="a1497-107">Entfernen Sie das Schema manuell aus den URLs (entfernen Sie z.B. `file://` aus den URLs).</span><span class="sxs-lookup"><span data-stu-id="a1497-107">Remove the scheme from URLs manually (e.g. remove `file://` from URLs)</span></span>

- <span data-ttu-id="a1497-108">Übergeben Sie den URI der Klasse <xref:System.Uri> und verwenden Sie <xref:System.Uri.LocalPath>.</span><span class="sxs-lookup"><span data-stu-id="a1497-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath></span></span>

<span data-ttu-id="a1497-109">Alternativ können Sie sich gegen die Normalisierung des neuen Pfads entscheiden, indem Sie die AppContext-Option `Switch.System.IO.UseLegacyPathHandling` auf TRUE festlegen.</span><span class="sxs-lookup"><span data-stu-id="a1497-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to true.</span></span>

| <span data-ttu-id="a1497-110">Name</span><span class="sxs-lookup"><span data-stu-id="a1497-110">Name</span></span>    | <span data-ttu-id="a1497-111">Wert</span><span class="sxs-lookup"><span data-stu-id="a1497-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a1497-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="a1497-112">Scope</span></span>   | <span data-ttu-id="a1497-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a1497-113">Edge</span></span>        |
| <span data-ttu-id="a1497-114">Version</span><span class="sxs-lookup"><span data-stu-id="a1497-114">Version</span></span> | <span data-ttu-id="a1497-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="a1497-115">4.6.2</span></span>       |
| <span data-ttu-id="a1497-116">Typ</span><span class="sxs-lookup"><span data-stu-id="a1497-116">Type</span></span>    | <span data-ttu-id="a1497-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="a1497-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a1497-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a1497-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
