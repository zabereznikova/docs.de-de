---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595680"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a><span data-ttu-id="e6d39-101">UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt</span><span class="sxs-lookup"><span data-stu-id="e6d39-101">UriBuilder properties no longer prepend leading characters</span></span>

<span data-ttu-id="e6d39-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType> wird führenden `#`-Zeichen mehr vorangestellt, und <xref:System.UriBuilder.Query?displayProperty=nameWithType> wird führenden `?`-Zeichen nicht mehr vorangestellt, wenn ein solches Element bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e6d39-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType> no longer prepends a leading `#` character and <xref:System.UriBuilder.Query?displayProperty=nameWithType> no longer prepends a leading `?` character when one is already present.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e6d39-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e6d39-103">Change description</span></span>

<span data-ttu-id="e6d39-104">In .NET Framework stellen die <xref:System.UriBuilder.Fragment?displayProperty=nameWithType>- und <xref:System.UriBuilder.Query?displayProperty=nameWithType>-Eigenschaften immer ein `#`- oder `?`-Zeichen voran, das sich nach dem gespeicherten Wert richtet.</span><span class="sxs-lookup"><span data-stu-id="e6d39-104">In .NET Framework, the <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> and <xref:System.UriBuilder.Query?displayProperty=nameWithType> properties always prepend a `#` or `?` character, respectively, to the value being stored.</span></span> <span data-ttu-id="e6d39-105">Dieses Verhalten kann zu mehreren `#`- oder `?`-Zeichen im gespeicherten Wert führen, wenn die Zeichenfolge bereits eines dieser führenden Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="e6d39-105">This behavior can result in multiple `#` or `?` characters in the stored value if the string already contains one of these leading characters.</span></span> <span data-ttu-id="e6d39-106">Beispielsweise kann der Wert von <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> zu `##main` werden.</span><span class="sxs-lookup"><span data-stu-id="e6d39-106">For example, the value of <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> might become `##main`.</span></span>

<span data-ttu-id="e6d39-107">Ab .NET Core 1.0 stellen diese Eigenschaften die `#`- und `?`-Zeichen nicht mehr dem gespeicherten Wert voran, wenn diese bereits am Anfang der Zeichenfolge vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e6d39-107">Starting in .NET Core 1.0, these properties no longer prepend the `#` or `?` characters to the stored value if one is already present at the beginning of the string.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e6d39-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e6d39-108">Version introduced</span></span>

<span data-ttu-id="e6d39-109">1.0</span><span class="sxs-lookup"><span data-stu-id="e6d39-109">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e6d39-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="e6d39-110">Recommended action</span></span>

<span data-ttu-id="e6d39-111">Beim Festlegen der Eigenschaftswerte müssen Sie keines dieser führenden Zeichen mehr explizit entfernen.</span><span class="sxs-lookup"><span data-stu-id="e6d39-111">You no longer need to explicitly remove any of these leading characters when setting the property values.</span></span> <span data-ttu-id="e6d39-112">Dies ist besonders nützlich, wenn Sie Werte anfügen, da Sie die führenden `#`- oder `?`-Zeichen nicht mehr jedes Mal entfernen müssen.</span><span class="sxs-lookup"><span data-stu-id="e6d39-112">This is especially useful when you're appending values, because you no longer have to remove the leading `#` or `?` each time you append.</span></span>

<span data-ttu-id="e6d39-113">Der folgende Codeausschnitt zeigt z. B. den Verhaltensunterschied zwischen .NET Framework und .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6d39-113">For example, the following code snippet shows the behavior difference between .NET Framework and .NET Core.</span></span>

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- <span data-ttu-id="e6d39-114">In .NET Framework lautet die Ausgabe `????one=1&two=2&three=3&four=4`.</span><span class="sxs-lookup"><span data-stu-id="e6d39-114">In .NET Framework, the output is `????one=1&two=2&three=3&four=4`.</span></span>
- <span data-ttu-id="e6d39-115">In .NET Core lautet die Ausgabe `?one=1&two=2&three=3&four=4`.</span><span class="sxs-lookup"><span data-stu-id="e6d39-115">In .NET Core, the output is `?one=1&two=2&three=3&four=4`.</span></span>

#### <a name="category"></a><span data-ttu-id="e6d39-116">Kategorie</span><span class="sxs-lookup"><span data-stu-id="e6d39-116">Category</span></span>

<span data-ttu-id="e6d39-117">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="e6d39-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e6d39-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e6d39-118">Affected APIs</span></span>

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
