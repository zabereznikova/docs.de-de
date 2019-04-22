---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774323"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a>List\<T>.ForEach kann beim Ändern eines Listenelements eine Ausnahme auslösen

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 löst ein <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})>-Enumerator eine <xref:System.InvalidOperationException?displayProperty=name>-Ausnahme aus, wenn ein Element in der aufrufenden Sammlung geändert wird. Zuvor hätte dies keine Ausnahme ausgelöst, aber zu Racebedingungen geführt.|
|Vorschlag|Im Idealfall sollte der Code unveränderlich sein, damit Listen nicht geändert werden, während ihre Elemente aufgezählt werden, da dies nie ein sicherer Vorgang ist. Eine App kann auf .NET Framework 4.0 ausgelegt werden, um zum vorherigen Verhalten zurückzukehren.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
