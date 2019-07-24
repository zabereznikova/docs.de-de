---
title: Verbindungszeichenfolgen in ADO.NET
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 02fe8d984f1287673477bb142b3f9626e248898e
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363747"
---
# <a name="connection-strings-in-adonet"></a>Verbindungszeichenfolgen in ADO.NET

Eine Verbindungszeichenfolge enthält Initialisierungsinformationen, die als Parameter von einem Datenanbieter an eine Datenquelle übergeben werden. Der Datenanbieter empfängt die Verbindungs Zeichenfolge als Wert <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> der-Eigenschaft. Der Anbieter analysiert die Verbindungs Zeichenfolge und stellt sicher, dass die Syntax korrekt ist und dass die Schlüsselwörter unterstützt werden. Anschließend übergibt <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> die-Methode die analysierten Verbindungsparameter an die Datenquelle. Die Datenquelle führt eine weitere Validierung durch und stellt eine Verbindung her.

## <a name="connection-string-syntax"></a>Verbindungs Zeichen folgen Syntax

Eine Verbindungs Zeichenfolge ist eine durch Semikolons getrennte Liste von Schlüssel-Wert-Parameter Paaren:

```
keyword1=value; keyword2=value;
```

Bei Schlüsselwörtern wird Groß-/Kleinschreibung nicht beachtet. Bei Werten kann jedoch abhängig von der Datenquelle die Groß-/Kleinschreibung beachtet werden. Sowohl Schlüsselwörter als auch Werte können [Leerzeichen](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)enthalten. Führende und nachfolgende Leerzeichen werden in Schlüsselwörtern und Werten ohne Anführungszeichen ignoriert.

Wenn ein Wert das Semikolon oder [Unicode-Steuerzeichen](https://en.wikipedia.org/wiki/Unicode_control_characters)oder führende oder nachfolgende Leerzeichen enthält, muss er in einfache oder doppelte Anführungszeichen eingeschlossen werden. Beispiel:

```
Keyword=" whitespace  ";
Keyword='special;character';
```

Das einschließende Zeichen darf nicht innerhalb des umschließenden Werts auftreten. Daher kann ein Wert, der einfache Anführungszeichen enthält, nur in doppelte Anführungszeichen eingeschlossen werden und umgekehrt:

```
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

Sie können das einschließende Zeichen auch mit Escapezeichen versehen, indem Sie zwei davon verwenden:

```
Keyword="double""quotation";
Keyword='single''quotation';
```

Die Anführungszeichen selbst und das Gleichheitszeichen erfordern keinen Escapezeichen, sodass die folgenden Verbindungs Zeichenfolgen gültig sind:

```
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

Da jeder Wert bis zum nächsten Semikolon oder Ende der Zeichenfolge gelesen wird, ist `a=b=c`der Wert im letzteren Beispiel, und das abschließende Semikolon ist optional.

Alle Verbindungs Zeichenfolgen haben dieselbe grundlegende Syntax, die oben beschrieben wird. Der Satz der erkannten Schlüsselwörter hängt jedoch vom Anbieter ab und hat sich über die Jahre von früheren APIs wie *ODBC*entwickelt. Der *.NET Framework* -Datenanbieter  für SQL Server`SqlClient`() unterstützt viele Schlüsselwörter aus älteren APIs, ist jedoch im Allgemeinen flexibler und akzeptiert Synonyme für viele der allgemeinen Schlüsselwörter der Verbindungs Zeichenfolge.

Das Eingeben von Fehlern kann zu Fehlern führen. Beispielsweise `Integrated Security=true` ist gültig `IntegratedSecurity=true` , verursacht jedoch einen Fehler.

Verbindungs Zeichenfolgen, die zur Laufzeit von nicht validierten Benutzereingaben manuell erstellt werden, sind anfällig für Angriffe durch Zeichen folgen Injektion und gefährden die Sicherheit in der Datenquelle. Um diese Probleme zu beheben, wurden von *ADO.net* 2,0 [Verbindungs](../../../../docs/framework/data/adonet/connection-string-builders.md) Zeichenfolgen-Generatoren für jeden *.NET Framework* -Datenanbieter eingeführt. Diese Verbindungs Zeichenfolgen-Generatoren machen Parameter als stark typisierte Eigenschaften verfügbar und ermöglichen es, die Verbindungs Zeichenfolge zu validieren, bevor Sie an die Datenquelle gesendet wird.

## <a name="in-this-section"></a>In diesem Abschnitt

[Verbindungs Zeichen folgen-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md)\
Zeigt, wie mit den `ConnectionStringBuilder`-Klassen gültige Verbindungszeichenfolgen zur Laufzeit erstellt werden können.

[Verbindungs Zeichenfolgen und Konfigurationsdateien](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\
Zeigt, wie Verbindungszeichenfolgen in Konfigurationsdateien gespeichert und abgerufen werden können.

[Verbindungs Zeichen folgen Syntax](../../../../docs/framework/data/adonet/connection-string-syntax.md)\
Beschreibt das Konfigurieren anbieterspezifischer Verbindungszeichenfolgen für `SqlClient`, `OracleClient`, `OleDb` und `Odbc`.

[Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md)\
Demonstriert Verfahren zum Schützen von Informationen, die beim Herstellen von Verbindungen mit einer Datenquelle verwendet werden.

## <a name="see-also"></a>Siehe auch

- [Aufbauen der Verbindung zu einer Datenquelle](/cpp/data/odbc/connecting-to-a-data-source)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
