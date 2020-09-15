---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616129"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a><span data-ttu-id="01e27-101">Die bidirektionale Datenbindung an eine Eigenschaft mit einem nicht öffentlichen Setter wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="01e27-101">Two-way data-binding to a property with a non-public setter is not supported</span></span>

#### <a name="details"></a><span data-ttu-id="01e27-102">Details</span><span class="sxs-lookup"><span data-stu-id="01e27-102">Details</span></span>

<span data-ttu-id="01e27-103">Der Versuch, Daten ohne einen öffentlichen Setter an eine Eigenschaft zu binden, wurde nie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="01e27-103">Attempting to data bind to a property without a public setter has never been a supported scenario.</span></span> <span data-ttu-id="01e27-104">Ab .NET Framework 4.5.1 löst dieses Szenario <xref:System.InvalidOperationException?displayProperty=fullName> aus.</span><span class="sxs-lookup"><span data-stu-id="01e27-104">Beginning in the .NET Framework 4.5.1, this scenario will throw an <xref:System.InvalidOperationException?displayProperty=fullName>.</span></span> <span data-ttu-id="01e27-105">Beachten Sie, dass diese neue Ausnahme nur für Apps ausgelöst wird, die speziell auf .NET Framework 4.5.1 abzielen.</span><span class="sxs-lookup"><span data-stu-id="01e27-105">Note that this new exception will only be thrown for apps that specifically target the .NET Framework 4.5.1.</span></span> <span data-ttu-id="01e27-106">Wenn eine App auf .NET Framework 4.5 ausgerichtet ist, wird der Aufruf zugelassen.</span><span class="sxs-lookup"><span data-stu-id="01e27-106">If an app targets the .NET Framework 4.5, the call will be allowed.</span></span> <span data-ttu-id="01e27-107">Wenn die App nicht auf eine bestimmte Version von .NET Framework ausgerichtet ist, wird die Bindung als unidirektionale Bindung behandelt.</span><span class="sxs-lookup"><span data-stu-id="01e27-107">If the app does not target a particular .NET Framework version, the binding will be treated as one-way.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="01e27-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="01e27-108">Suggestion</span></span>

<span data-ttu-id="01e27-109">Die App sollte aktualisiert werden, um entweder die unidirektionale Bindung zu verwenden oder den Setter der Eigenschaft öffentlich zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="01e27-109">The app should be updated to either use one-way binding, or expose the property's setter publicly.</span></span> <span data-ttu-id="01e27-110">Alternativ können Sie die App auf .NET Framework 4.5 ausrichten, um das alte Verhalten zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="01e27-110">Alternatively, targeting the .NET Framework 4.5 will cause the app to exhibit the old behavior.</span></span>

| <span data-ttu-id="01e27-111">name</span><span class="sxs-lookup"><span data-stu-id="01e27-111">Name</span></span>    | <span data-ttu-id="01e27-112">Wert</span><span class="sxs-lookup"><span data-stu-id="01e27-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="01e27-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="01e27-113">Scope</span></span>   | <span data-ttu-id="01e27-114">Gering</span><span class="sxs-lookup"><span data-stu-id="01e27-114">Minor</span></span>       |
| <span data-ttu-id="01e27-115">Version</span><span class="sxs-lookup"><span data-stu-id="01e27-115">Version</span></span> | <span data-ttu-id="01e27-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="01e27-116">4.5.1</span></span>       |
| <span data-ttu-id="01e27-117">Typ</span><span class="sxs-lookup"><span data-stu-id="01e27-117">Type</span></span>    | <span data-ttu-id="01e27-118">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="01e27-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="01e27-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="01e27-119">Affected APIs</span></span>

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>
