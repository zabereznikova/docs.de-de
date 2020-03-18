---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449398"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="64f72-101">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="64f72-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="64f72-102">In .NET Core wird eine <xref:System.UnauthorizedAccessException> ausgelöst, wenn der Aufrufer versucht, den Wert eines Dateiattributs festzulegen, aber nicht über die Schreibberechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="64f72-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="64f72-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="64f72-103">Change description</span></span>

<span data-ttu-id="64f72-104">In .NET Framework wird eine <xref:System.ArgumentException> ausgelöst, wenn der Aufrufer versucht, in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> den Wert eines Dateiattributs festzulegen, aber nicht über die Schreibberechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="64f72-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="64f72-105">In .NET Core wird stattdessen eine <xref:System.UnauthorizedAccessException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="64f72-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="64f72-106">(In .NET Core wird eine <xref:System.ArgumentException> weiterhin ausgelöst, wenn der Aufrufer versucht, ein ungültiges Dateiattribut festzulegen.)</span><span class="sxs-lookup"><span data-stu-id="64f72-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="64f72-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="64f72-107">Version introduced</span></span>

<span data-ttu-id="64f72-108">1,0</span><span class="sxs-lookup"><span data-stu-id="64f72-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="64f72-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="64f72-109">Recommended action</span></span>

<span data-ttu-id="64f72-110">Ändern Sie beliebige `catch`-Anweisungen so, dass sie nach Bedarf <xref:System.UnauthorizedAccessException> anstelle von oder zusätzlich zu <xref:System.ArgumentException> abfangen.</span><span class="sxs-lookup"><span data-stu-id="64f72-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="64f72-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="64f72-111">Category</span></span>

<span data-ttu-id="64f72-112">CoreFx</span><span class="sxs-lookup"><span data-stu-id="64f72-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64f72-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="64f72-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
