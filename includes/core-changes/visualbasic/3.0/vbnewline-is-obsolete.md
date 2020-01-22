---
ms.openlocfilehash: 95a4c807f5c1077cf52f54b196e904ebc98c32f8
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116357"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="a39d8-101">„Microsoft.VisualBasic.Constants.vbNewLine“ ist veraltet</span><span class="sxs-lookup"><span data-stu-id="a39d8-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="a39d8-102">Die Konstante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> ist ab .NET Core 3.0 Preview 8 als [\[Veraltet\]](xref:System.ObsoleteAttribute) gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="a39d8-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked as [\[Obsolete\]](xref:System.ObsoleteAttribute) starting with .NET Core 3.0 Preview 8.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a39d8-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a39d8-103">Version introduced</span></span>

<span data-ttu-id="a39d8-104">3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="a39d8-104">3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="a39d8-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a39d8-105">Change description</span></span>

<span data-ttu-id="a39d8-106">Ab .NET Core 3.0 Preview 8 wird das Attribut [Veraltet](xref:System.ObsoleteAttribute) auf die Konstante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> angewendet.</span><span class="sxs-lookup"><span data-stu-id="a39d8-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant.</span></span> <span data-ttu-id="a39d8-107">Die Verwendung der Konstante führt zu einer Compilerwarnung.</span><span class="sxs-lookup"><span data-stu-id="a39d8-107">Use of the constant produces a compiler warning.</span></span> <span data-ttu-id="a39d8-108">In NET Framework Core und in früheren Releases von .NET Core war sie nicht als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="a39d8-108">In .NET Framework and previous releases of .NET Core, it was not marked as obsolete.</span></span>

<span data-ttu-id="a39d8-109">Diese Änderung wurde vorgenommen, um Visual Basic als Sprache für die Entwicklung auf mehreren Plattformen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a39d8-109">This change was made to support Visual Basic as a language for multi-platform development.</span></span> <span data-ttu-id="a39d8-110">Die Konstante <xref:Microsoft.VisualBasic.Constants.vbNewLine> entspricht `\r\n`, der Zeichenfolge für neue Zeile bei Windows.</span><span class="sxs-lookup"><span data-stu-id="a39d8-110">The <xref:Microsoft.VisualBasic.Constants.vbNewLine> constant is equivalent to `\r\n`, the newline character sequence on Windows.</span></span> <span data-ttu-id="a39d8-111">Bei Unix-basierten Systemen ist `\n` das Zeichen für eine neue Zeile.</span><span class="sxs-lookup"><span data-stu-id="a39d8-111">On Unix-based systems, the newline character is `\n`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a39d8-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="a39d8-112">Recommended action</span></span>

<span data-ttu-id="a39d8-113">Die [ObsoleteAttribute](xref:System.ObsoleteAttribute)-Meldung für <xref:Microsoft.VisualBasic.Constants.vbNewLine> enthält folgende Empfehlung:</span><span class="sxs-lookup"><span data-stu-id="a39d8-113">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for <xref:Microsoft.VisualBasic.Constants.vbNewLine> includes the following recommendation:</span></span>

<span data-ttu-id="a39d8-114">Für einen Wagenrücklauf oder Zeilenvorschub verwenden Sie <xref:Microsoft.VisualBasic.Constants.vbCrLf>.</span><span class="sxs-lookup"><span data-stu-id="a39d8-114">For a carriage return and line feed, use <xref:Microsoft.VisualBasic.Constants.vbCrLf>.</span></span> <span data-ttu-id="a39d8-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>. (Verwenden Sie für einen Wagenrücklauf und Zeilenvorschub „vbCrLf“. Verwenden Sie auf der aktuellen Plattform für einen Zeilenumbruch „Environment.NewLine“.).</span><span class="sxs-lookup"><span data-stu-id="a39d8-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="a39d8-116">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a39d8-116">Category</span></span>

<span data-ttu-id="a39d8-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a39d8-117">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a39d8-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a39d8-118">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
