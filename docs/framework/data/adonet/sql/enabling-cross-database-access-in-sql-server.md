---
title: Aktivieren des datenbankübergreifenden Zugriffs in SQL Server
ms.date: 03/30/2017
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
ms.openlocfilehash: 62b0bffd5e77cccdb49913428005c4f0036abd46
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554904"
---
# <a name="enabling-cross-database-access-in-sql-server"></a>Aktivieren des datenbankübergreifenden Zugriffs in SQL Server
Von einer datenbankübergreifenden Besitzverkettung spricht man, wenn eine Prozedur in einer Datenbank von Objekten in einer anderen Datenbank abhängt. Eine datenbankübergreifende Besitzkette funktioniert wie die Besitzkette innerhalb einer einzelnen Datenbank – mit dem Unterschied, dass eine durchgängige Besitzkette voraussetzt, dass alle Objektbesitzer demselben Anmeldekonto zugeordnet sind. Wenn das Quellobjekt in der Quelldatenbank und das Zielobjekt in der Zieldatenbank zu ein und demselben Anmeldekonto gehören, nimmt SQL Server keine Prüfung der Berechtigungen für die Zielobjekte vor.  
  
## <a name="off-by-default"></a>Standardmäßig deaktiviert  
 Die datenbankübergreifende Besitzverkettung ist standardmäßig deaktiviert. Microsoft empfiehlt, dass Sie die datenbankübergreifende Besitzverkettung deaktivieren, da Sie sich sonst den folgenden Sicherheitsrisiken aussetzen:  
  
- Datenbankbesitzer und Member der `db_ddladmin`-Datenbankrolle bzw. `db_owners` können Objekte erstellen, deren Besitzer andere Benutzer sind. Diese Objekte können potenziell auf Objekte in anderen Datenbanken zielen. Das bedeutet: Wenn Sie die datenbankübergreifende Besitzverkettung aktivieren, müssen Sie sich dessen bewusst sein, dass diese Benutzer auf die Daten in allen verketteten Datenbanken zugreifen können.  
  
- Benutzer mit der CREATE DATABASE-Berechtigung können neue Datenbanken erstellen und vorhandene Datenbanken anfügen. Wenn die datenbankübergreifende Besitzverkettung aktiviert ist, können diese Benutzer u. U. auf Objekte in anderen Datenbanken zugreifen, auf die sie von den Datenbanken aus, die sie selbst neu erstellen oder anhängen, keinen Zugriff hätten.  
  
## <a name="enabling-cross-database-ownership-chaining"></a>Aktivieren der datenbankübergreifenden Besitzverkettung  
 Die datenbankübergreifende Besitzverkettung sollte nur in Umgebungen aktiviert werden, in denen Sie Benutzern mit weitreichenden Berechtigungen voll vertrauen. Sie kann bei der Einrichtung für alle Datenbanken oder mit den Transact-SQL-Befehlen `sp_configure` und `ALTER DATABASE` nur für bestimmte Datenbanken aktiviert werden.  
  
 Wenn Sie die datenbankübergreifende Besitzverkettung selektiv konfigurieren möchten, deaktivieren Sie sie mithilfe von `sp_configure` für den Server. Konfigurieren Sie dann mit dem Befehl ALTER DATABASE und mit SET DB_CHAINING ON die datenbankübergreifende Besitzverkettung für die gewünschten Datenbanken.  
  
 Im folgenden Beispiel wird die datenbankübergreifende Besitzverkettung für alle Datenbanken aktiviert:  
  
```sql
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 Im folgenden Beispiel wird die datenbankübergreifende Besitzverkettung für bestimmte Datenbanken aktiviert:  
  
```sql
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a>Dynamische SQL-Anweisungen  
 Die datenbankübergreifende Besitzverkettung funktioniert nicht, wenn dynamisch erstellte SQL-Anweisungen ausgeführt werden, sofern derselbe Benutzer nicht in beiden Datenbanken vorhanden ist. Dieses Problem können Sie in SQL Server umgehen, indem Sie eine gespeicherte Prozedur erstellen, die auf die Daten in einer anderen Datenbank zugreift, und die Prozedur mit einem Zertifikat signieren, das in beiden Datenbanken vorhanden ist. Dadurch erhalten Benutzer Zugriff auf die von der Prozedur verwendeten Datenbankressourcen, ohne dass ihnen Datenbankzugriff gewährt wird oder Berechtigungen erteilt werden.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Resource|BESCHREIBUNG|  
|--------------|-----------------|  
|[Erweitern des Daten Bank Identitäts Wechsels mithilfe der Option EXECUTE AS](/previous-versions/sql/sql-server-2008-r2/ms188304(v=sql.105)) und [Cross DB Ownership Chaining](/sql/database-engine/configure-windows/cross-db-ownership-chaining-server-configuration-option).|In den Artikeln wird beschrieben, wie die datenbankübergreifende Besitz Verkettung für eine Instanz von SQL Server konfiguriert wird.|  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Übersicht über die SQL Server-Sicherheit](overview-of-sql-server-security.md)
- [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Schreiben von sicherem dynamischem SQL in SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Signieren von gespeicherten Prozeduren in SQL Server](signing-stored-procedures-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
