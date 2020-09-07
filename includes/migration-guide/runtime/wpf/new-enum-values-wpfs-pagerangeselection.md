---
ms.openlocfilehash: 61749f59f9379a6d18bb013b2612a07cb7822b3a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496960"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a>Neue Enumerationswerte in der PageRangeSelection-Enumeration für WPF

#### <a name="details"></a>Details

Es wurden zwei neue Member (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> und <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) zur <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>-Enumeration hinzugefügt.

#### <a name="suggestion"></a>Vorschlag

In den meisten Fällen wirken sich diese Änderungen nicht auf Benutzercode aus. Code, der von einer bestimmten Anzahl von Elementen abhängig ist, die in <xref:System.Enum.GetNames(System.Type)>- oder <xref:System.Enum.GetValues(System.Type)>-Aufrufen für den <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>-Typ vorhanden sind, sollte jedoch geändert werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.PageRangeSelection`

-->
