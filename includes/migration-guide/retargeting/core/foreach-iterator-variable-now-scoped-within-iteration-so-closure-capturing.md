---
ms.openlocfilehash: 1805c26f1eff46719f30de8a14ca6d35f01948a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234756"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>Der Gültigkeitsbereich der Foreach-Iteratorvariable ist jetzt auf die Iteration beschränkt, weswegen sich die Semantik für die Abschlusserfassung (in C# 5) unterscheidet

|   |   |
|---|---|
|Details|Ab C# 5 (Visual Studio 2012) ist der Gültigkeitsbereich von <code>foreach</code>-Iteratorvariablen auf die Iteration beschränkt. Dies kann zu Fehlern führen, wenn der Code zuvor davon abhängig war, dass die Variablen nicht in den <code>foreach</code>-Abschluss einbezogen wurden. Diese Änderung führt dazu, dass eine an einen Delegaten übergebene Iteratorvariable als der Wert behandelt wird, den sie zum Zeitpunkt der Erstellung des Delegaten aufwies, anstatt sie als den Wert zu behandeln, den sie zum Zeitpunkt aufwies, als der Delegat aufgerufen wurde.|
|Vorschlag|Idealerweise sollte der Code aktualisiert werden, um das neue Compilerverhalten zu erwarten. Wenn die alte Semantik erforderlich ist, kann die Iteratorvariable durch eine separate Variable ersetzt werden, die explizit außerhalb des Gültigkeitsbereichs der Schleife platziert wird.|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Neuzuweisung|
