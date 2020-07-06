---
ms.openlocfilehash: 9a2d6a25a8ab1b8bf65b947557802e0805a7f826
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617202"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>Der Gültigkeitsbereich der Foreach-Iteratorvariable ist jetzt auf die Iteration beschränkt, weswegen sich die Semantik für die Abschlusserfassung (in C# 5) unterscheidet

#### <a name="details"></a>Details

Ab C# 5 (Visual Studio 2012) ist der Gültigkeitsbereich von `foreach`-Iteratorvariablen auf die Iteration beschränkt. Dies kann zu Fehlern führen, wenn der Code zuvor davon abhängig war, dass die Variablen nicht in den `foreach`-Abschluss einbezogen wurden. Diese Änderung führt dazu, dass eine an einen Delegaten übergebene Iteratorvariable als der Wert behandelt wird, den sie zum Zeitpunkt der Erstellung des Delegaten aufwies, anstatt sie als den Wert zu behandeln, den sie zum Zeitpunkt aufwies, als der Delegat aufgerufen wurde.

#### <a name="suggestion"></a>Vorschlag

Idealerweise sollte der Code aktualisiert werden, um das neue Compilerverhalten zu erwarten. Wenn die alte Semantik erforderlich ist, kann die Iteratorvariable durch eine separate Variable ersetzt werden, die explizit außerhalb des Gültigkeitsbereichs der Schleife platziert wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.5         |
| Typ    | Neuzuweisung |
