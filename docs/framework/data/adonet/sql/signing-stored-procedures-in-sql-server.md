---
title: Signieren von gespeicherten Prozeduren in SQL Server
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: da7b21d725d301006288245c940e4367c3ce8568
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606821"
---
# <a name="signing-stored-procedures-in-sql-server"></a>Signieren von gespeicherten Prozeduren in SQL Server
 Eine digitale Signatur ist ein mit dem privaten Schlüssel des Signaturgebers verschlüsselter Datenhashwert. Der private Schlüssel stellt sicher, dass die digitale Signatur für den Träger oder Besitzer eindeutig ist. Sie können gespeicherte Prozeduren, Funktionen (mit Ausnahme von Inline-Tabellenwertfunktionen), Trigger und Assemblys registrieren.  
  
 Sie können gespeicherte Prozeduren mit einem Zertifikat oder einem asymmetrischen Schlüssel signieren. Gedacht ist dies für Szenarien, in denen Berechtigungen nicht über die Besitzverkettung geerbt werden können oder in denen die Besitzkette unterbrochen ist, wie bei dynamischem SQL. Anschließend können Sie erstellen einen auf das Zertifikat zugeordneten Benutzer erteilen von Benutzerberechtigungen für die Objekte, die Zugriff auf die gespeicherte Prozedur muss für das Zertifikat.  

 Sie können auch erstellen eine Anmeldung für das gleiche Zertifikat, und klicken Sie dann alle erforderlichen Berechtigungen auf Serverebene, die dieser Anmeldung zu gewähren oder hinzufügen die Anmeldung an eine oder mehrere der festen Serverrollen. Auf diese Weise vermeiden Sie aktivieren die `TRUSTWORTHY` Datenbank-Einstellung für Szenarien, in dem Berechtigungen auf höhere Ebene benötigt werden.  
  
 Wenn die gespeicherte Prozedur ausgeführt wird, kombiniert SQL Server die Berechtigungen der Zertifikatsbenutzer bzw. der Anmeldung, mit denen des Aufrufers. Im Gegensatz zu den `EXECUTE AS` -Klausel wird nicht den Ausführungskontext der Prozedur geändert. Integrierte Funktionen, die Anmelde- und Benutzernamen zurückgeben, geben den Namen des Aufrufers, und nicht den Namen des Zertifikatsbenutzers zurück.  
  
## <a name="creating-certificates"></a>Erstellen von Zertifikaten  
 Wenn Sie eine gespeicherte Prozedur mit einem Zertifikat oder asymmetrischen Schlüssels ein datenhashwert bestehend aus dem verschlüsselten Hash Code der gespeicherten Prozedur, zusammen mit der Execute Anmelden – als Benutzer erstellt wird, mit dem privaten Schlüssel. Zur Laufzeit wird der Datenhashwert mit dem öffentlichen Schlüssel entschlüsselt und mit dem Hashwert der gespeicherten Prozedur verglichen. Ändern die Execute-wie Benutzer den Hashwert ungültig, so, dass die digitale Signatur nicht mehr übereinstimmt. Ändern die gespeicherte Prozedur löscht die Signatur vollständig, die verhindert, dass eine Person, die keinen Zugriff auf den privaten Schlüssel aus Code der gespeicherten Prozedur zu ändern. In beiden Fällen Sie müssen neu signieren die Prozedur bei jeder Änderung des Codes oder die Execute-Benutzer.  
  
 Es gibt zwei notwendigen Schritten beteiligt, die zum Signieren eines Moduls:  
  
1.  Erstellen Sie mit der Transact-SQL-`CREATE CERTIFICATE [certificateName]`-Anweisung ein Zertifikat. Diese Anweisung verfügt über mehrere Optionen, mit denen das Start- und Enddatum und ein Kennwort festgelegt werden können. Die Standardgültigkeitsdauer ist ein Jahr.  
  
1.  Signieren Sie die Prozedur mit dem Zertifikat. Verwenden Sie dazu die Transact-SQL-`ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]`-Anweisung.  

Nachdem das Modul signiert wurde, muss einen oder mehrere Prinzipale erstellt werden, um die zusätzlichen Berechtigungen enthalten, die mit dem Zertifikat verknüpft werden sollen.  

Wenn das Modul zusätzliche auf Datenbankebene-Berechtigungen erforderlich:  
  
1.  Erstellen Sie mit der Transact-SQL-`CREATE USER [userName] FROM CERTIFICATE [certificateName]`-Anweisung einen mit diesem Zertifikat verknüpften Datenbankbenutzer. Dieser Benutzer nur in der Datenbank vorhanden ist, und es ist nicht mit einer Anmeldung verknüpft, es sei denn, eine Anmeldung auch über das gleiche Zertifikat erstellt wurde.  
  
1.  Erteilen Sie dem Zertifikatsbenutzer die erforderlichen Berechtigungen auf Datenbankebene.  
  
Wenn das Modul zusätzliche auf Serverebene-Berechtigungen erforderlich:  
  
1.  Kopieren Sie das Zertifikat auf dem `master` Datenbank.  
 
1.  Erstellen Sie eine Anmeldung mit diesem Zertifikat, mit der Transact-SQL-verknüpften `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` Anweisung.  
  
1.  Erteilen Sie der Anmeldung des Zertifikats die erforderlichen Berechtigungen auf Serverebene.  
  
> [!NOTE]  
>  Ein Zertifikat kann keine Berechtigungen für Benutzer gewähren, die Berechtigungen hatten, die mit der DENY-Anweisung widerrufen wurden. DENY hat immer Vorrang gegenüber GRANT und verhindert, dass der Aufrufer Berechtigungen erben kann, die dem Zertifikatsbenutzer gewährt wurden.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Modulsignierung](https://go.microsoft.com/fwlink/?LinkId=98590) in SQL Server-Onlinedokumentation|Beschreibt die Modulsignierung und enthält ein Beispielszenario sowie Links zu den relevanten Transact-SQL-Themen.|  
|[Signieren von gespeicherten Prozeduren mit einem Zertifikat](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate) in SQL Server-Onlinedokumentation|Enthält ein Lernprogramm zum Signieren einer gespeicherten Prozedur mit einem Zertifikat.|  
  
## <a name="see-also"></a>Siehe auch
- [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [Schreiben von sicherem dynamischen SQL in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)
- [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)
- [Ändern von Daten mit gespeicherten Prozeduren](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
