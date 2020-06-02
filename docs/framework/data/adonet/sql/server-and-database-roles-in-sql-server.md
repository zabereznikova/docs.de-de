---
title: Server- und Datenbankrollen in SQL Server
description: Erfahren Sie mehr über die Rollen fester Server und fester Daten Bank, denen ein fester Satz von Berechtigungen zugewiesen ist. SQL Server verwendet rollenbasierte Sicherheit.
ms.date: 03/30/2017
ms.assetid: 5482dfdb-e498-4614-8652-b174829eed13
ms.openlocfilehash: 9c3725b0404a5b3c754a53fa56f4a22497afee70
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286235"
---
# <a name="server-and-database-roles-in-sql-server"></a>Server- und Datenbankrollen in SQL Server
Alle SQL Server-Versionen verwenden die rollenbasierte Sicherheit, mit der Sie einer Rolle, also einer ganzen Gruppe von Benutzern, Berechtigungen zuweisen können, statt Berechtigungen individuell für jeden Benutzer einzeln festzulegen. Feste Server- und feste Datenbankrollen besitzen einen festen Satz von ihnen übertragenen Berechtigungen.  
  
## <a name="fixed-server-roles"></a>Feste Serverrollen  
 Feste Serverrollen besitzen einen festen Satz von Berechtigungen, die serverweit gültig sind. Sie sind zur Verwaltung von SQL Server gedacht, und die ihnen zugewiesenen Berechtigungen können nicht geändert werden. Anmeldungen können festen Serverrollen zugewiesen sein, ohne dass in einer Datenbank ein Benutzerkonto vorhanden ist.  
  
> [!IMPORTANT]
> Die feste Serverrolle `sysadmin` schließt alle anderen Rollen ein und kennt keine Einschränkungen. Fügen Sie dieser Rolle keine Prinzipale hinzu, außer wenn ihre Vertrauenswürdigkeit sehr hoch ist. Mitglieder der Rolle `sysadmin` verfügen über unwiderrufliche Administratorberechtigungen für alle Serverdatenbanken und -ressourcen.  
  
 Gehen Sie beim Hinzufügen von Benutzern zu festen Serverrollen mit großer Sorgfalt vor. So können z. B. Benutzer mit der Rolle `bulkadmin` den Inhalt einer beliebigen lokalen Datei in eine Tabelle einfügen, wodurch die Datenintegrität gefährdet werden könnte. Eine komplette Liste fester Server Rollen und Berechtigungen finden Sie unter SQL Server-Onlinedokumentation.  
  
## <a name="fixed-database-roles"></a>Feste Datenbankrollen  
 Feste Datenbankrollen besitzen einen vordefinierten Satz von Berechtigungen, mit denen Sie problemlos ganze Berechtigungsgruppen verwalten können. Member der Rolle `db_owner` können alle Konfigurations- und Wartungsaktivitäten an der Datenbank ausführen.  
  
 Weitere Informationen zu den vordefinierten SQL Server-Rollen finden Sie in den folgenden Ressourcen.  
  
|Resource|BESCHREIBUNG|  
|--------------|-----------------|  
|[Rollen auf Serverebene](/sql/relational-databases/security/authentication-access/server-level-roles)|Beschreibt die Fixed Server-Rollen und die Berechtigungen, die Ihnen in SQL Server zugeordnet sind.|  
|[Rollen auf Datenbankebene](/sql/relational-databases/security/authentication-access/database-level-roles)|Beschreibt die festen Datenbankrollen und die mit ihnen verknüpften Berechtigungen.|  
  
## <a name="database-roles-and-users"></a>Datenbankrollen und Benutzer  
 Anmeldungen müssen Datenbankbenutzerkonten zugeordnet werden, damit das Arbeiten mit den Datenbankobjekten funktioniert. Anschließend können den Datenbankrollen Datenbankbenutzer hinzugefügt werden, die alle Berechtigungssätze erben, die mit diesen Rollen verknüpft sind. Alle Berechtigungen können erteilt werden.  
  
 Beim Entwickeln des Sicherheitskonzepts für Ihre Anwendung müssen Sie auch die Rolle `public`, das Benutzerkonto `dbo` und das `guest`-Konto berücksichtigen.  
  
### <a name="the-public-role"></a>Die Rolle "public"  
 Die Rolle `public` ist in jeder Datenbank mit Systemdatenbanken enthalten. Sie kann nicht gelöscht werden, und Sie können ihr weder Benutzer hinzufügen, noch Benutzer daraus entfernen. Die der Rolle `public` gewährten Berechtigungen werden von allen anderen Benutzern und Rollen geerbt, da sie standardmäßig zur Rolle `public` gehören. Gewähren Sie der Rolle `public` nur die Berechtigungen, die auch wirklich alle Benutzer haben sollen.  
  
### <a name="the-dbo-user-account"></a>Das "dbo"-Benutzerkonto  
 `dbo` (Database Owner, Datenbankbesitzer) ist ein Benutzerkonto, das implizite Berechtigungen zum Ausführen aller Aktivitäten in der Datenbank besitzt. Member der festen Serverrolle `sysadmin` werden automatisch dem `dbo`-Benutzerkonto zugeordnet.  
  
> [!NOTE]
> `dbo`ist auch der Name eines Schemas, wie unter [Besitz und Trennung von Benutzer und Schema in SQL Server](ownership-and-user-schema-separation-in-sql-server.md)erläutert.  
  
 Das `dbo`-Benutzerkonto wird häufig mit der festen Datenbankrolle `db_owner` verwechselt. Der Gültigkeitsbereich von `db_owner` umfasst eine Datenbank, während serverweit `sysadmin` gültig ist. Die Zugehörigkeit zur Rolle `db_owner` verleiht keine `dbo`-Benutzerrechte.  
  
### <a name="the-guest-user-account"></a>Das "guest"-Benutzerkonto  
 Nachdem ein Benutzer authentifiziert und als berechtigt eingestuft wurde, sich bei einer Instanz von SQL Server anzumelden, muss in jeder Datenbank, auf die der Benutzer zugreifen können soll, ein separates Benutzerkonto vorhanden sein. Auf diese Weise wird verhindert, dass Benutzer eine Verbindung mit einer SQL Server-Instanz herstellen und damit auf alle auf einem Server vorhandenen Datenbanken zugreifen können. Wenn in der Datenbank ein `guest`-Benutzerkonto vorhanden ist, gilt diese Anforderung nicht, und für den Datenbankzugriff reicht eine Anmeldung ohne ein Datenbankbenutzerkonto.  
  
 Das `guest`-Konto ist in allen Versionen von SQL Server ein integriertes Konto. In neuen Datenbanken ist es standardmäßig deaktiviert. Wenn es aktiviert ist, können Sie es deaktivieren, indem Sie dessen CONNECT-Berechtigung widerrufen. Führen Sie dazu die Transact-SQL-REVOKE CONNECT FROM GUEST-Anweisung aus.  
  
> [!IMPORTANT]
> Vermeiden Sie die Verwendung des `guest`-Kontos, denn alle Anmeldungen ohne eigene Datenbankberechtigungen erhalten die Datenbankberechtigungen, die diesem Konto gewährt wurden. Wenn Sie das `guest`-Konto verwenden müssen, gewähren Sie ihm nur minimale Berechtigungen.  
  
 Weitere Informationen zu SQL Server-Anmeldungen, -Benutzern und -Rollen finden Sie in den folgenden Ressourcen:  
  
|Resource|BESCHREIBUNG|  
|--------------|-----------------|  
|[Erste Schritte mit Berechtigungen für die Datenbank-Engine](/sql/relational-databases/security/authentication-access/getting-started-with-database-engine-permissions)|Enthält Links zu Themen, in denen Prinzipale, Rollen, Anmeldeinformationen, sicherungsfähige Elemente und Berechtigungen beschrieben werden.|  
|[Principals](/sql/relational-databases/security/authentication-access/principals-database-engine)|Beschreibt Prinzipale und enthält Links zu Themen, in denen Server- und Datenbankrollen beschrieben werden.|  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Authentifizierung in SQL Server](authentication-in-sql-server.md)
- [Objektbesitz und Trennung von Benutzer und Schema in SQL Server](ownership-and-user-schema-separation-in-sql-server.md)
- [Autorisierung und Berechtigungen in SQL Server](authorization-and-permissions-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
