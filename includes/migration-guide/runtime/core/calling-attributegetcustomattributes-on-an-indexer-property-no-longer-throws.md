---
ms.openlocfilehash: 34093fd8c47049a0bd59020228043c06035af421
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621294"
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
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li></ul>|
