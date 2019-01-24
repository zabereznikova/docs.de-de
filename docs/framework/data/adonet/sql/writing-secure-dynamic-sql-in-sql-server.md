---
title: Schreiben von sicherem dynamischen SQL in SQL Server
ms.date: 03/30/2017
ms.assetid: df5512b0-c249-40d2-82f9-f9a2ce6665bc
ms.openlocfilehash: 446a9f6a49b376f04d1c82d45463d567d89116d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745609"
---
# <a name="writing-secure-dynamic-sql-in-sql-server"></a>Schreiben von sicherem dynamischen SQL in SQL Server
Die Einschleusung von SQL-Befehlen (SQL Injection-Angriff) ist eine Möglichkeit, Anwendungen anzugreifen. Dabei werden anstelle einer gültigen Eingabe Transact-SQL-Anweisungen in den Code eingeschleust. Wenn die Eingabe direkt und ohne Validierung an den Server weitergeleitet wird und die Anwendung den eingeschleusten Code ausführt, können Daten beschädigt oder sogar zerstört werden.  
  
 Alle Prozeduren, die SQL-Anweisungen konstruieren, sollten auf Schwachstellen überprüft werden, die die Einschleusung von SQL-Befehlen ermöglichen, da SQL Server alle syntaktisch gültigen Abfragen ungeprüft ausführt. Selbst parametrisierte Daten können von einem geschickten und entschlossenen Angreifer manipuliert werden. Bei Verwendung von dynamischem SQL sollten Sie Ihre Befehle unbedingt parametrisieren und auf keinen Fall Parameterwerte direkt in die Abfragezeichenfolge aufnehmen.  
  
## <a name="anatomy-of-a-sql-injection-attack"></a>Anatomie eines SQL Injection-Angriffs  
 Beim Einschleusen wird eine Textzeichenfolge vorzeitig beendet, und es wird ein neuer Befehl angefügt. Da der eingeschleuste Befehl zusätzliche Zeichenfolgen enthalten kann, die vor dessen Ausführung angefügt wurden, beendet der Angreifer die eingeschleuste Zeichenfolge mit einer Kommentarmarkierung ("--"). Der Text, der dieser Kommentarmarkierung folgt, wird bei der Ausführung ignoriert. Durch Eingabe eines Semikolons (;) als Trennzeichen können auch mehrere Befehle eingeschleust werden.  
  
 Sofern der SQL-Code syntaktisch korrekt ist, kann die Manipulation nicht programmgesteuert erkannt werden. Sie müssen daher alle Benutzereingaben validieren und Code sorgfältig prüfen, der konstruierte SQL-Befehle im verwendeten Server ausführt. Verketten Sie nie Benutzereingaben, die nicht validiert wurden. Die Zeichenfolgenverkettung ist der primäre Ansatzpunkt für die Einschleusung von Skriptcode.  
  
 Beachten Sie Folgendes:  
  
-   Erstellen Sie keine Transact-SQL-Anweisungen direkt aus Benutzereingaben. Validieren Sie Benutzereingaben mit gespeicherten Prozeduren.  
  
-   Validieren Sie Benutzereingaben durch Prüfen des Typs, der Länge, des Formats und des Bereichs. Verwenden Sie die Transact-SQL-QUOTENAME()-Funktion, um Systemnamen zu maskieren, oder die REPLACE()-Funktion, um Zeichen in einer Zeichenfolge zu maskieren.  
  
-   Implementieren Sie für jede Anwendungsebene mehrere Validierungsschichten.  
  
-   Prüfen Sie die Größe und den Datentyp der Eingabe, und sorgen Sie für die Einhaltung der festgelegten Grenzwerte. Dies kann helfen, vorsätzliche Pufferüberläufe zu verhindern.  
  
-   Prüfen Sie den Inhalt von Zeichenfolgenvariablen, und akzeptieren Sie nur erwartete Werte. Lehnen Sie Einträge ab, die Binärdaten, Maskierungssequenzen und Kommentarzeichen enthalten.  
  
-   Validieren Sie beim Arbeiten mit XML-Dokumenten alle eingegebenen Daten anhand ihres Schemas.  
  
-   Sorgen Sie dafür, dass in Umgebungen mit mehreren Ebenen alle Daten vor dem Eintritt in die vertrauenswürdige Zone validiert werden.  
  
-   Akzeptieren Sie keine der folgenden Zeichenfolgen in Feldern, die von denen Dateinamen erstellt werden können: AUX, CLOCK$, COM1 bis COM8, CON, CONFIG$, LPT1 bis LPT8, NUL und PRN.  
  
-   Verwenden Sie für die Typprüfung und die Längenvalidierung <xref:System.Data.SqlClient.SqlParameter>-Objekte mit gespeicherten Prozeduren und Befehlen.  
  
-   Verwenden Sie im Clientcode <xref:System.Text.RegularExpressions.Regex>-Ausdrücke, um ungültige Zeichen herauszufiltern.  
  
## <a name="dynamic-sql-strategies"></a>Strategien bei der Verwendung von dynamischem SQL  
 Beim Ausführen dynamisch erstellter SQL-Anweisungen in Ihrem prozeduralen Code wird die Besitzkette unterbrochen, sodass SQL Server die Berechtigungen des Aufrufers anhand der Objekte prüfen muss, auf die die dynamischen SQL-Anweisungen zugreifen.  
  
 SQL Server verfügt über Methoden, um Benutzern mithilfe von gespeicherten Prozeduren und benutzerdefinierten Funktionen, die dynamischen SQL-Code ausführen, den Zugriff auf Daten zu gewähren.  
  
-   Die Verwendung vom Identitätswechsel mit der T-SQL-Klausel EXECUTE AS, wie im Artikel zum [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md) beschrieben wird.  
  
-   Das Signieren von gespeicherten Prozeduren mit Zertifikaten, wie im Artikel zum [Signieren von gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md).  
  
### <a name="execute-as"></a>EXECUTE AS  
 Die EXECUTE AS-Klausel ersetzt die Berechtigungen des Aufrufers durch die Berechtigungen des in der EXECUTE AS-Klausel angegebenen Benutzers. Geschachtelte gespeicherte Prozeduren oder Trigger werden im Sicherheitskontext des Proxybenutzers ausgeführt. Bei Anwendungen, die sich auf zeilenbasierte Sicherheit stützen oder eine Überwachung verlangen, kann dies zum Abbruch führen. Einige Funktionen, die die Identität des Benutzers zurückgeben, geben den in der EXECUTE AS-Klausel angegebenen Benutzer und nicht den ursprünglichen Aufrufer zurück. Der Ausführungskontext geht erst dann wieder auf den ursprünglichen Aufrufer über, wenn die Ausführung der Prozedur abgeschlossen wurde oder wenn eine REVERT-Anweisung ausgegeben wird.  
  
### <a name="certificate-signing"></a>Signieren mit Zertifikaten  
 Bei der Ausführung einer mit einem Zertifikat signierten gespeicherten Prozedur werden die dem Zertifikatsbenutzer gewährten Berechtigungen mit den Berechtigungen des Aufrufers zusammengeführt. Der Ausführungskontext bleibt identisch. Der Zertifikatsbenutzer nimmt nicht die Identität des Aufrufers an. Für das Signieren gespeicherter Prozeduren müssen verschiedene Schritte ausgeführt werden. Jedes Mal, wenn die Prozedur geändert wird, muss sie neu signiert werden.  
  
### <a name="cross-database-access"></a>Datenbankübergreifender Zugriff  
 Bei der Ausführung dynamisch erstellter SQL-Anweisungen funktioniert die datenbankübergreifende Besitzverkettung nicht. Dieses Problem können Sie in SQL Server umgehen, indem Sie eine gespeicherte Prozedur erstellen, die auf die Daten in einer anderen Datenbank zugreift, und die Prozedur mit einem Zertifikat signieren, das in beiden Datenbanken vorhanden ist. Die Benutzer können dann auf die von der Prozedur verwendeten Datenbankressourcen zugreifen, ohne dass ihnen Zugriffsrechte für die Datenbank oder andere Berechtigungen erteilt werden müssen.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Gespeicherte Prozeduren](/sql/relational-databases/stored-procedures/stored-procedures-database-engine) und [SQL Injection](/sql/relational-databases/security/sql-injection) in der SQL Server-Onlinedokumentation|In den Themen wird beschrieben, wie Sie gespeicherte Prozeduren erstellen und wie die Einschleusung von SQL-Befehlen bei SQL Injection-Angriffen funktioniert.|  
  
## <a name="see-also"></a>Siehe auch
- [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [Signieren von gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)
- [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
