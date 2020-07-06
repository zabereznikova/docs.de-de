---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616129"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>Die bidirektionale Datenbindung an eine Eigenschaft mit einem nicht öffentlichen Setter wird nicht unterstützt

#### <a name="details"></a>Details

Der Versuch, Daten ohne einen öffentlichen Setter an eine Eigenschaft zu binden, wurde nie unterstützt. Ab .NET Framework 4.5.1 löst dieses Szenario <xref:System.InvalidOperationException?displayProperty=fullName> aus. Beachten Sie, dass diese neue Ausnahme nur für Apps ausgelöst wird, die speziell auf .NET Framework 4.5.1 abzielen. Wenn eine App auf .NET Framework 4.5 ausgerichtet ist, wird der Aufruf zugelassen. Wenn die App nicht auf eine bestimmte Version von .NET Framework ausgerichtet ist, wird die Bindung als unidirektionale Bindung behandelt.

#### <a name="suggestion"></a>Vorschlag

Die App sollte aktualisiert werden, um entweder die unidirektionale Bindung zu verwenden oder den Setter der Eigenschaft öffentlich zur Verfügung zu stellen. Alternativ können Sie die App auf .NET Framework 4.5 ausrichten, um das alte Verhalten zu erreichen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>
