---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621330"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="10e43-101">Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden</span><span class="sxs-lookup"><span data-stu-id="10e43-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="10e43-102">Details</span><span class="sxs-lookup"><span data-stu-id="10e43-102">Details</span></span>

<span data-ttu-id="10e43-103">Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="10e43-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="10e43-104">Die folgenden Typen sind betroffen:</span><span class="sxs-lookup"><span data-stu-id="10e43-104">The following types are affected:</span></span><ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><span data-ttu-id="10e43-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (und die abgeleiteten Typen, einschließlich <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> und <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span><span class="sxs-lookup"><span data-stu-id="10e43-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span></li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><span data-ttu-id="10e43-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="10e43-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span></span></li></ul><span data-ttu-id="10e43-107">Aufrufe von <code>IMarshal</code> für das Objekt geben <code>E_NOINTERFACE</code> zurück.</span><span class="sxs-lookup"><span data-stu-id="10e43-107">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="10e43-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="10e43-108">Suggestion</span></span>

<span data-ttu-id="10e43-109">Aktualisieren Sie den Marshallingcode, damit dieser mit Nicht-Reflection-Objekten arbeitet.</span><span class="sxs-lookup"><span data-stu-id="10e43-109">Update marshaling code to work with non-reflection objects</span></span>

| <span data-ttu-id="10e43-110">name</span><span class="sxs-lookup"><span data-stu-id="10e43-110">Name</span></span>    | <span data-ttu-id="10e43-111">Wert</span><span class="sxs-lookup"><span data-stu-id="10e43-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="10e43-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="10e43-112">Scope</span></span>   |<span data-ttu-id="10e43-113">Gering</span><span class="sxs-lookup"><span data-stu-id="10e43-113">Minor</span></span>|
|<span data-ttu-id="10e43-114">Version</span><span class="sxs-lookup"><span data-stu-id="10e43-114">Version</span></span>|<span data-ttu-id="10e43-115">4.6</span><span class="sxs-lookup"><span data-stu-id="10e43-115">4.6</span></span>|
|<span data-ttu-id="10e43-116">Typ</span><span class="sxs-lookup"><span data-stu-id="10e43-116">Type</span></span>|<span data-ttu-id="10e43-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="10e43-117">Runtime</span></span>|
