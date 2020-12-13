---
ms.openlocfilehash: 83644b9205d650da68c910095dd1d22a14940c44
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366851"
---
### <a name="exclude-specific-symbols"></a>Bestimmte Symbole ausschließen

Sie können bestimmte Symbole, z. b. Typen und Methoden, von der Analyse ausschließen. Um z. b. anzugeben, dass die Regel nicht für Code innerhalb von Typen mit dem Namen ausgeführt `MyType` werden soll, fügen Sie das folgende Schlüssel-Wert-Paar in eine *Editor config* -Datei in Ihrem Projekt ein:

```ini
dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType
```

Zulässige Symbol namens Formate im Optionswert (durch getrennt `|` ):

- Nur Symbol Name (schließt alle Symbole mit dem Namen ein, unabhängig vom enthaltenden Typ oder Namespace).
- Voll qualifizierte Namen im [Dokumentations-ID-Format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)des Symbols. Jeder Symbol Name erfordert ein Symbol-Kind-Präfix, z `M:` . b. für Methoden, `T:` für Typen und `N:` für Namespaces.
- `.ctor` für Konstruktoren und `.cctor` für statische Konstruktoren.

Beispiele:

| Optionswert | Zusammenfassung |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType` | Entspricht allen Symbolen mit dem Namen `MyType` . |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType1|MyType2` | Entspricht allen Symbolen mit dem Namen `MyType1` oder `MyType2` . |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS.MyType.MyMethod(ParamType)` | Entspricht einer bestimmten Methode `MyMethod` mit der angegebenen voll qualifizierten Signatur. |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS1.MyType1.MyMethod1(ParamType)|M:NS2.MyType2.MyMethod2(ParamType)` | Entspricht bestimmten Methoden `MyMethod1` und `MyMethod2` mit den jeweiligen voll qualifizierten Signaturen. |
