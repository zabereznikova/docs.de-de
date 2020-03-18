---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74643928"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a><span data-ttu-id="9b83c-101">Zugriffsänderung für AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="9b83c-101">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>

<span data-ttu-id="9b83c-102">Ab .NET Core 3.0 RC1 hat sich der Zugriff auf `AccessibleObject.RuntimeIDFirstItem` aus `protected` in `internal` geändert.</span><span class="sxs-lookup"><span data-stu-id="9b83c-102">Starting in .NET Core 3.0 RC1, the accessibility of `AccessibleObject.RuntimeIDFirstItem` has changed from `protected` to `internal`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9b83c-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="9b83c-103">Change description</span></span>

<span data-ttu-id="9b83c-104">Ab .NET Core 3.0 Vorschau 4 war das Feld `AccessibleObject.RuntimeIDFirstItem` vom Typ `protected`.</span><span class="sxs-lookup"><span data-stu-id="9b83c-104">Starting with .NET Core 3.0 Preview 4, the `AccessibleObject.RuntimeIDFirstItem` field was `protected`.</span></span> <span data-ttu-id="9b83c-105">Ab .NET Core 3.0 RC1 wurde der Typ aus `protected` in `internal` geändert, um dem Zugriffstyp des Felds in .NET Framework zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9b83c-105">Starting with .NET Core 3.0 RC1, it has changed from `protected` to `internal` to align with the accessibility of the field in the .NET Framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9b83c-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9b83c-106">Version introduced</span></span>

<span data-ttu-id="9b83c-107">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="9b83c-107">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9b83c-108">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="9b83c-108">Recommended action</span></span>

<span data-ttu-id="9b83c-109">Die Änderung kann sich auf Sie auswirken, wenn Sie eine .NET Core-App mit einem Typ entwickelt haben, der von <xref:System.Windows.Forms.AccessibleObject> abgeleitet ist und auf das `RuntimeIDFirstItem`-Feld zugreift.</span><span class="sxs-lookup"><span data-stu-id="9b83c-109">The change can affect you if you've developed a .NET Core app with a type that derives from <xref:System.Windows.Forms.AccessibleObject> and accesses the `RuntimeIDFirstItem` field.</span></span> <span data-ttu-id="9b83c-110">Wenn dies der Fall ist, können Sie wie folgt eine lokale Konstante definieren:</span><span class="sxs-lookup"><span data-stu-id="9b83c-110">If this is the case, you can define a local constant as follows:</span></span>

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a><span data-ttu-id="9b83c-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="9b83c-111">Category</span></span>

<span data-ttu-id="9b83c-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9b83c-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9b83c-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9b83c-113">Affected APIs</span></span>

- <span data-ttu-id="9b83c-114">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="9b83c-114">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
