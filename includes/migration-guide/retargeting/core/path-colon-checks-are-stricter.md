---
ms.openlocfilehash: 6af63c0a58a3273aa98fa70f22e3637b481806b4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496814"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="f411c-101">Die Überprüfung von Pfaden auf Doppelpunkte ist genauer</span><span class="sxs-lookup"><span data-stu-id="f411c-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="f411c-102">Details</span><span class="sxs-lookup"><span data-stu-id="f411c-102">Details</span></span>

<span data-ttu-id="f411c-103">In .NET Framework 4.6.2 wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (hinsichtlich Länge und Format).</span><span class="sxs-lookup"><span data-stu-id="f411c-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="f411c-104">Die Überprüfung auf eine korrekte Syntax bei der Verwendung von Laufwerkstrennzeichen (Doppelpunkt) wurde verbessert. Als Nebenwirkung wurden mehrere URI-Pfade in einigen ausgewählten Pfad-APIs blockiert, in denen sie zuvor toleriert wurden.</span><span class="sxs-lookup"><span data-stu-id="f411c-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they were previously tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f411c-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="f411c-105">Suggestion</span></span>

<span data-ttu-id="f411c-106">Wenn ein URI an betroffene APIs übergeben wird, sollten Sie zunächst die Zeichenfolge in einen gültigen Pfad ändern.</span><span class="sxs-lookup"><span data-stu-id="f411c-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span>

- <span data-ttu-id="f411c-107">Entfernen Sie das Schema manuell aus den URLs (entfernen Sie z. B. `file://` aus den URLs).</span><span class="sxs-lookup"><span data-stu-id="f411c-107">Remove the scheme from URLs manually (for example, remove `file://` from URLs).</span></span>

- <span data-ttu-id="f411c-108">Übergeben Sie den URI an die Klasse <xref:System.Uri>, und verwenden Sie <xref:System.Uri.LocalPath>.</span><span class="sxs-lookup"><span data-stu-id="f411c-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath>.</span></span>

<span data-ttu-id="f411c-109">Stattdessen können Sie sich gegen die Normalisierung des neuen Pfads entscheiden, indem Sie die AppContext-Option `Switch.System.IO.UseLegacyPathHandling` auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="f411c-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to `true`.</span></span>

| <span data-ttu-id="f411c-110">Name</span><span class="sxs-lookup"><span data-stu-id="f411c-110">Name</span></span>    | <span data-ttu-id="f411c-111">Wert</span><span class="sxs-lookup"><span data-stu-id="f411c-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f411c-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="f411c-112">Scope</span></span>   | <span data-ttu-id="f411c-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f411c-113">Edge</span></span>        |
| <span data-ttu-id="f411c-114">Version</span><span class="sxs-lookup"><span data-stu-id="f411c-114">Version</span></span> | <span data-ttu-id="f411c-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="f411c-115">4.6.2</span></span>       |
| <span data-ttu-id="f411c-116">Typ</span><span class="sxs-lookup"><span data-stu-id="f411c-116">Type</span></span>    | <span data-ttu-id="f411c-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="f411c-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f411c-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f411c-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
