---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032001"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="881be-101">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="881be-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="881be-102">In .NET Core wird eine <xref:System.UnauthorizedAccessException> ausgelöst, wenn der Aufrufer versucht, den Wert eines Dateiattributs festzulegen, aber nicht über die Schreibberechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="881be-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="881be-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="881be-103">Change description</span></span>

<span data-ttu-id="881be-104">In .NET Framework wird eine <xref:System.ArgumentException> ausgelöst, wenn der Aufrufer versucht, in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> den Wert eines Dateiattributs festzulegen, aber nicht über die Schreibberechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="881be-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="881be-105">In .NET Core wird stattdessen eine <xref:System.UnauthorizedAccessException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="881be-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="881be-106">(In .NET Core wird eine <xref:System.ArgumentException> weiterhin ausgelöst, wenn der Aufrufer versucht, ein ungültiges Dateiattribut festzulegen.)</span><span class="sxs-lookup"><span data-stu-id="881be-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="881be-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="881be-107">Version introduced</span></span>

<span data-ttu-id="881be-108">1.0</span><span class="sxs-lookup"><span data-stu-id="881be-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="881be-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="881be-109">Recommended action</span></span>

<span data-ttu-id="881be-110">Ändern Sie beliebige `catch`-Anweisungen so, dass sie nach Bedarf <xref:System.UnauthorizedAccessException> anstelle von oder zusätzlich zu <xref:System.ArgumentException> abfangen.</span><span class="sxs-lookup"><span data-stu-id="881be-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="881be-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="881be-111">Category</span></span>

<span data-ttu-id="881be-112">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="881be-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="881be-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="881be-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
