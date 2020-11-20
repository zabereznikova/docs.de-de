---
ms.openlocfilehash: 56127309c5f5993ffc2e2faedd1f481e8131e094
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400634"
---
### <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="8a641-101">TextFormatFlags.ModifyString ist veraltet</span><span class="sxs-lookup"><span data-stu-id="8a641-101">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="8a641-102">Das Feld <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> ist als Warnung veraltet und kann in einer zukünftigen .NET-Version entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8a641-102">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8a641-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8a641-103">Change description</span></span>

<span data-ttu-id="8a641-104">In früheren .NET-Versionen ist das Enumerationsfeld <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> nicht als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="8a641-104">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="8a641-105">In .NET 5.0 oder höher ist es als Warnung als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="8a641-105">In .NET 5.0 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="8a641-106">Dieses Feld kann in einer zukünftigen .NET-Version entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8a641-106">This field may be removed in a future .NET version.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8a641-107">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="8a641-107">Reason for change</span></span>

<span data-ttu-id="8a641-108">Durch die Übergabe einer Zeichenfolge an <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> mit <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> wird die Zeichenfolge in einigen Situationen geändert.</span><span class="sxs-lookup"><span data-stu-id="8a641-108">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="8a641-109">Dieses Verhalten unterbricht die Unveränderlichkeitszusage der Zeichenfolge und kann zu einer schwerwiegenden Beschädigung des Runtimestatus von .NET führen.</span><span class="sxs-lookup"><span data-stu-id="8a641-109">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8a641-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8a641-110">Version introduced</span></span>

<span data-ttu-id="8a641-111">.NET 5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="8a641-111">.NET 5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8a641-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="8a641-112">Recommended action</span></span>

<span data-ttu-id="8a641-113">Aktualisieren Sie Code, der auf <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> basiert.</span><span class="sxs-lookup"><span data-stu-id="8a641-113">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="8a641-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="8a641-114">Category</span></span>

<span data-ttu-id="8a641-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8a641-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8a641-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8a641-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

-->
