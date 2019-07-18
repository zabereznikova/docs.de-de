---
title: Anpassen von Berechtigungen durch Identitätswechsel in SQL Server
ms.date: 03/30/2017
ms.assetid: dc733d09-1d6d-4af0-9c4b-8d24504860f1
ms.openlocfilehash: d44e410727924260640f0f50aea5ea41f264f3af
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650340"
---
# <a name="customizing-permissions-with-impersonation-in-sql-server"></a>Anpassen von Berechtigungen durch Identitätswechsel in SQL Server
Viele Anwendungen verwenden für den Zugriff auf Daten gespeicherte Prozeduren, wobei der Zugriff auf die Basistabellen per Besitzverkettung gesteuert wird. Sie können EXECUTE-Berechtigungen für gespeicherte Prozeduren gewähren und so Berechtigungen für die Basistabellen widerrufen oder verweigern. Wenn der Besitzer der gespeicherten Prozedur identisch mit dem Besitzer der Tabellen ist, nimmt SQL Server keine Prüfung der Berechtigungen des Aufrufers vor. Bei Objekten, die verschiedenen Besitzern gehören, und bei dynamischem SQL funktioniert die Besitzverkettung jedoch nicht.  
  
 Sie können die EXECUTE AS-Klausel in einer gespeicherten Prozedur verwenden, wenn der Aufrufer keine Berechtigung für die Datenbankobjekte besitzt, auf die verwiesen wird. Durch die EXECUTE AS-Klausel geht der Ausführungskontext auf den Proxybenutzer über. Sämtlicher Code sowie alle Aufrufe geschachtelter gespeicherter Prozeduren oder Trigger werden im Sicherheitskontext des Proxybenutzers ausgeführt. Der Ausführungskontext geht erst dann wieder auf den ursprünglichen Aufrufer über, wenn die Ausführung der Prozedur abgeschlossen wurde oder wenn eine REVERT-Anweisung ausgegeben wird.  
  
## <a name="context-switching-with-the-execute-as-statement"></a>Kontextwechsel mit der EXECUTE AS-Anweisung  
 Mit der Transact-SQL-EXECUTE AS-Anweisung können Sie den Ausführungskontext einer Anweisung wechseln, indem ein Identitätswechsel zu einer anderen Anmeldung oder einem anderen Datenbankbenutzer erfolgt. Diese Vorgehensweise empfiehlt sich, wenn Abfragen und Prozeduren unter einem anderen Benutzernamen getestet werden sollen.  
  
```  
EXECUTE AS LOGIN = 'loginName';  
EXECUTE AS USER = 'userName';  
```  
  
 Sie müssen IMPERSONATE-Berechtigungen für die Anmeldung oder den Benutzer besitzen, mit dessen Identität Sie auftreten möchten. Benutzer mit der `sysadmin`-Rolle haben per se IMPERSONATE-Berechtigungen für alle Datenbanken, und für Benutzer mit der `db_owner`-Rolle gelten diese Berechtigungen für die Datenbanken, deren Besitzer sie sind.  
  
## <a name="granting-permissions-with-the-execute-as-clause"></a>Gewähren von Berechtigungen mit der EXECUTE AS-Klausel  
 Sie können die EXECUTE AS-Klausel im Definitionsheader einer gespeicherten Prozedur, eines Triggers oder einer benutzerdefinierten Funktion (nicht aber in Inline-Tabellenwertfunktionen) verwenden. Die Prozedur wird dann im Kontext des Benutzernamens oder Schlüsselworts ausgeführt, der oder das in der EXECUTE AS-Klausel angegeben ist. Sie können einen Proxybenutzer in der Datenbank erstellen, der keiner Anmeldung zugeordnet ist, indem Sie ihm nur die erforderlichen Berechtigungen für die Objekte gewähren, auf die die Prozedur zugreift. Nur der in der EXECUTE AS-Klausel angegebene Proxybenutzer muss eine Berechtigung für alle Objekte besitzen, auf die das Modul zugreift.  
  
> [!NOTE]
>  Einige Aktionen, z. B. TRUNCATE TABLE, besitzen keine Berechtigungen, die gewährt werden können. Durch Integrieren der Anweisung in eine Prozedur und Angeben eines Proxybenutzers, der ALTER TABLE-Berechtigungen besitzt, können Sie die Berechtigungen so erweitern, dass die Tabelle für die Aufrufer, die nur EXECUTE-Berechtigungen für die Prozedur besitzen, abgeschnitten wird.  
  
 Der in der EXECUTE AS-Klausel angegebene Kontext ist für die Dauer der Prozedur, einschließlich der geschachtelten Prozeduren und Trigger, gültig. Nach Abschluss der Ausführung oder bei Ausgabe der REVERT-Anweisung wechselt der Kontext wieder zum Aufrufer zurück.  
  
 Für die Aufnahme der EXECUTE AS-Klausel in eine Prozedur sind die folgenden drei Schritte auszuführen.  
  
1. Erstellen Sie einen Proxybenutzer in der Datenbank, der keiner Anmeldung zugeordnet wird. Dieser Schritt ist nicht zwingend erforderlich, erleichtert aber das Verwalten der Berechtigungen.  
  
```  
CREATE USER proxyUser WITHOUT LOGIN  
```  
  
1. Gewähren Sie dem Proxybenutzer die notwendigen Berechtigungen.  
  
2. Fügen Sie der gespeicherten Prozedur oder der benutzerdefinierten Funktion die EXECUTE AS-Klausel hinzu.  
  
```  
CREATE PROCEDURE [procName] WITH EXECUTE AS 'proxyUser' AS ...  
```  
  
> [!NOTE]
>  Anwendungen, die eine Überwachung erfordern, können abgebrochen werden, da der ursprüngliche Sicherheitskontext des Aufrufers nicht beibehalten wird. Integrierte Funktionen, die die Identität des aktuellen Benutzers zurückgeben, z. B. SESSION_USER, USER oder USER_NAME, geben den mit der EXECUTE AS-Klausel verknüpften Benutzer und nicht den ursprünglichen Aufrufer zurück.  
  
### <a name="using-execute-as-with-revert"></a>Verwenden von EXECUTE AS mit REVERT  
 Mit der Transact-SQL-REVERT-Anweisung  können Sie zum ursprünglichen Ausführungskontext zurückkehren.  
  
 Der optionale Klausel WITH NO REVERT COOKIE = @variableName, können Sie den Ausführungskontext zurück zum Aufrufer wechseln, wenn die @variableName Variable enthält den richtigen Wert. Auf diese Weise kann der Ausführungskontext in Umgebungen, in denen Verbindungspooling verwendet wird, wieder an den Aufrufer zurückgegeben werden. Da der Wert des @variableName kennt nur der Aufrufer der EXECUTE AS-Anweisung, dass der Ausführungskontext vom Endbenutzer geändert werden kann, die die Anwendung aufruft, kann der Aufrufer sicherstellen. Beim Schließen wird die Verbindung an den Pool zurückgegeben. Weitere Informationen zum Verbindungspooling in ADO.NET finden Sie unter [SQL Server Connection Pooling (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
### <a name="specifying-the-execution-context"></a>Angeben des Ausführungskontexts  
 Neben dem Angeben eines Benutzers können Sie EXECUTE AS auch zusammen mit den folgenden Schlüsselwörtern verwenden.  
  
- CALLER: Das Ausführen als CALLER ist die Standardeinstellung. Wenn nichts anderes angegeben ist, wird die Prozedur im Sicherheitskontext des Aufrufers ausgeführt.  
  
- OWNER: Mit OWNER wird die Prozedur im Kontext des Prozedurbesitzers ausgeführt. Wenn die Prozedur in einem Schema erstellt wird, dessen Besitzer der Datenbankbesitzer (`dbo`) ist, wird die Prozedur mit uneingeschränkten Berechtigungen ausgeführt.  
  
- SELF: Mit SELF wird die Prozedur im Sicherheitskontext des Erstellers der gespeicherten Prozedur ausgeführt. Dies entspricht der Ausführung der Prozedur als ein spezifischer Benutzer, wobei der spezifische Benutzer die Person ist, die die Prozedur erstellt oder geändert hat.  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [Schreiben von sicherem dynamischen SQL in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)
- [Signieren von gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)
- [Ändern von Daten mit gespeicherten Prozeduren](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
