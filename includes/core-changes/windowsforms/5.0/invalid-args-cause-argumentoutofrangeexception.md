---
ms.openlocfilehash: f42da00487735acdcc60f876c75e1dfd17103008
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702439"
---
### <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="87322-101">WinForms-Eigenschaften lösen nun ArgumentOutOfRangeException aus</span><span class="sxs-lookup"><span data-stu-id="87322-101">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="87322-102">Einige Windows Forms-Eigenschaften lösen nun eine <xref:System.ArgumentOutOfRangeException> für ungültige Argumente aus, was zuvor nicht der Fall war.</span><span class="sxs-lookup"><span data-stu-id="87322-102">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="87322-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="87322-103">Change description</span></span>

<span data-ttu-id="87322-104">Zuvor haben diese Eigenschaften verschiedene Ausnahmen ausgelöst, wie z. B. <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException> oder <xref:System.ArgumentException>, wenn Argumente außerhalb des zulässigen Bereichs übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="87322-104">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="87322-105">Ab .NET 5.0 lösen diese Eigenschaften stattdessen eine <xref:System.ArgumentOutOfRangeException> aus, wenn Argumente außerhalb des zulässigen Bereichs übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="87322-105">Starting in .NET 5.0, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="87322-106">Das Auslösen einer <xref:System.ArgumentOutOfRangeException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="87322-106">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="87322-107">Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="87322-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="87322-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="87322-108">Version introduced</span></span>

<span data-ttu-id="87322-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="87322-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="87322-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="87322-110">Recommended action</span></span>

- <span data-ttu-id="87322-111">Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="87322-111">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="87322-112">Behandeln Sie ggf. eine <xref:System.ArgumentOutOfRangeException>, wenn Sie die Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="87322-112">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

#### <a name="category"></a><span data-ttu-id="87322-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="87322-113">Category</span></span>

<span data-ttu-id="87322-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87322-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="87322-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="87322-115">Affected APIs</span></span>

<span data-ttu-id="87322-116">In der folgenden Tabelle sind die betroffenen Eigenschaften und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="87322-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="87322-117">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="87322-117">Property</span></span> | <span data-ttu-id="87322-118">Parametername</span><span class="sxs-lookup"><span data-stu-id="87322-118">Parameter name</span></span> | <span data-ttu-id="87322-119">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="87322-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="87322-120">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="87322-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="87322-121">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="87322-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="87322-122">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="87322-122">5.0 Preview 6</span></span> |

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

-->
