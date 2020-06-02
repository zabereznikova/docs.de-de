---
title: Autorisierung und Berechtigungen in SQL Server
description: Erfahren Sie, wie Sie explizit Berechtigungen für die Erstellung von Datenbankobjekten, die Sie erstellen, für Benutzer in SQL Server mit ADO.net erteilen.
ms.date: 03/30/2017
ms.assetid: d340405c-91f4-4837-a3cc-a238ee89888a
ms.openlocfilehash: eb01e29b36da5e1793b9176301a968a42115d19c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286532"
---
# <a name="authorization-and-permissions-in-sql-server"></a>Autorisierung und Berechtigungen in SQL Server
Beim Erstellen von Datenbankobjekten müssen Sie Berechtigungen explizit gewähren, damit die Benutzer auch auf die Datenbankobjekte zugreifen können. Jedes sicherungsfähige Objekt verfügt über Berechtigungen, die einem Prinzipal mithilfe von Berechtigungsanweisungen gewährt werden können.  
  
## <a name="the-principle-of-least-privilege"></a>Das Prinzip der minimalen Rechtegewährung  
 Die Verwendung von Konten der untersten Berechtigungsebene (Least-Privileged User Account, LUA) für das Entwickeln von Anwendungen ist ein wichtiger Bestandteil einer tiefgestaffelten Verteidigungsstrategie zur Abwehr von Sicherheitsbedrohungen. Die LUA-Strategie sorgt dafür, dass das Prinzip der minimalen Rechtegewährung eingehalten wird und die Benutzer für die Anmeldung immer nur Benutzerkonten mit eingeschränkten Rechten verwenden. Administrative Aufgaben werden mithilfe fester Serverrollen erledigt, und die Verwendung der festen Serverrolle `sysadmin` ist stark eingeschränkt.  
  
 Befolgen Sie beim Gewähren von Berechtigungen für Datenbankbenutzer stets das Prinzip der minimalen Rechtegewährung. Gewähren Sie immer nur so viele Berechtigungen, wie der Benutzer oder die Rolle zum Ausführen der jeweiligen Aufgabe benötigt.  
  
> [!IMPORTANT]
> Das Entwickeln und Testen einer auf der LUA-Strategie beruhenden Anwendung erfordert ein bestimmtes Maß an zusätzlichem Aufwand. Es ist einfacher, Objekte zu erstellen und Code zu schreiben, während man als Systemadministrator oder Datenbankbesitzer angemeldet ist, als wenn man ein Konto der untersten Berechtigungsebene verwendet. Das Entwickeln von Anwendungen mit einem Konto mit weitreichenden Berechtigungen kann jedoch die Auswirkungen der reduzierten Funktionalität verschleiern, wenn Benutzer mit minimalen Berechtigungen versuchen, eine Anwendung zu starten, die eine höhere Berechtigungsebene erfordert, um funktionsfähig zu sein. Wenn dann den Benutzern zusätzliche Berechtigungen gewährt werden, um verloren gegangene Funktionalität wiederzugewinnen, kann Ihre Anwendung angreifbar werden. Wird jedoch beim Entwerfen, Entwickeln und Testen Ihrer Anwendung ein Konto der untersten Berechtigungsebene verwendet, werden Sie zu einer disziplinierten Herangehensweise an die Sicherheitsplanung gezwungen, sodass unliebsame Überraschungen ausbleiben und Sie nicht in Versuchung geraten, Probleme durch Gewährung erweiterter Rechte zu lösen. Sie können zum Testen eine SQL Server-Anmeldung verwenden, auch wenn Ihre Anwendung mit der Windows-Authentifizierung bereitgestellt werden soll.  
  
## <a name="role-based-permissions"></a>Rollenbasierte Berechtigungen  
 Das Gewähren von Berechtigungen für Rollen statt für Benutzer vereinfacht die Sicherheitsverwaltung. Berechtigungssätze, die Rollen zugewiesen werden, werden von allen Membern der Rolle geerbt. Es ist einfacher, Benutzer einer Rolle hinzuzufügen oder aus ihr zu entfernen, als separate Berechtigungssätze für einzelne Benutzer neu zu erstellen. Rollen können geschachtelt werden, wobei aber zu beachten ist, dass zu viele Ebenen beim Schachteln Leistungseinbußen zur Folge haben können. Sie können Benutzer auch festen Datenbankrollen hinzufügen, wodurch sich das Zuweisen von Berechtigungen vereinfacht.  
  
 Sie können Berechtigungen auf Schemaebene erteilen. Die Benutzer erben dann automatisch Berechtigungen für alle neu im Schema erstellten Objekte, d. h., Sie müssen keine Berechtigungen gewähren, wenn neue Objekte erstellt werden.  
  
## <a name="permissions-through-procedural-code"></a>Berechtigungen über prozeduralen Code  
 Das Kapseln des Datenzugriffs über Module, wie gespeicherte Prozeduren und benutzerdefinierte Funktionen, bedeutet einen zusätzlichen Schutzwall für Ihre Anwendung. Sie können Benutzer von der direkten Interaktion mit Datenbankobjekten abhalten, indem Sie ihnen nur für die gespeicherten Prozeduren oder Funktionen Berechtigungen gewähren und für die zugrunde liegenden Objekte, z. B. Tabellen, die Berechtigungen verweigern. SQL Server erreicht dies durch Besitzverkettung.  
  
## <a name="permission-statements"></a>Berechtigungsanweisungen  
 In der folgenden Tabelle werden die drei Transact-SQL-Berechtigungsanweisungen beschrieben:  
  
|Berechtigungsanweisung|BESCHREIBUNG|  
|--------------------------|-----------------|  
|GRANT|Gewährt eine Berechtigung.|  
|REVOKE|Widerruft eine Berechtigung. Dies ist der Standardzustand für ein neues Objekt. Eine für einen Benutzer oder eine Rolle widerrufene Berechtigung kann von anderen Gruppen oder Rollen, denen der Prinzipal zugewiesen ist, weiter geerbt werden.|  
|VERWEIGERN|Widerruft eine Berechtigung, sodass sie nicht geerbt werden kann. DENY hat gegenüber allen Berechtigungen absolute Priorität. DENY gilt jedoch nicht für Objektbesitzer oder `sysadmin`-Member. Wenn Sie der Rolle `public` mit DENY Berechtigungen für ein Objekt verweigern, gilt dies, mit Ausnahme der Objektbesitzer und der `sysadmin`-Member, für alle Benutzer und Rollen.|  
  
- Die GRANT-Anweisung kann Berechtigungen für eine Gruppe oder Rolle zuweisen, die von Datenbankbenutzern geerbt werden können. Die DENY-Anweisung hat aber gegenüber allen anderen Berechtigungsanweisungen Vorrang. Ein Benutzer, dem eine Berechtigung verweigert wurde, kann daher diese Berechtigung nicht von einer anderen Rolle erben.  
  
> [!NOTE]
> Membern der festen Serverrolle `sysadmin` und Objektbesitzern können Berechtigungen nicht verweigert werden.  
  
## <a name="ownership-chains"></a>Besitzketten  
 SQL Server stellt sicher, dass nur Prinzipale auf Objekte zugreifen können, denen eine entsprechende Berechtigung gewährt wurde. Wenn mehrere Datenbankobjekte gegenseitig aufeinander zugreifen, wird diese Sequenz auch als Kette bezeichnet. Beim Durchlaufen der Glieder der Kette wertet SQL Server Berechtigungen anders aus, als dies beim separaten Zugriff auf die einzelnen Objekte der Fall wäre. Wenn der Zugriff auf ein Objekt über eine Kette erfolgt, vergleicht SQL Server zunächst den Besitzer des Objekts mit dem Besitzer des aufrufenden Objekts (vorhergehender Link in der Kette). Wenn der Besitzer beider Objekte identisch ist, werden die Berechtigungen für das Objekt, auf das verwiesen wird, nicht überprüft. Wenn ein Objekt aber auf ein anderes Objekt zugreift, das einem anderen Besitzer gehört, ist die Besitzkette unterbrochen und SQL Server muss den Sicherheitskontext des Aufrufers prüfen.  
  
## <a name="procedural-code-and-ownership-chaining"></a>Prozeduraler Code und Besitzverkettung  
 Nehmen wir an, einem Besitzer wurden Ausführungsberechtigungen für eine gespeicherte Prozedur gewährt, die Daten aus einer Tabelle auswählt. Wenn der Besitzer der gespeicherten Prozedur identisch mit dem Besitzer der Tabelle ist, müssen dem Benutzer überhaupt keine Berechtigungen für die Tabelle gewährt werden – ihm könnten die Berechtigungen dafür sogar verweigert werden. Ist der Besitzer der gespeicherten Prozedur aber nicht mit dem Besitzer der Tabelle identisch, muss SQL Server die Berechtigungen des Benutzers für die Tabelle prüfen, bevor der Zugriff auf die Daten erlaubt wird.  
  
> [!NOTE]
> Bei dynamischen SQL-Anweisungen gilt die Besitzverkettung nicht. Zum Aufrufen einer Prozedur, die eine SQL-Anweisung ausführt, müssen dem Aufrufer Berechtigungen für die zugrunde liegenden Tabellen gewährt werden, wodurch die Anwendung aber anfällig für SQL Injection-Angriffe wird. SQL Server bietet neue Mechanismen, wie den Identitätswechsel und das Signieren von Modulen mit Zertifikaten, bei denen keine Berechtigungen für die zugrunde liegenden Tabellen erteilt werden müssen. Diese Mechanismen können auch mit gespeicherten Prozeduren für die CLR verwendet werden.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Resource|BESCHREIBUNG|  
|--------------|-----------------|  
|[Berechtigungen](/sql/relational-databases/security/permissions-database-engine)|Enthält Themen, in denen die Berechtigungshierarchie, Katalogsichten und Berechtigungen fester Serverrollen und fester Datenbankrollen beschrieben werden.|
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Authentifizierung in SQL Server](authentication-in-sql-server.md)
- [Server- und Datenbankrollen in SQL Server](server-and-database-roles-in-sql-server.md)
- [Objektbesitz und Trennung von Benutzer und Schema in SQL Server](ownership-and-user-schema-separation-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
