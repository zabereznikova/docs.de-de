---
ms.openlocfilehash: 5844dbc2c3c89baeb39b69f16846f92ac10e97f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804604"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>Die XSD-Schemaüberprüfung erkennt jetzt Verstöße gegen eindeutige Einschränkungen richtig, wenn Verbundschlüssel verwendet werden und ein Schlüssel leer ist

|   |   |
|---|---|
|Details|Versionen von .NET Framework vor 4.6 wiesen einen Fehler auf, der dazu geführt hat, dass die XSD-Validierung eindeutige Einschränkungen für Verbundschlüssel nicht erkannt hat, wenn einer der Schlüssel leer war. Dieses Problem wurde in .NET Framework 4.6 behoben. Dies führt zu einwandfreieren Validierung, aber möglicherweise auch dazu, dass einige XML-Daten nicht überprüft werden, die zuvor überprüft wurden.|
|Vorschlag|Wenn eine weniger strenge Überprüfung für .NET Framework 4.0 erforderlich ist, kann die überprüfende Anwendung auf Version 4.5 (oder niedriger) von .NET Framework ausgerichtet werden. Wenn eine Neuausrichtung auf .NET Framework 4.6 erfolgt, sollte jedoch eine Code Review erfolgen, um sicherzustellen, dass die Validierung doppelter Verbundschlüssel (wie in dieser Problembeschreibung erläutert) nicht erwartet wird.|
|`Scope`|Edge|
|Version|4.6|
|Geben Sie Folgendes ein:|Neuzuweisung|
