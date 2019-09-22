---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117104"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="30d2c-101">„Microsoft.VisualBasic.Constants.vbNewLine“ ist veraltet</span><span class="sxs-lookup"><span data-stu-id="30d2c-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="30d2c-102">Die <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>-Konstante ist im .NET Framework mit [ObsoleteAttribute](xref:System.ObsoleteAttribute) versehen und damit als veraltet gekennzeichnet. Das Attribut fehlte jedoch bislang in der .NET Core 3.0-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="30d2c-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) in .NET Framework, but the attribute was missing previously in the .NET Core 3.0 library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="30d2c-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="30d2c-103">Version introduced</span></span>

<span data-ttu-id="30d2c-104">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="30d2c-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="30d2c-105">Details</span><span class="sxs-lookup"><span data-stu-id="30d2c-105">Details</span></span>

<span data-ttu-id="30d2c-106">Ab Preview 8 von .NET Core 3.0 wird das Attribut [ObsoleteAttribute](xref:System.ObsoleteAttribute) auf die <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>-Konstante angewendet, um eine Angleichung an `vbNewLine` im .NET Framework zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="30d2c-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant to conform to `vbNewLine` in the .NET Framework.</span></span> <span data-ttu-id="30d2c-107">Die Verwendung der `vbNewLine`-Konstante führt zu einer Compilerwarnung.</span><span class="sxs-lookup"><span data-stu-id="30d2c-107">Use of the `vbNewLine` constant produces a compiler warning.</span></span> 

<span data-ttu-id="30d2c-108">In früheren Versionen von .NET Core löste `vbNewLine` keine Compilerwarnung aus.</span><span class="sxs-lookup"><span data-stu-id="30d2c-108">In previous versions of .NET Core, `vbNewLine` did not produce a compiler warning.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="30d2c-109">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="30d2c-109">Recommended action</span></span>

<span data-ttu-id="30d2c-110">Die [ObsoleteAttribute](xref:System.ObsoleteAttribute)-Meldung für `vbNewLine` enthält folgende Empfehlung:</span><span class="sxs-lookup"><span data-stu-id="30d2c-110">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="30d2c-111">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span><span class="sxs-lookup"><span data-stu-id="30d2c-111">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="30d2c-112">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>. (Verwenden Sie für einen Wagenrücklauf und Zeilenvorschub „vbCrLf“. Verwenden Sie auf der aktuellen Plattform für einen Zeilenumbruch „Environment.NewLine“.).</span><span class="sxs-lookup"><span data-stu-id="30d2c-112">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="30d2c-113">Category (Kategorie)</span><span class="sxs-lookup"><span data-stu-id="30d2c-113">Category</span></span>

<span data-ttu-id="30d2c-114">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30d2c-114">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="30d2c-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="30d2c-115">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

