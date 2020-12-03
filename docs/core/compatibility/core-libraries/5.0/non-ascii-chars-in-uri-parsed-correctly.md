---
title: 'Breaking Change: Ordnungsgemäße Analyse von URI-Pfaden mit Nicht-ASCII-Zeichen unter UNIX'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den absolute URI-Pfade, die ASCII-fremde Zeichen enthalten, jetzt auf UNIX-Plattformen richtig analysiert werden.
ms.date: 11/01/2020
ms.openlocfilehash: 94de4e0eb94a11153d873871d4003422a4286a0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759216"
---
# <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a><span data-ttu-id="820d5-103">Ordnungsgemäße Analyse von URI-Pfaden mit Nicht-ASCII-Zeichen unter UNIX</span><span class="sxs-lookup"><span data-stu-id="820d5-103">URI paths with non-ASCII characters parse correctly on Unix</span></span>

<span data-ttu-id="820d5-104">Es wurde ein Fehler in der <xref:System.Uri?displayProperty=fullName>-Klasse behoben, sodass absolute URI-Pfade, die Nicht-ASCII-Zeichen enthalten, jetzt auf UNIX-Plattformen korrekt analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="820d5-104">A bug was fixed in the <xref:System.Uri?displayProperty=fullName> class such that absolute URI paths that contain non-ASCII characters now parse correctly on Unix platforms.</span></span>

## <a name="change-description"></a><span data-ttu-id="820d5-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="820d5-105">Change description</span></span>

<span data-ttu-id="820d5-106">In früheren .NET-Versionen werden absolute URI-Pfade, die Nicht-ASCII-Zeichen enthalten, auf UNIX-Plattformen falsch analysiert, und Segmente des Pfads werden dupliziert.</span><span class="sxs-lookup"><span data-stu-id="820d5-106">In previous versions of .NET, absolute URI paths that contain non-ASCII characters are parsed incorrectly on Unix platforms, and segments of the path are duplicated.</span></span> <span data-ttu-id="820d5-107">(Absolute Pfade beginnen mit „/“.) Das Analyseproblem wurde für .NET 5.0 behoben.</span><span class="sxs-lookup"><span data-stu-id="820d5-107">(Absolute paths are those that start with "/".) The parsing issue has been fixed for .NET 5.0.</span></span> <span data-ttu-id="820d5-108">Wenn Sie von einer früheren Version von .NET zu .NET 5.0 oder höher wechseln, erhalten Sie unterschiedliche Werte, die von <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType> oder anderen <xref:System.Uri>-Membern erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="820d5-108">If you move from a previous version of .NET to .NET 5.0 or later, you'll get different values produced by <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType>, and other <xref:System.Uri> members.</span></span>

<span data-ttu-id="820d5-109">Beachten Sie bei der Ausführung unter UNIX die Ausgabe des folgenden Codes.</span><span class="sxs-lookup"><span data-stu-id="820d5-109">Consider the output of the following code when run on Unix.</span></span>

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

<span data-ttu-id="820d5-110">Ausgabe bei der vorherigen .NET-Version:</span><span class="sxs-lookup"><span data-stu-id="820d5-110">Output on previous .NET version:</span></span>

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

<span data-ttu-id="820d5-111">Ausgabe bei .NET 5.0 oder einer höheren Version:</span><span class="sxs-lookup"><span data-stu-id="820d5-111">Output on .NET 5.0 or later version:</span></span>

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

## <a name="version-introduced"></a><span data-ttu-id="820d5-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="820d5-112">Version introduced</span></span>

<span data-ttu-id="820d5-113">5.0</span><span class="sxs-lookup"><span data-stu-id="820d5-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="820d5-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="820d5-114">Recommended action</span></span>

<span data-ttu-id="820d5-115">Wenn Sie Code verwenden, der die duplizierten Pfadsegmente erwartet und berücksichtigt, können Sie diesen Code entfernen.</span><span class="sxs-lookup"><span data-stu-id="820d5-115">If you have code that expects and accounts for the duplicated path segments, you can remove that code.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="820d5-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="820d5-116">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
