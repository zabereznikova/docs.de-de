---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614541"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a><span data-ttu-id="86d37-101">Falsche Implementierung von MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="86d37-101">Incorrect implementation of MemberDescriptor.Equals</span></span>

#### <a name="details"></a><span data-ttu-id="86d37-102">Details</span><span class="sxs-lookup"><span data-stu-id="86d37-102">Details</span></span>

<span data-ttu-id="86d37-103">Die ursprüngliche Implementierung der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>-Methode hat zwei verschiedene Zeichenfolgeneigenschaften der zu vergleichenden Objekte miteinander verglichen: den Kategorienamen und die Beschreibungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="86d37-103">The original implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method compares two different string properties from the objects being compared: the category name and the description string.</span></span> <span data-ttu-id="86d37-104">Die Korrektur besteht darin, <xref:System.ComponentModel.MemberDescriptor.Category> des ersten Objekts mit <xref:System.ComponentModel.MemberDescriptor.Category> des zweiten Objekts und <xref:System.ComponentModel.MemberDescriptor.Description> des ersten Objekts mit <xref:System.ComponentModel.MemberDescriptor.Description> des zweiten Objekts zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="86d37-104">The fix is to compare the <xref:System.ComponentModel.MemberDescriptor.Category> of the first object to the <xref:System.ComponentModel.MemberDescriptor.Category> of the second one, and the <xref:System.ComponentModel.MemberDescriptor.Description> of the first to the <xref:System.ComponentModel.MemberDescriptor.Description> of the second.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="86d37-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="86d37-105">Suggestion</span></span>

<span data-ttu-id="86d37-106">Wenn Ihre Anwendung erfordert, dass <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> manchmal `false` zurückgibt, wenn Deskriptoren äquivalent sind, und sie als Zielplattform .NET Framework 4.6.2 verwendet, sind mehrere Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="86d37-106">If your application depends on <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> sometimes returning `false` when descriptors are equivalent, and you are targeting the .NET Framework 4.6.2 or later, you have several options:</span></span>

- <span data-ttu-id="86d37-107">Nehmen Sie Codeänderungen vor, um die <xref:System.ComponentModel.MemberDescriptor.Category>- und <xref:System.ComponentModel.MemberDescriptor.Description>-Felder manuell zusätzlich zum Aufrufen der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>-Methode zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="86d37-107">Make code changes to compare the <xref:System.ComponentModel.MemberDescriptor.Category> and <xref:System.ComponentModel.MemberDescriptor.Description> fields manually in addition to calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method.</span></span>
- <span data-ttu-id="86d37-108">Sie können diese Änderung deaktivieren, indem Sie der Datei „app.config“ den folgenden Wert hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="86d37-108">Opt out of this change by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

<span data-ttu-id="86d37-109">Wenn Ihre Anwendung für .NET Framework 4.6.1 oder frühere Versionen konzipiert ist, unter .NET Framework 4.6.2 ausgeführt wird und Sie diese Änderung aktivieren möchten, können Sie den Kompatibilitätsschalter auf `false` festlegen, indem Sie der Datei „app.config“ den folgenden Wert hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="86d37-109">If your application targets .NET Framework 4.6.1 or earlier and is running on the .NET Framework 4.6.2 or later and you want this change enabled, you can set the compatibility switch to `false` by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| <span data-ttu-id="86d37-110">name</span><span class="sxs-lookup"><span data-stu-id="86d37-110">Name</span></span>    | <span data-ttu-id="86d37-111">Wert</span><span class="sxs-lookup"><span data-stu-id="86d37-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="86d37-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="86d37-112">Scope</span></span>   | <span data-ttu-id="86d37-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="86d37-113">Edge</span></span>        |
| <span data-ttu-id="86d37-114">Version</span><span class="sxs-lookup"><span data-stu-id="86d37-114">Version</span></span> | <span data-ttu-id="86d37-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="86d37-115">4.6.2</span></span>       |
| <span data-ttu-id="86d37-116">Typ</span><span class="sxs-lookup"><span data-stu-id="86d37-116">Type</span></span>    | <span data-ttu-id="86d37-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="86d37-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="86d37-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="86d37-118">Affected APIs</span></span>

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
