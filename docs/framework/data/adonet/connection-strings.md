---
title: Verbindungszeichenfolgen in ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd787373b869c31727cfc0d027b6b98774b0d630
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="connection-strings-in-adonet"></a>Verbindungszeichenfolgen in ADO.NET
.NET Framework 2.0 führte neue Funktionen zum Arbeiten mit Verbindungszeichenfolgen ein. So wurden z. B. die Klassen des Verbindungszeichenfolgen-Generators um neue Schlüsselwörter erweitert, sodass gültige Verbindungszeichenfolgen zur Laufzeit erstellt werden können.  
  
 Eine Verbindungszeichenfolge enthält Initialisierungsinformationen, die als Parameter von einem Datenanbieter an eine Datenquelle übergeben werden. Die Syntax ist abhängig vom Datenanbieter, und die Verbindungszeichenfolge wird beim Versuch analysiert, eine Verbindung herzustellen. Syntaxfehler generieren eine Laufzeitausnahme, aber andere Fehler treten erst auf, nachdem die Datenquelle die Verbindungsinformationen empfangen hat. Nach erfolgter Validierung übernimmt die Datenquelle die in der Verbindungszeichenfolge angegebenen Optionen und öffnet die Verbindung.  
  
 Das Format einer Verbindungszeichenfolge besteht aus einer durch Semikolons getrennten Liste mit Schlüssel-Wert-Parameterpaaren:  
  
 `keyword1=value; keyword2=value;`  
  
 Bei den Schlüsselwörtern spielt die Groß- und Kleinschreibung keine Rolle, und Leerzeichen zwischen den Schlüssel-Wert-Paaren werden ignoriert. Je nach Datenquelle muss aber bei den Werten u. U. auf die Groß- und Kleinschreibung geachtet werden. Alle Werte, die ein Semikolon, ein einfaches oder ein doppeltes Anführungszeichen enthalten, müssen in doppelte Anführungszeichen eingeschlossen werden.  
  
 Die Syntax für gültige Verbindungszeichenfolgen ist anbieterabhängig und hat sich über die Jahre hinweg aus früheren APIs, wie ODBC, entwickelt. Der .NET Framework-Datenanbieter für SQL Server (SqlClient) enthält eine Vielzahl von Elementen aus älterer Syntax und zeigt sich in der Regel bei einer allgemeinen Verbindungszeichenfolgensyntax flexibler. Für viele Elemente der Verbindungszeichenfolgensyntax gibt es mehrere gültige Synonyme, aber einige Syntax- und Rechtschreibfehler können zu Problemen führen. So ist z. B. `Integrated Security=true` gültig, wohingegen `IntegratedSecurity=true` zu einem Fehler führt. Außerdem können Verbindungszeichenfolgen, die zur Laufzeit aus nicht validierten Benutzereingaben konstruiert werden, zu Angriffen durch Einschleusung von Zeichenfolgen führen und so die Sicherheit der Datenquelle gefährden.  
  
 Zur Beseitigung dieser Probleme gibt es in ADO.NET 2.0 neue Verbindungszeichenfolgen-Generatoren für die einzelnen .NET Framework-Datenanbieter. Schlüsselwörter werden als Eigenschaften verfügbar gemacht, wodurch die Syntax der Verbindungszeichenfolge validiert werden kann, bevor sie an die Datenquelle übermittelt wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verbindungszeichenfolgen-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 Zeigt, wie mit den `ConnectionStringBuilder`-Klassen gültige Verbindungszeichenfolgen zur Laufzeit erstellt werden können.  
  
 [Verbindungszeichenfolgen und Konfigurationsdateien](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 Zeigt, wie Verbindungszeichenfolgen in Konfigurationsdateien gespeichert und abgerufen werden können.  
  
 [Syntax für Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 Beschreibt das Konfigurieren anbieterspezifischer Verbindungszeichenfolgen für `SqlClient`, `OracleClient`, `OleDb` und `Odbc`.  
  
 [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 Demonstriert Verfahren zum Schützen von Informationen, die beim Herstellen von Verbindungen mit einer Datenquelle verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufbauen der Verbindung zu einer Datenquelle](/cpp/data/odbc/connecting-to-a-data-source)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
