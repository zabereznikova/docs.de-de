---
ms.openlocfilehash: 150882f3e4c9ff7abe811e09da94b8141de75778
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366852"
---
### <a name="exclude-specific-types-and-their-derived-types"></a>Bestimmte Typen und deren abgeleitete Typen ausschließen

Sie können bestimmte Typen und deren abgeleitete Typen aus der Analyse ausschließen. Um z. b. anzugeben, dass die Regel nicht für Methoden innerhalb von Typen mit dem Namen `MyType` und den abgeleiteten Typen ausgeführt werden soll, fügen Sie das folgende Schlüssel-Wert-Paar zu einer *editorconfig* -Datei in Ihrem Projekt hinzu:

```ini
dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType
```

Zulässige Symbol namens Formate im Optionswert (durch getrennt `|` ):

- Nur Typname (schließt alle Typen mit dem Namen ein, unabhängig vom enthaltenden Typ oder Namespace).
- Voll qualifizierte Namen im [Dokumentations-ID-Format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)des Symbols mit einem optionalen `T:` Präfix.

Beispiele:

| Optionswert | Zusammenfassung |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType` | Entspricht allen Typen `MyType` mit dem Namen und allen abgeleiteten Typen. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType1|MyType2` | Entspricht allen Typen `MyType1` `MyType2` mit dem Namen oder und allen abgeleiteten Typen. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS.MyType` | Entspricht einem bestimmten Typ `MyType` mit dem angegebenen voll qualifizierten Namen und allen abgeleiteten Typen. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS1.MyType1|M:NS2.MyType2` | Vergleicht bestimmte Typen `MyType1` und `MyType2` mit den jeweiligen voll qualifizierten Namen und allen abgeleiteten Typen. |
