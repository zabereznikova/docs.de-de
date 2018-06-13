---
title: Anwendungssicherheitsszenarios in SQL Server
ms.date: 03/30/2017
ms.assetid: 0164f3a4-406e-4693-bec3-03c8e18b46d7
ms.openlocfilehash: 1239715678bda648bc962f9b23667b954b540e3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363324"
---
# <a name="application-security-scenarios-in-sql-server"></a>Anwendungssicherheitsszenarios in SQL Server
Für das Erstellen einer sicheren SQL Server-Clientanwendung gibt es kein Patentrezept. Jede Anwendung hat spezifische Anforderungen, eine spezielle Bereitstellungsumgebung und einen eigenen Benutzerkreis. Eine Anwendung, die zum Zeitpunkt ihrer Bereitstellung angemessen sicher ist, kann im Laufe der Zeit weniger sicher werden. Es ist unmöglich, genau vorherzusagen, welche Bedrohungen zukünftig entstehen können.  
  
 SQL Server, als Produkt, wurde im Laufe der Zeit ständig um die jeweils neuesten Sicherheitsfunktionen erweitert, um Entwicklern das Erstellen sicherer Datenbankanwendungen zu ermöglichen. Dennoch ist Sicherheit nicht einfach "ab Werk" zu haben; sie erfordert eine ständige Überwachung und Aktualisierung.  
  
## <a name="common-threats"></a>Allgemeine Bedrohungen  
 Entwickler müssen die Sicherheitsbedrohungen und die Tools zu deren Abwehr kennen, und sie müssen wissen, wie selbst zu verantwortende Sicherheitslücken vermieden werden können. Sicherheit ist wie eine Kette – Mängel in einem Glied bringen die Festigkeit der gesamten Kette in Gefahr. In der folgenden Liste finden Sie eine Übersicht über die häufigsten Sicherheitsbedrohungen. Eine ausführliche Erläuterung dieser Bedrohungen folgt dann in den einzelnen Themen in diesem Abschnitt.  
  
### <a name="sql-injection"></a>SQL-Injection  
 Die Einschleusung von SQL-Befehlen (SQL Injection-Angriff) ist eine Möglichkeit, Anwendungen anzugreifen. Dabei werden anstelle einer gültigen Eingabe Transact-SQL-Anweisungen in den Code eingeschleust. Wenn die Eingabe direkt und ohne Validierung an den Server weitergeleitet wird und die Anwendung den eingeschleusten Code ausführt, können auf diese Weise Daten beschädigt oder sogar zerstört werden. Sie können die Einschleusung von SQL Server-Befehlen vereiteln, indem Sie gespeicherte Prozeduren und parametrisierte Befehle verwenden, dynamisches SQL vermeiden und den Benutzern nur eingeschränkte Berechtigungen gewähren.  
  
### <a name="elevation-of-privilege"></a>Angriffe durch Rechteerweiterung  
 Von einem Angriff durch Rechteerweiterung wird gesprochen, wenn sich ein Benutzer Zugang zu den Privilegien eines vertrauenswürdigen Kontos, z. B. als Besitzer oder Administrator, verschafft hat und diese für schädliche Aktionen nutzt. Arbeiten Sie immer nur mit Konten der untersten Berechtigungsebene, und weisen Sie nur die Berechtigungen zu, die wirklich benötigt werden. Vermeiden Sie es, zum Ausführen von Code administrative oder Besitzerkonten zu verwenden. Auf diese Weise dämmen Sie den potenziellen Schaden ein, den ein erfolgreicher Angriff verursachen kann. Verwenden Sie beim Ausführen von Aufgaben, die zusätzliche Berechtigungen erfordern, Prozedursignatur oder Identitätswechsel nur so lange, wie Sie sie für die Aufgabe benötigen. Sie können gespeicherte Prozeduren mit Zertifikaten signieren oder zur vorübergehenden Zuweisung von Berechtigungen Identitätswechsel verwenden.  
  
### <a name="probing-and-intelligent-observation"></a>Angriffe durch Auswertung von Fehlermeldungen und intelligente Beobachtung  
 Angreifer können durch die Auswertung der von einer Anwendung generierten Fehlermeldungen Rückschlüsse auf eventuelle Sicherheitslücken ziehen. Implementieren Sie daher in prozeduralem Code immer auch eine Fehlerbehandlungsroutine, damit der Endbenutzer keine SQL Server-Fehlerinformationen angezeigt bekommt.  
  
### <a name="authentication"></a>Authentifizierung  
 Angreifer können die Verwendung von SQL Server-Anmeldungen ausnutzen, bei denen zur Laufzeit eine auf einer Benutzereingabe basierende Verbindungszeichenfolge konstruiert wird. Wenn die Verbindungszeichenfolge nicht auf gültige Schlüsselwortpaare überprüft wird, hat der Angreifer u. U. die Möglichkeit, zusätzliche Zeichen einzuschleusen, die es ihm erlauben, auf sicherheitsrelevante Daten oder andere Ressourcen auf dem Server zuzugreifen. Verwenden Sie daher nach Möglichkeit die Windows-Authentifizierung. Wenn Sie mit SQL Server-Anmeldungen arbeiten müssen, verwenden Sie zum Erstellen und Validieren der Verbindungszeichenfolgen zur Laufzeit den Verbindungszeichenfolgen-Generator (<xref:System.Data.SqlClient.SqlConnectionStringBuilder>).  
  
### <a name="passwords"></a>Kennwortangriffe  
 Viele Angriffe sind erfolgreich, weil es dem Angreifer gelungen ist, das Kennwort eines Benutzers auszuspionieren oder zu erraten. Kennwörter bilden die erste Verteidigungslinie gegen Angriffe, daher ist die Festlegung starker Kennwörter für die Sicherheit Ihres Systems von entscheidender Bedeutung. Sie können Kennwortrichtlinien für die Authentifizierung im gemischten Modus erstellen und durchsetzen.  
  
 Weisen Sie dem `sa`-Konto immer, auch bei Verwendung der Windows-Authentifizierung, ein starkes Kennwort zu.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 Beschreibt, wie gespeicherte Prozeduren zur Verwaltung von Berechtigungen und zum Steuern des Datenzugriffs verwendet werden können. Die Verwendung gespeicherter Prozeduren bietet einen effektiven Schutz vor einer ganzen Reihe von Sicherheitsbedrohungen.  
  
 [Schreiben von sicherem dynamischen SQL in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 Beschreibt Verfahren zum Schreiben von sicherem dynamischen SQL-Code unter Verwendung gespeicherter Prozeduren.  
  
 [Signieren von gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 Beschreibt die Vorgehensweise zum Signieren gespeicherter Prozeduren mit einem Zertifikat, sodass die Benutzer mit Daten arbeiten können, auf die sie keinen direkten Zugriff haben. Auf diese Weise können gespeicherte Prozeduren Vorgänge ausführen, die der Aufrufer seinen Berechtigungen zufolge nicht direkt ausführen darf.  
  
 [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 Beschreibt, wie mithilfe der EXECUTE AS-Klausel die Identität eines anderen Benutzers angenommen werden kann. Beim Identitätswechsel wechselt der Ausführungskontext vom Aufrufer zum angegebenen Benutzer.  
  
 [Gewähren zeilenspezifischer Berechtigungen in SQL Server](../../../../../docs/framework/data/adonet/sql/granting-row-level-permissions-in-sql-server.md)  
 Beschreibt die Implementierung von zeilenspezifischen Berechtigungen zur Einschränkung des Datenzugriffs.  
  
 [Erstellen von Anwendungsrollen in SQL Server](../../../../../docs/framework/data/adonet/sql/creating-application-roles-in-sql-server.md)  
 Beschreibt die Funktionen und die Funktionalität von Anwendungsrollen.  
  
 [Aktivieren des datenbankübergreifenden Zugriffs in SQL Server](../../../../../docs/framework/data/adonet/sql/enabling-cross-database-access-in-sql-server.md)  
 Beschreibt, wie der Zugriff auf mehrere Datenbanken bereitgestellt werden kann, ohne dabei die Sicherheit zu gefährden.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Security (SQL Server-Sicherheit)](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
