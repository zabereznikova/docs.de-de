---
ms.openlocfilehash: f011f6ebe0fa85a59f3e69c93bba9eddc4c1689b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497348"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="4816d-101">Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden</span><span class="sxs-lookup"><span data-stu-id="4816d-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="4816d-102">Details</span><span class="sxs-lookup"><span data-stu-id="4816d-102">Details</span></span>

<span data-ttu-id="4816d-103">Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="4816d-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="4816d-104">Die folgenden Typen sind betroffen:</span><span class="sxs-lookup"><span data-stu-id="4816d-104">The following types are affected:</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <span data-ttu-id="4816d-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (und die abgeleiteten Typen, einschließlich <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> und <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span><span class="sxs-lookup"><span data-stu-id="4816d-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>

<span data-ttu-id="4816d-106">Aufrufe von <code>IMarshal</code> für das Objekt geben <code>E_NOINTERFACE</code> zurück.</span><span class="sxs-lookup"><span data-stu-id="4816d-106">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4816d-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4816d-107">Suggestion</span></span>

<span data-ttu-id="4816d-108">Aktualisieren Sie den Marshallingcode, sodass dieser auch mit Nichtreflexionsobjekten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="4816d-108">Update marshaling code to work with non-reflection objects.</span></span>

| <span data-ttu-id="4816d-109">Name</span><span class="sxs-lookup"><span data-stu-id="4816d-109">Name</span></span>    | <span data-ttu-id="4816d-110">Wert</span><span class="sxs-lookup"><span data-stu-id="4816d-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4816d-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="4816d-111">Scope</span></span>   |<span data-ttu-id="4816d-112">Gering</span><span class="sxs-lookup"><span data-stu-id="4816d-112">Minor</span></span>|
|<span data-ttu-id="4816d-113">Version</span><span class="sxs-lookup"><span data-stu-id="4816d-113">Version</span></span>|<span data-ttu-id="4816d-114">4.6</span><span class="sxs-lookup"><span data-stu-id="4816d-114">4.6</span></span>|
|<span data-ttu-id="4816d-115">Typ</span><span class="sxs-lookup"><span data-stu-id="4816d-115">Type</span></span>|<span data-ttu-id="4816d-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="4816d-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4816d-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4816d-117">Affected APIs</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.FieldInfo?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.MethodInfo?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>
- <xref:System.Reflection.TypeInfo?displayProperty=fullName>
- <xref:System.Type?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Reflection.Assembly`
- `T:System.Reflection.FieldInfo`
- `T:System.Reflection.MemberInfo`
- `T:System.Reflection.MethodBody`
- `T:System.Reflection.MethodInfo`
- `T:System.Reflection.Module`
- `T:System.Reflection.ParameterInfo`
- `T:System.Reflection.TypeInfo`
- `T:System.Type`

-->
