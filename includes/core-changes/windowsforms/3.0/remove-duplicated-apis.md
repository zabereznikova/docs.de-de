---
ms.openlocfilehash: e609b8006846cd202a6a7eeec2529cf1fbb09e7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936989"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="e8ddc-101">Doppelte APIs aus Windows Forms entfernt</span><span class="sxs-lookup"><span data-stu-id="e8ddc-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="e8ddc-102">Eine Reihe von APIs, die versehentlich im Namespace <xref:System.Windows.Forms?displayProperty=fullName> ab .NET Core 3.0 Vorschau 4 dupliziert wurden, wurden in .NET Core 3.0 RC1 entfernt.</span><span class="sxs-lookup"><span data-stu-id="e8ddc-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e8ddc-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e8ddc-103">Change description</span></span>

<span data-ttu-id="e8ddc-104">.NET Core 3.0 Vorschau 4 hat versehentlich eine Reihe von Typen im Namespace <xref:System.Windows.Forms?displayProperty=fullName> dupliziert, die bereits im Namespace <xref:System.ComponentModel.Design?displayProperty=fullName> vorhanden waren.</span><span class="sxs-lookup"><span data-stu-id="e8ddc-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="e8ddc-105">Ab .NET Core 3.0 RC1 sind diese duplizierten Typen nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8ddc-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="e8ddc-106">In der folgenden Tabelle werden der ursprüngliche Typ und der duplizierte Typ aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="e8ddc-106">The following table shows lists the original type and its duplicated type:</span></span>

> [!div class="mx-tdCol2BreakAll"]
> |<span data-ttu-id="e8ddc-107">Ursprünglicher Typ</span><span class="sxs-lookup"><span data-stu-id="e8ddc-107">Original type</span></span>|<span data-ttu-id="e8ddc-108">Duplizierter Typ</span><span class="sxs-lookup"><span data-stu-id="e8ddc-108">Duplicated type</span></span>|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="e8ddc-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e8ddc-109">Version introduced</span></span>

<span data-ttu-id="e8ddc-110">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="e8ddc-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e8ddc-111">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="e8ddc-111">Recommended action</span></span>

<span data-ttu-id="e8ddc-112">Aktualisieren Sie den Code so, dass er auf den ursprünglichen Typ verweist, wie in der Spalte **Ursprünglicher Typ** der Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e8ddc-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="e8ddc-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="e8ddc-113">Category</span></span>

<span data-ttu-id="e8ddc-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8ddc-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e8ddc-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e8ddc-115">Affected APIs</span></span>

- <span data-ttu-id="e8ddc-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="e8ddc-116">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis.

-->
