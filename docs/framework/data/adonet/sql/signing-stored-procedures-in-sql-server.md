---
title: Signieren von gespeicherten Prozeduren in SQL Server
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 98dfaa6d5293cb1ad85f70be3388fb333daef373
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361077"
---
# <a name="signing-stored-procedures-in-sql-server"></a>Signieren von gespeicherten Prozeduren in SQL Server
 Eine digitale Signatur ist ein mit dem privaten Schlüssel des Signaturgebers verschlüsselter Datenhashwert. Der private Schlüssel stellt sicher, dass die digitale Signatur für den Träger oder Besitzer eindeutig ist. Sie können gespeicherte Prozeduren, Funktionen (mit Ausnahme von Inline-Tabellenwertfunktionen), Trigger und Assemblys signieren.  
  
 Sie können gespeicherte Prozeduren mit einem Zertifikat oder einem asymmetrischen Schlüssel signieren. Gedacht ist dies für Szenarien, in denen Berechtigungen nicht über die Besitzverkettung geerbt werden können oder in denen die Besitzkette unterbrochen ist, wie bei dynamischem SQL. Anschließend können Sie erstellen einen mit dem Zertifikat zugeordneten Benutzer Benutzerberechtigungen das Zertifikat für die Objekte, die die gespeicherte Prozedur zugreifen muss.  

 Sie können auch eine Anmeldung für das gleiche Zertifikat erstellen und dann erforderlichen Berechtigungen auf Serverebene, die dieser Anmeldung zu gewähren, oder hinzufügen die Anmeldung an eine oder mehrere der festen Serverrollen. Dies dient zum Aktivieren der vermeiden der `TRUSTWORTHY` Datenbank-Einstellung für Szenarien, in denen Berechtigungen auf höhere Ebene erforderlich sind.  
  
 Wenn die gespeicherte Prozedur ausgeführt wird, kombiniert SQL Server die Berechtigungen der Zertifikatsbenutzer und/oder Anmeldung, mit denen des Aufrufers. Im Gegensatz zu den `EXECUTE AS` -Klausel ändert nicht den Ausführungskontext der Prozedur. Integrierte Funktionen, die Anmelde- und Benutzernamen zurückgeben, geben den Namen des Aufrufers, und nicht den Namen des Zertifikatsbenutzers zurück.  
  
## <a name="creating-certificates"></a>Erstellen von Zertifikaten  
 Wenn Sie eine gespeicherte Prozedur mit einem Zertifikat oder den asymmetrischen Schlüssel, einen Datendigest, bestehend aus dem verschlüsselten Hash der Code der gespeicherten Prozedur, zusammen mit der Execute Anmelden – als Benutzer erstellt wird, mit dem privaten Schlüssel. Zur Laufzeit wird der Datenhashwert mit dem öffentlichen Schlüssel entschlüsselt und mit dem Hashwert der gespeicherten Prozedur verglichen. Ändern die Execute-wie Benutzer den Hashwert ungültig, sodass die digitale Signatur nicht mehr übereinstimmt. Ändern die gespeicherte Prozedur löscht die Signatur vollständig, die verhindert, dass eine Person, die keinen Zugriff auf den privaten Schlüssel am Code der gespeicherten Prozedur zu ändern. In beiden Fällen müssen Sie erneut anmelden die Prozedur bei jeder Änderung des Codes oder der Execute-Benutzer.  
  
 Zum Signieren eines Moduls stehen zwei Schritte:  
  
1.  Erstellen Sie mit der Transact-SQL-`CREATE CERTIFICATE [certificateName]`-Anweisung ein Zertifikat. Diese Anweisung verfügt über mehrere Optionen, mit denen das Start- und Enddatum und ein Kennwort festgelegt werden können. Die Standardgültigkeitsdauer beträgt ein Jahr.  
  
1.  Signieren Sie die Prozedur mit dem Zertifikat. Verwenden Sie dazu die Transact-SQL-`ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]`-Anweisung.  

Nachdem das Modul signiert wurde, muss einen oder mehrere Prinzipale erstellt werden, um die zusätzlichen Berechtigungen enthalten, die dem Zertifikat zugeordnet werden sollen.  

Wenn das Modul zusätzliche Datenbankebene Berechtigungen benötigt:  
  
1.  Erstellen Sie mit der Transact-SQL-`CREATE USER [userName] FROM CERTIFICATE [certificateName]`-Anweisung einen mit diesem Zertifikat verknüpften Datenbankbenutzer. Dieser Benutzer nur in der Datenbank vorhanden ist, und es ist nicht mit einer Anmeldung verknüpft, es sei denn, eine Anmeldung auch über das gleiche Zertifikat erstellt wurde.  
  
1.  Gewähren Sie dem Zertifikatsbenutzer die erforderlichen Berechtigungen für die Datenbankebene.  
  
Wenn das Modul zusätzliche auf Serverebene Berechtigungen benötigt:  
  
1.  Kopieren Sie das Zertifikat an die `master` Datenbank.  
 
1.  Erstellen Sie eine Anmeldung mit diesem Zertifikat mit der Transact-SQL-verknüpften `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` Anweisung.  
  
1.  Erteilen Sie die Anmeldung mit Zertifikat die erforderlichen Berechtigungen für die Serverebene.  
  
> [!NOTE]  
>  Ein Zertifikat kann keine Berechtigungen für Benutzer gewähren, die Berechtigungen hatten, die mit der DENY-Anweisung widerrufen wurden. DENY hat immer Vorrang gegenüber GRANT und verhindert, dass der Aufrufer Berechtigungen erben kann, die dem Zertifikatsbenutzer gewährt wurden.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Modulsignierung](http://go.microsoft.com/fwlink/?LinkId=98590) in SQL Server-Onlinedokumentation|Beschreibt die Modulsignierung und enthält ein Beispielszenario sowie Links zu den relevanten Transact-SQL-Themen.|  
|[Signieren von gespeicherten Prozeduren mit einem Zertifikat](http://msdn.microsoft.com/library/bb283630.aspx) in SQL Server-Onlinedokumentation|Enthält ein Lernprogramm zum Signieren einer gespeicherten Prozedur mit einem Zertifikat.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [Schreiben von sicherem dynamischen SQL in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [Ändern von Daten mit gespeicherten Prozeduren](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
