---
title: Verbindungszeichenfolgen
description: Erfahren Sie mehr über Verbindungs Zeichenfolgen in ADO.net, die Initialisierungs Informationen enthalten, die als Parameter von einem Datenanbieter an eine Datenquelle übergeben werden.
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: baa6599a532746895cbb3920f2c623dd4c2be864
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287024"
---
# <a name="connection-strings-in-adonet"></a>Verbindungszeichenfolgen in ADO.NET

Eine Verbindungszeichenfolge enthält Initialisierungsinformationen, die als Parameter von einem Datenanbieter an eine Datenquelle übergeben werden. Der Datenanbieter empfängt die Verbindungs Zeichenfolge als Wert der- <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> Eigenschaft. Der Anbieter analysiert die Verbindungs Zeichenfolge und stellt sicher, dass die Syntax korrekt ist und dass die Schlüsselwörter unterstützt werden. Anschließend übergibt die- <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> Methode die analysierten Verbindungsparameter an die Datenquelle. Die Datenquelle führt eine weitere Validierung durch und stellt eine Verbindung her.

## <a name="connection-string-syntax"></a>Syntax von Verbindungszeichenfolgen

Eine Verbindungs Zeichenfolge ist eine durch Semikolons getrennte Liste von Schlüssel-Wert-Parameter Paaren:

```csharp
keyword1=value; keyword2=value;
```

Bei Schlüsselwörtern muss die Groß-/Kleinschreibung nicht beachtet werden. Bei Werten kann jedoch abhängig von der Datenquelle die Groß-/Kleinschreibung beachtet werden. Sowohl Schlüsselwörter als auch Werte können [Leerzeichen](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)enthalten. Führende und nachfolgende Leerzeichen werden in Schlüsselwörtern und Werten ohne Anführungszeichen ignoriert.

Wenn ein Wert das Semikolon oder [Unicode-Steuerzeichen](https://en.wikipedia.org/wiki/Unicode_control_characters)oder führende oder nachfolgende Leerzeichen enthält, muss er in einfache oder doppelte Anführungszeichen eingeschlossen werden. Beispiel:

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

Das einschließende Zeichen darf nicht innerhalb des umschließenden Werts auftreten. Daher kann ein Wert, der einfache Anführungszeichen enthält, nur in doppelte Anführungszeichen eingeschlossen werden und umgekehrt:

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

Sie können das einschließende Zeichen auch mit Escapezeichen versehen, indem Sie zwei davon verwenden:

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

Die Anführungszeichen selbst und das Gleichheitszeichen erfordern keinen Escapezeichen, sodass die folgenden Verbindungs Zeichenfolgen gültig sind:

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

Da jeder Wert bis zum nächsten Semikolon oder Ende der Zeichenfolge gelesen wird, ist der Wert im letzteren Beispiel `a=b=c` , und das abschließende Semikolon ist optional.

Alle Verbindungs Zeichenfolgen haben dieselbe grundlegende Syntax, die oben beschrieben wird. Der Satz der erkannten Schlüsselwörter hängt jedoch vom Anbieter ab und hat sich über die Jahre von früheren APIs wie *ODBC*entwickelt. Der *.NET Framework* -Datenanbieter für *SQL Server* ( `SqlClient` ) unterstützt viele Schlüsselwörter aus älteren APIs, ist jedoch im Allgemeinen flexibler und akzeptiert Synonyme für viele der allgemeinen Schlüsselwörter der Verbindungs Zeichenfolge.

Das Eingeben von Fehlern kann zu Fehlern führen. Beispielsweise `Integrated Security=true` ist gültig, verursacht jedoch `IntegratedSecurity=true` einen Fehler.

Verbindungs Zeichenfolgen, die zur Laufzeit von nicht validierten Benutzereingaben manuell erstellt werden, sind anfällig für Angriffe durch Zeichen folgen Injektion und gefährden die Sicherheit in der Datenquelle. Um diese Probleme zu beheben, wurden von *ADO.net* 2,0 [Verbindungs Zeichenfolgen](connection-string-builders.md) -Generatoren für jeden *.NET Framework* -Datenanbieter eingeführt. Diese Verbindungs Zeichenfolgen-Generatoren machen Parameter als stark typisierte Eigenschaften verfügbar und ermöglichen es, die Verbindungs Zeichenfolge zu validieren, bevor Sie an die Datenquelle gesendet wird.

## <a name="in-this-section"></a>In diesem Abschnitt

[Verbindungs Zeichen folgen-Generatoren](connection-string-builders.md)\
Zeigt, wie mit den `ConnectionStringBuilder`-Klassen gültige Verbindungszeichenfolgen zur Laufzeit erstellt werden können.

[Verbindungs Zeichenfolgen und Konfigurationsdateien](connection-strings-and-configuration-files.md)\
Zeigt, wie Verbindungszeichenfolgen in Konfigurationsdateien gespeichert und abgerufen werden können.

[Verbindungs Zeichen folgen Syntax](connection-string-syntax.md)\
Beschreibt das Konfigurieren anbieterspezifischer Verbindungszeichenfolgen für `SqlClient`, `OracleClient`, `OleDb` und `Odbc`.

[Schützen von Verbindungsinformationen](protecting-connection-information.md)\
Demonstriert Verfahren zum Schützen von Informationen, die beim Herstellen von Verbindungen mit einer Datenquelle verwendet werden.

## <a name="see-also"></a>Siehe auch

- [Herstellen der Verbindung mit einer Datenquelle](/cpp/data/odbc/connecting-to-a-data-source)
- [Übersicht über ADO.NET](ado-net-overview.md)
