---
ms.openlocfilehash: c0a281b05f453b68495e6fa6fca45f3f36a204a3
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804604"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>Die XSD-Schemaüberprüfung erkennt jetzt Verstöße gegen eindeutige Einschränkungen richtig, wenn Verbundschlüssel verwendet werden und ein Schlüssel leer ist

|   |   |
|---|---|
|Details|Versionen von .NET Framework vor 4.6 wiesen einen Fehler auf, der dazu geführt hat, dass die XSD-Validierung eindeutige Einschränkungen für Verbundschlüssel nicht erkannt hat, wenn einer der Schlüssel leer war. Dieses Problem wurde in .NET Framework 4.6 behoben. Dies führt zu einwandfreieren Validierung, aber möglicherweise auch dazu, dass einige XML-Daten nicht überprüft werden, die zuvor überprüft wurden.|
|Vorschlag|Wenn eine weniger strenge Überprüfung für .NET Framework 4.0 erforderlich ist, kann die überprüfende Anwendung auf Version 4.5 (oder niedriger) von .NET Framework ausgerichtet werden. Wenn eine Neuausrichtung auf .NET Framework 4.6 erfolgt, sollte jedoch eine Code Review erfolgen, um sicherzustellen, dass die Validierung doppelter Verbundschlüssel (wie in dieser Problembeschreibung erläutert) nicht erwartet wird.|
|Bereich|Microsoft Edge|
|Version|4.6|
|Typ|Neuzuweisung|

