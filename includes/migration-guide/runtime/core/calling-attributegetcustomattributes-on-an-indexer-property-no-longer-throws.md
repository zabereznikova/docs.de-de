---
ms.openlocfilehash: f61e5670334f4d3674fd0b008d1a476b14c7ba4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497686"
---
### <a name="calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>Der Aufruf von Attribute.GetCustomAttributes für eine Indexereigenschaft löst keine AmbiguousMatchException-Ausnahme mehr aus, wenn die Mehrdeutigkeit durch den Typ des Indexes aufgelöst werden kann

#### <a name="details"></a>Details

Vor .NET Framework 4.6 führte der Aufruf von <code>GetCustomAttribute(s)</code> für eine Indexereigenschaft, die sich nur durch den Indextyp von einer anderen Eigenschaft unterschied, zu einer <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>. Ab .NET Framework 4.6 werden die Attribute der Eigenschaft ordnungsgemäß zurückgegeben.

#### <a name="suggestion"></a>Vorschlag

Beachten Sie, dass „GetCustomAttribute(s)“ jetzt häufiger funktioniert. Wenn sich eine App zuvor auf <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName> verlassen hat, sollte jetzt die Reflektion verwendet werden, um stattdessen explizit nach mehreren Indexern zu suchen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

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
