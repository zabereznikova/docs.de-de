---
ms.openlocfilehash: f61e5670334f4d3674fd0b008d1a476b14c7ba4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497686"
---
### <a name="calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a><span data-ttu-id="eeb38-101">Der Aufruf von Attribute.GetCustomAttributes für eine Indexereigenschaft löst keine AmbiguousMatchException-Ausnahme mehr aus, wenn die Mehrdeutigkeit durch den Typ des Indexes aufgelöst werden kann</span><span class="sxs-lookup"><span data-stu-id="eeb38-101">Calling Attribute.GetCustomAttributes on an indexer property no longer throws AmbiguousMatchException if the ambiguity can be resolved by index's type</span></span>

#### <a name="details"></a><span data-ttu-id="eeb38-102">Details</span><span class="sxs-lookup"><span data-stu-id="eeb38-102">Details</span></span>

<span data-ttu-id="eeb38-103">Vor .NET Framework 4.6 führte der Aufruf von <code>GetCustomAttribute(s)</code> für eine Indexereigenschaft, die sich nur durch den Indextyp von einer anderen Eigenschaft unterschied, zu einer <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="eeb38-103">Prior to the .NET Framework 4.6, calling <code>GetCustomAttribute(s)</code> on an indexer property which differed from another property only by the type of the index would result in an <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>.</span></span> <span data-ttu-id="eeb38-104">Ab .NET Framework 4.6 werden die Attribute der Eigenschaft ordnungsgemäß zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eeb38-104">Beginning in the .NET Framework 4.6, the property's attributes will be correctly returned.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eeb38-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="eeb38-105">Suggestion</span></span>

<span data-ttu-id="eeb38-106">Beachten Sie, dass „GetCustomAttribute(s)“ jetzt häufiger funktioniert.</span><span class="sxs-lookup"><span data-stu-id="eeb38-106">Be aware that GetCustomAttribute(s) will work more frequently now.</span></span> <span data-ttu-id="eeb38-107">Wenn sich eine App zuvor auf <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName> verlassen hat, sollte jetzt die Reflektion verwendet werden, um stattdessen explizit nach mehreren Indexern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="eeb38-107">If an app was previously relying on the <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>, reflection should now be used to explicitly look for multiple indexers, instead.</span></span>

| <span data-ttu-id="eeb38-108">name</span><span class="sxs-lookup"><span data-stu-id="eeb38-108">Name</span></span>    | <span data-ttu-id="eeb38-109">Wert</span><span class="sxs-lookup"><span data-stu-id="eeb38-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eeb38-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="eeb38-110">Scope</span></span>   |<span data-ttu-id="eeb38-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eeb38-111">Edge</span></span>|
|<span data-ttu-id="eeb38-112">Version</span><span class="sxs-lookup"><span data-stu-id="eeb38-112">Version</span></span>|<span data-ttu-id="eeb38-113">4.6</span><span class="sxs-lookup"><span data-stu-id="eeb38-113">4.6</span></span>|
|<span data-ttu-id="eeb38-114">Typ</span><span class="sxs-lookup"><span data-stu-id="eeb38-114">Type</span></span>|<span data-ttu-id="eeb38-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="eeb38-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="eeb38-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="eeb38-116">Affected APIs</span></span>

- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo,System.Boolean)``
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo,System.Boolean)``

-->
