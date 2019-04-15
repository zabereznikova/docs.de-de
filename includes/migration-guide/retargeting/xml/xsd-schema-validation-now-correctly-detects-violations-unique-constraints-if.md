---
ms.openlocfilehash: 5844dbc2c3c89baeb39b69f16846f92ac10e97f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234471"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>Die XSD-Schemaüberprüfung erkennt jetzt Verstöße gegen eindeutige Einschränkungen richtig, wenn Verbundschlüssel verwendet werden und ein Schlüssel leer ist

|   |   |
|---|---|
|Details|Versionen von .NET Framework vor 4.6 wiesen einen Fehler auf, der dazu geführt hat, dass die XSD-Validierung eindeutige Einschränkungen für Verbundschlüssel nicht erkannt hat, wenn einer der Schlüssel leer war. Dieses Problem wurde in .NET Framework 4.6 behoben. Dies führt zu einwandfreieren Validierung, aber möglicherweise auch dazu, dass einige XML-Daten nicht überprüft werden, die zuvor überprüft wurden.|
|Vorschlag|Wenn eine weniger strenge Überprüfung für .NET Framework 4.0 erforderlich ist, kann die überprüfende Anwendung auf Version 4.5 (oder niedriger) von .NET Framework ausgerichtet werden. Wenn eine Neuausrichtung auf .NET Framework 4.6 erfolgt, sollte jedoch eine Code Review erfolgen, um sicherzustellen, dass die Validierung doppelter Verbundschlüssel (wie in dieser Problembeschreibung erläutert) nicht erwartet wird.|
|Bereich|Microsoft Edge|
|Version|4.6|
|Typ|Neuzuweisung|
