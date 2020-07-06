---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617218"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a>List&lt;T&gt;.ForEach kann beim Ändern eines Listenelements eine Ausnahme auslösen

#### <a name="details"></a>Details

Ab .NET Framework 4.5 löst ein <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})>-Enumerator eine <xref:System.InvalidOperationException?displayProperty=fullName>-Ausnahme aus, wenn ein Element in der aufrufenden Sammlung geändert wird. Zuvor hätte dies keine Ausnahme ausgelöst, aber zu Racebedingungen geführt.

#### <a name="suggestion"></a>Vorschlag

Im Idealfall sollte der Code unveränderlich sein, damit Listen nicht geändert werden, während ihre Elemente aufgezählt werden, da dies nie ein sicherer Vorgang ist. Eine App kann auf .NET Framework 4.0 ausgelegt werden, um zum vorherigen Verhalten zurückzukehren.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.5         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>
