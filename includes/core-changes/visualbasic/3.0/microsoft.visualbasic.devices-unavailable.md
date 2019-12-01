---
ms.openlocfilehash: 4c47b95e98aca727d9f0eda54a167a71fd53afb9
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567465"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="32d75-101">Typen im Microsoft.VisualBasic.Devices-Namespace nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="32d75-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="32d75-102">Die Typen im <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>-Namespace sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32d75-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="32d75-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="32d75-103">Version introduced</span></span>

<span data-ttu-id="32d75-104">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="32d75-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="32d75-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="32d75-105">Change description</span></span>

<span data-ttu-id="32d75-106">Die Typen im <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>-Namespace waren in einigen Versionen von .NET Core 3.0 Preview verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32d75-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="32d75-107">Ab .NET Core 3.0 Preview 9 sind sie nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32d75-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="32d75-108">Die Typen wurden entfernt, um unnötige Assemblyabhängigkeiten oder Breaking Changes in nachfolgenden Releases zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="32d75-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="32d75-109">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="32d75-109">Recommended action</span></span>

<span data-ttu-id="32d75-110">Wenn Sie für Ihren Code <xref:Microsoft.VisualBasic.Devices>-Typen und deren Member benötigen, können Sie möglicherweise einen entsprechenden Typ oder Member in der .NET-Klassenbibliothek verwenden.</span><span class="sxs-lookup"><span data-stu-id="32d75-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="32d75-111">Beispielsweise werden die entsprechenden Funktionen für die <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType>-Klasse von den Typen <xref:System.DateTime?displayProperty=nameWithType> und <xref:System.Environment?displayProperty=nameWithType> bereitgestellt, und die entsprechenden Funktionen für die <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType>-Klasse wird von Typen im <xref:System.IO.Ports?displayProperty=nameWithType>-Namespace bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="32d75-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="32d75-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="32d75-112">Category</span></span>

<span data-ttu-id="32d75-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32d75-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="32d75-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="32d75-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

