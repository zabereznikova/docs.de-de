---
title: Verbindungszeichenfolgen in ADO.NET
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 078fdab257115296f9ff00330265cb14ff8674c8
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50409456"
---
# <a name="connection-strings-in-adonet"></a>Verbindungszeichenfolgen in ADO.NET

Eine Verbindungszeichenfolge enthält Initialisierungsinformationen, die als Parameter von einem Datenanbieter an eine Datenquelle übergeben werden. Der Datenanbieter empfängt die Verbindungszeichenfolge als Wert für die <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> Eigenschaft. Der Anbieter die Verbindungszeichenfolge analysiert, und es wird sichergestellt, dass die Syntax richtig ist und die Schlüsselwörter unterstützt werden. Die <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> Methode übergibt die analysierten Verbindungsparameter an die Datenquelle. Die Datenquelle weiter überprüft und stellt eine Verbindung her.

## <a name="connection-string-syntax"></a>Syntax für Verbindungszeichenfolgen

Eine Verbindungszeichenfolge ist eine durch Semikolons getrennte Liste von Schlüssel/Wert-Parameterpaaren:
  
    keyword1=value; keyword2=value;
  
Schlüsselwörter sind nicht in der Groß-/Kleinschreibung beachtet. Werte, möglicherweise jedoch Groß-/Kleinschreibung beachtet, abhängig von der Datenquelle. Sowohl Schlüsselwörtern und Werten enthalten möglicherweise [aus Whitespace bestehenden Zeichen](https://en.wikipedia.org/wiki/Whitespace_character#Unicode). Führende und nachfolgende Leerzeichen ignoriert werden, Schlüsselwörter und ohne Anführungszeichen Werte.

Wenn Sie einen Wert enthält, Semikolon, [Unicode-Steuerzeichen](https://en.wikipedia.org/wiki/Unicode_control_characters), oder führende oder nachfolgende Leerzeichen, muss er in einfache oder doppelte Anführungszeichen eingeschlossen werden. Zum Beispiel:

    Keyword=" whitespace  ";
    Keyword='special;character';

Die umschließende Zeichen kann nicht im Wert auftreten, die eingeschlossen. Aus diesem Grund kann ein Wert mit einfachen Anführungszeichen eingeschlossen werden, nur in doppelte Anführungszeichen (und umgekehrt):

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

Die Anführungszeichen selbst als auch das Gleichheitszeichen erfordern Escapezeichen, keine daher die folgenden Verbindungszeichenfolgen gelten:

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

Da jeder Wert bis zum nächsten Semikolon oder dem Ende der Zeichenfolge gelesen wird, wird der Wert im zweiten Beispiel `a=b=c`, und das letzte Semikolon ist optional.

Alle Verbindungszeichenfolgen verwenden die gleiche grundlegende Syntax, die oben beschriebenen. Die erkannten Schlüsselwörter allerdings hängt von dem Anbieter und hat im Lauf der Jahre aus früheren APIs, wie z. B. entwickelt *ODBC*. Die *.NET Framework* -Datenanbieter für *SQL Server* (`SqlClient`) unterstützt viele Schlüsselwörter aus ältere APIs aber ist in der Regel eine flexiblere und akzeptiert Sie Synonyme für viele allgemeine Verbindungszeichenfolge Schlüsselwörter.

Eingeben der Fehler kann Fehler verursachen. Z. B. `Integrated Security=true` gültig ist, aber `IntegratedSecurity=true` verursacht einen Fehler.

Verbindungszeichenfolgen, die manuell zur Laufzeit aus nicht validierten Benutzereingaben konstruiert sind anfällig für Zeichenfolge-Injection-Angriffen und Sicherheit in der Datenquelle gefährden. Um diesen schwierigkeiten *ADO.NET* 2.0 enthält [Verbindungszeichenfolgen-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md) für jede *.NET Framework* Datenanbieter. Diese Verbindungszeichenfolgen-Generatoren verfügbar machen Parameter als stark typisierte Eigenschaften, und Sie können sie die Verbindungszeichenfolge zu überprüfen, bevor sie mit der Datenquelle gesendet wird.

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
