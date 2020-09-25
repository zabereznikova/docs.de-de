---
title: Anwendungssicherheitsszenarios in SQL Server
ms.date: 03/30/2017
ms.assetid: 0164f3a4-406e-4693-bec3-03c8e18b46d7
ms.openlocfilehash: 2d0e65f61939312bf29111e87c49366cd9e389be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197650"
---
# <a name="application-security-scenarios-in-sql-server"></a>Anwendungssicherheitsszenarios in SQL Server

Es gibt kein universelles Standardverfahren, um eine sichere SQL Server-Clientanwendung zu erstellen. Die Anforderungen, Bereitstellungsumgebung und Benutzereigenschaften sind bei jeder Anwendung unterschiedlich. Bei einer Anwendung, die bei der anfänglichen Bereitstellung sicher ist, kann die Sicherheit im Laufe der Zeit nachlassen. Potenzielle Bedrohungen der Zukunft lassen sich nicht präzise vorhersagen.  
  
 SQL Server wurde kontinuierlich weiterentwickelt und um die neuesten Sicherheitsfunktionen erweitert, mit denen Entwickler sichere Datenbankanwendungen erstellen können. Für maximale Sicherheit ist dennoch eine dauerhafte Überwachung und Aktualisierung erforderlich.  
  
## <a name="common-threats"></a>Allgemeine Bedrohungen  

 Entwickler müssen sich kontinuierlich über Sicherheitsbedrohungen und die verfügbaren Tools informieren, um diesen Bedrohungen entgegenzuwirken. Darüber hinaus müssen sie wissen, wie sie selbstverschuldete Sicherheitslücken vermeiden. Die Sicherheit eines Systems ist mit einer Kette vergleichbar, bei der die Beschädigung eines Kettenglieds den Zusammenhalt der gesamten Kette gefährdet. In der folgenden Liste sind einige gängige Sicherheitsbedrohungen aufgeführt, die in den Themen dieses Abschnitts näher erläutert werden.  
  
### <a name="sql-injection"></a>Einschleusung von SQL-Befehlen  

 Bei der Einschleusung von SQL-Befehlen gibt ein böswilliger Benutzer anstelle gültiger Eingaben Transact-SQL-Anweisungen ein. Wenn die Eingabe ohne Überprüfung direkt an den Server weitergegeben wird und die Anwendung den eingeschleusten Code versehentlich ausführt, kann der Angriff Daten beschädigen oder zerstören. Sie können Angriffe, die das Ziel haben, SQL Server-Befehle einzuschleusen, abwehren, indem Sie gespeicherte Prozeduren und parametrisierte Befehle verwenden, dynamisches SQL vermeiden und die Berechtigungen aller Benutzer einschränken.  
  
### <a name="elevation-of-privilege"></a>Erhöhung von Rechten  

 Angriffe durch Rechteerweiterungen treten auf, wenn ein Benutzer die Berechtigungen eines vertrauenswürdigen Kontos (z.B. eines Besitzers oder Administrators) annehmen kann. Arbeiten Sie stets mit Benutzerkonten mit geringstmöglichen Berechtigungen, und weisen Sie nur die wirklich benötigten Berechtigungen zu. Vermeiden Sie bei der Ausführung von Code die Verwendung von Administrator- oder Besitzerkonten. Dadurch lässt sich der Schaden begrenzen, falls ein Angriff erfolgreich ist. Wenn Sie Aufgaben ausführen, für die zusätzliche Berechtigungen erforderlich sind, verwenden Sie für die Dauer der Aufgabe Prozedursignaturen oder einen Identitätswechsel. Sie können gespeicherte Prozeduren mit Zertifikaten signieren oder zur vorübergehenden Zuweisung von Berechtigungen mit Identitätswechsel arbeiten.  
  
### <a name="probing-and-intelligent-observation"></a>Angriffe durch Auswertung von Fehlermeldungen und intelligente Beobachtung  

 Bei einem Probing-Angriff können die von einer Anwendung generierten Fehlermeldungen verwendet werden, um nach Sicherheitslücken zu suchen. Implementieren Sie im gesamten prozeduralen Code eine Fehlerbehandlung, um zu verhindern, dass SQL Server-Fehlerinformationen an den Endbenutzer zurückgegeben werden.  
  
### <a name="authentication"></a>Authentifizierung  

 Ein Angriff durch Einschleusung einer Verbindungszeichenfolge kann bei Verwendung von SQL Server-Anmeldungen auftreten, bei denen Verbindungszeichenfolgen zur Laufzeit basierend auf Benutzereingaben generiert werden. Wenn die Verbindungszeichenfolge nicht auf gültige Schlüsselwortkombinationen geprüft wird, kann ein Angreifer zusätzliche Zeichen einfügen und möglicherweise auf vertrauliche Daten oder andere Ressourcen auf dem Server zugreifen. Verwenden Sie nach Möglichkeit die Windows-Authentifizierung. Wenn Sie SQL Server-Anmeldungen nutzen müssen, verwenden Sie <xref:System.Data.SqlClient.SqlConnectionStringBuilder>, um Verbindungszeichenfolgen zur Laufzeit zu erstellen und zu überprüfen.  
  
### <a name="passwords"></a>Kennwörter  

 Viele Angriffe sind erfolgreich, weil ein Eindringling ein Kennwort für einen Benutzer mit Administratorenrechten abrufen oder erraten konnte. Kennwörter dienen als erste Schutzmaßnahme gegen Eindringlinge, daher ist die Festlegung sicherer Kennwörter von entscheidender Bedeutung für die Systemsicherheit. Erstellen Sie Kennwortrichtlinien für die Authentifizierung im gemischten Modus, und setzen Sie diese Richtlinien durch.  
  
 Weisen Sie dem `sa`-Konto immer ein sicheres Kennwort zu, auch wenn Sie die Windows-Authentifizierung verwenden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)  
 Beschreibt, wie gespeicherte Prozeduren zur Verwaltung von Berechtigungen und zum Steuern des Datenzugriffs verwendet werden können. Die Verwendung gespeicherter Prozeduren bietet einen effektiven Schutz vor einer ganzen Reihe von Sicherheitsbedrohungen.  
  
 [Schreiben von sicherem dynamischem SQL in SQL Server](writing-secure-dynamic-sql-in-sql-server.md)  
 Beschreibt Verfahren, um mithilfe von gespeicherten Prozeduren sicheren dynamischen SQL-Code zu schreiben.  
  
 [Signieren von gespeicherten Prozeduren in SQL Server](signing-stored-procedures-in-sql-server.md)  
 Beschreibt die Vorgehensweise zum Signieren gespeicherter Prozeduren mit einem Zertifikat, sodass die Benutzer mit Daten arbeiten können, auf die sie keinen direkten Zugriff haben. Auf diese Weise können gespeicherte Prozeduren Vorgänge ausführen, die der Aufrufer seinen Berechtigungen zufolge nicht direkt ausführen darf.  
  
 [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)  
 Beschreibt, wie mithilfe der EXECUTE AS-Klausel die Identität eines anderen Benutzers angenommen werden kann. Beim Identitätswechsel wechselt der Ausführungskontext vom Aufrufer zum angegebenen Benutzer.  
  
 [Gewähren zeilenspezifischer Berechtigungen in SQL Server](granting-row-level-permissions-in-sql-server.md)  
 Beschreibt die Implementierung von zeilenspezifischen Berechtigungen zur Einschränkung des Datenzugriffs.  
  
 [Erstellen von Anwendungsrollen in SQL Server](creating-application-roles-in-sql-server.md)  
 Beschreibt die Funktionen und die Funktionalität von Anwendungsrollen.  
  
 [Aktivieren des datenbankübergreifenden Zugriffs in SQL Server](enabling-cross-database-access-in-sql-server.md)  
 Beschreibt, wie der Zugriff auf mehrere Datenbanken bereitgestellt werden kann, ohne dabei die Sicherheit zu gefährden.  
  
## <a name="see-also"></a>Weitere Informationen

- [SQL Server Sicherheit](sql-server-security.md)
- [Übersicht über die SQL Server-Sicherheit](overview-of-sql-server-security.md)
- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
