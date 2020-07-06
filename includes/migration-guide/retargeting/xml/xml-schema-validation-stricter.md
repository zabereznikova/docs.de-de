---
ms.openlocfilehash: 4a22d78f2308aab544d7a7d2e4d05ddc1ad5457d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617239"
---
### <a name="xml-schema-validation-is-stricter"></a>Die XML-Schemaüberprüfung ist genauer

#### <a name="details"></a>Details

In .NET Framework 4.5 ist die XML-Schemaüberprüfung genauer. Wenn Sie xsd:anyURI verwenden, um einen URI wie ein mailto-Protokoll zu überprüfen, tritt bei der Validierung ein Fehler auf, wenn der URI Leerzeichen enthält. In früheren Versionen von .NET Framework war die Validierung erfolgreich. Die Änderung betrifft nur Anwendungen, die auf .NET Framework 4.5 ausgerichtet sind.

#### <a name="suggestion"></a>Vorschlag

Wenn eine weniger genaue Überprüfung für .NET Framework 4.0 erforderlich ist, kann die überprüfende Anwendung auf Version 4.0 von .NET Framework ausgerichtet werden. Bei einer Neuausrichtung auf .NET Framework 4.5 sollte jedoch ein Code Review erfolgen, um sicherzustellen, dass ungültige URIs (mit Leerzeichen) nicht als Attributwerte mit dem Datentyp „anyURI“ erwartet werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5         |
| Typ    | Neuzuweisung |
