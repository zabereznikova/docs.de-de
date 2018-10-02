---
title: Verbindungszeichenfolgen in ADO.NET
ms.date: 03/30/2017
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 1e6e2b6870195c99279639e1f4576a30b7126d4d
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48029390"
---
# <a name="connection-strings-in-adonet"></a>Verbindungszeichenfolgen in ADO.NET
.NET Framework 2.0 führte neue Funktionen zum Arbeiten mit Verbindungszeichenfolgen ein. So wurden z. B. die Klassen des Verbindungszeichenfolgen-Generators um neue Schlüsselwörter erweitert, sodass gültige Verbindungszeichenfolgen zur Laufzeit erstellt werden können.  
  
Eine Verbindungszeichenfolge enthält Initialisierungsinformationen, die als Parameter von einem Datenanbieter an eine Datenquelle übergeben werden. Die Syntax ist abhängig vom Datenanbieter, und die Verbindungszeichenfolge wird beim Versuch analysiert, eine Verbindung herzustellen. Syntaxfehler generieren eine Laufzeitausnahme, aber andere Fehler treten erst auf, nachdem die Datenquelle die Verbindungsinformationen empfangen hat. Nach erfolgter Validierung übernimmt die Datenquelle die in der Verbindungszeichenfolge angegebenen Optionen und öffnet die Verbindung.
  
Das Format einer Verbindungszeichenfolge besteht aus einer durch Semikolons getrennten Liste mit Schlüssel-Wert-Parameterpaaren:
  
    keyword1=value; keyword2=value;
  
Schlüsselwörter sind nicht in der Groß-/Kleinschreibung beachtet. Werte, möglicherweise jedoch Groß-/Kleinschreibung beachtet, abhängig von der Datenquelle. Sowohl Schlüsselwörtern und Werten enthalten möglicherweise [aus Whitespace bestehenden Zeichen](https://en.wikipedia.org/wiki/Whitespace_character#Unicode), obwohl führende und nachfolgende Leerzeichen werden, Schlüsselwörter ignoriert und ohne Anführungszeichen Werte.

Wenn Sie einen Wert enthält, Semikolon, [Unicode-Steuerzeichen](https://en.wikipedia.org/wiki/Unicode_control_characters), führende oder nachfolgende Leerzeichen, Sie z. B. in einfache oder doppelte Anführungszeichen eingeschlossen werden müssen:

    Keyword=" whitespace  ";
    Keyword='special;character';

Die umschließende Zeichen kann nicht im Wert auftreten, die eingeschlossen. Aus diesem Grund kann ein Wert mit einfachen Anführungszeichen eingeschlossen werden, nur in doppelte Anführungszeichen und umgekehrt:

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

Die Anführungszeichen selbst als auch das Gleichheitszeichen erfordern Escapezeichen, keine daher die folgenden Verbindungszeichenfolgen gelten:

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

Da jeder Wert bis zum nächsten Semikolon oder dem Ende der Zeichenfolge gelesen wird, wird der Wert im zweiten Beispiel `a=b=c`, und das letzte Semikolon ist optional.

Die Syntax für gültige Verbindungszeichenfolgen ist anbieterabhängig und hat sich über die Jahre hinweg aus früheren APIs, wie ODBC, entwickelt. Der .NET Framework-Datenanbieter für SQL Server (SqlClient) enthält eine Vielzahl von Elementen aus älterer Syntax und zeigt sich in der Regel bei einer allgemeinen Verbindungszeichenfolgensyntax flexibler. Für viele Elemente der Verbindungszeichenfolgensyntax gibt es mehrere gültige Synonyme, aber einige Syntax- und Rechtschreibfehler können zu Problemen führen. So ist z. B. `Integrated Security=true` gültig, wohingegen `IntegratedSecurity=true` zu einem Fehler führt. Außerdem können Verbindungszeichenfolgen, die zur Laufzeit aus nicht validierten Benutzereingaben konstruiert werden, zu Angriffen durch Einschleusung von Zeichenfolgen führen und so die Sicherheit der Datenquelle gefährden.
  
Zur Beseitigung dieser Probleme gibt es in ADO.NET 2.0 neue Verbindungszeichenfolgen-Generatoren für die einzelnen .NET Framework-Datenanbieter. Schlüsselwörter werden als Eigenschaften verfügbar gemacht, wodurch die Syntax der Verbindungszeichenfolge validiert werden kann, bevor sie an die Datenquelle übermittelt wird.
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verbindungszeichenfolgengeneratoren](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 Zeigt, wie mit den `ConnectionStringBuilder`-Klassen gültige Verbindungszeichenfolgen zur Laufzeit erstellt werden können.
  
 [Verbindungszeichenfolgen und Konfigurationsdateien](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 Zeigt, wie Verbindungszeichenfolgen in Konfigurationsdateien gespeichert und abgerufen werden können.
  
 [Verbindungszeichenfolgensyntax](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 Beschreibt das Konfigurieren anbieterspezifischer Verbindungszeichenfolgen für `SqlClient`, `OracleClient`, `OleDb` und `Odbc`.
  
 [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 Demonstriert Verfahren zum Schützen von Informationen, die beim Herstellen von Verbindungen mit einer Datenquelle verwendet werden.
  
## <a name="see-also"></a>Siehe auch  
 [Aufbauen der Verbindung zu einer Datenquelle](/cpp/data/odbc/connecting-to-a-data-source)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
