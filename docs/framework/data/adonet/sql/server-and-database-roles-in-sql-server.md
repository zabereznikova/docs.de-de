---
title: Server- und Datenbankrollen in SQL Server
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5482dfdb-e498-4614-8652-b174829eed13
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b650c61a8d3d0b457bc9d5232c613d47f36ccbfc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="server-and-database-roles-in-sql-server"></a>Server- und Datenbankrollen in SQL Server
Alle SQL Server-Versionen verwenden die rollenbasierte Sicherheit, mit der Sie einer Rolle, also einer ganzen Gruppe von Benutzern, Berechtigungen zuweisen können, statt Berechtigungen individuell für jeden Benutzer einzeln festzulegen. Feste Server- und feste Datenbankrollen besitzen einen festen Satz von ihnen übertragenen Berechtigungen.  
  
## <a name="fixed-server-roles"></a>Feste Serverrollen  
 Feste Serverrollen besitzen einen festen Satz von Berechtigungen, die serverweit gültig sind. Sie sind zur Verwaltung von SQL Server gedacht, und die ihnen zugewiesenen Berechtigungen können nicht geändert werden. Anmeldungen können festen Serverrollen zugewiesen sein, ohne dass in einer Datenbank ein Benutzerkonto vorhanden ist.  
  
> [!IMPORTANT]
>  Die feste Serverrolle `sysadmin` schließt alle anderen Rollen ein und kennt keine Einschränkungen. Fügen Sie dieser Rolle keine Prinzipale hinzu, außer wenn ihre Vertrauenswürdigkeit sehr hoch ist. Mitglieder der Rolle `sysadmin` verfügen über unwiderrufliche Administratorberechtigungen für alle Serverdatenbanken und -ressourcen.  
  
 Gehen Sie beim Hinzufügen von Benutzern zu festen Serverrollen mit großer Sorgfalt vor. So können z. B. Benutzer mit der Rolle `bulkadmin` den Inhalt einer beliebigen lokalen Datei in eine Tabelle einfügen, wodurch die Datenintegrität gefährdet werden könnte. Die vollständige Liste der festen Serverrollen und Berechtigungen finden Sie in der SQL Server-Onlinedokumentation.  
  
## <a name="fixed-database-roles"></a>Feste Datenbankrollen  
 Feste Datenbankrollen besitzen einen vordefinierten Satz von Berechtigungen, mit denen Sie problemlos ganze Berechtigungsgruppen verwalten können. Member der Rolle `db_owner` können alle Konfigurations- und Wartungsaktivitäten an der Datenbank ausführen.  
  
 Weitere Informationen zu den vordefinierten SQL Server-Rollen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Rollen auf Serverebene](http://msdn.microsoft.com/library/ms188659.aspx) und [Berechtigungen fester Serverrollen](http://msdn.microsoft.com/library/ms175892.aspx) in SQL Server-Onlinedokumentation|Beschreibt feste Serverrollen und die Berechtigungen in SQL Server zugeordnet.|  
|[Rollen auf Datenbankebene](http://msdn.microsoft.com/library/ms189121.aspx) und [Berechtigungen fester Datenbankrollen](http://msdn.microsoft.com/library/ms189612.aspx) in SQL Server-Onlinedokumentation|Beschreibt die festen Datenbankrollen und die mit ihnen verknüpften Berechtigungen.|  
  
## <a name="database-roles-and-users"></a>Datenbankrollen und Benutzer  
 Anmeldungen müssen Datenbankbenutzerkonten zugeordnet werden, damit das Arbeiten mit den Datenbankobjekten funktioniert. Anschließend können den Datenbankrollen Datenbankbenutzer hinzugefügt werden, die alle Berechtigungssätze erben, die mit diesen Rollen verknüpft sind. Alle Berechtigungen können erteilt werden.  
  
 Beim Entwickeln des Sicherheitskonzepts für Ihre Anwendung müssen Sie auch die Rolle `public`, das Benutzerkonto `dbo` und das `guest`-Konto berücksichtigen.  
  
### <a name="the-public-role"></a>Die Rolle "public"  
 Die Rolle `public` ist in jeder Datenbank mit Systemdatenbanken enthalten. Sie kann nicht gelöscht werden, und Sie können ihr weder Benutzer hinzufügen, noch Benutzer daraus entfernen. Die der Rolle `public` gewährten Berechtigungen werden von allen anderen Benutzern und Rollen geerbt, da sie standardmäßig zur Rolle `public` gehören. Gewähren Sie der Rolle `public` nur die Berechtigungen, die auch wirklich alle Benutzer haben sollen.  
  
### <a name="the-dbo-user-account"></a>Das "dbo"-Benutzerkonto  
 `dbo` (Database Owner, Datenbankbesitzer) ist ein Benutzerkonto, das implizite Berechtigungen zum Ausführen aller Aktivitäten in der Datenbank besitzt. Member der festen Serverrolle `sysadmin` werden automatisch dem `dbo`-Benutzerkonto zugeordnet.  
  
> [!NOTE]
>  `dbo` ist auch der Name eines Schemas, wie beschrieben in [Objektbesitz und Trennung von Benutzer und Schema in SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md).  
  
 Das `dbo`-Benutzerkonto wird häufig mit der festen Datenbankrolle `db_owner` verwechselt. Der Gültigkeitsbereich von `db_owner` umfasst eine Datenbank, während serverweit `sysadmin` gültig ist. Die Zugehörigkeit zur Rolle `db_owner` verleiht keine `dbo`-Benutzerrechte.  
  
### <a name="the-guest-user-account"></a>Das "guest"-Benutzerkonto  
 Nachdem ein Benutzer authentifiziert und als berechtigt eingestuft wurde, sich bei einer Instanz von SQL Server anzumelden, muss in jeder Datenbank, auf die der Benutzer zugreifen können soll, ein separates Benutzerkonto vorhanden sein. Auf diese Weise wird verhindert, dass Benutzer eine Verbindung mit einer SQL Server-Instanz herstellen und damit auf alle auf einem Server vorhandenen Datenbanken zugreifen können. Wenn in der Datenbank ein `guest`-Benutzerkonto vorhanden ist, gilt diese Voraussetzung nicht, und für den Datenbankzugriff reicht eine Anmeldung ohne ein Datenbankbenutzerkonto.  
  
 Das `guest`-Konto ist in allen Versionen von SQL Server ein integriertes Konto. In neuen Datenbanken ist es standardmäßig deaktiviert. Wenn es aktiviert ist, können Sie es deaktivieren, indem Sie dessen CONNECT-Berechtigung widerrufen. Führen Sie dazu die Transact-SQL-REVOKE CONNECT FROM GUEST-Anweisung aus.  
  
> [!IMPORTANT]
>  Vermeiden Sie die Verwendung des `guest`-Kontos, denn alle Anmeldungen ohne eigene Datenbankberechtigungen erhalten die Datenbankberechtigungen, die diesem Konto gewährt wurden. Wenn Sie das `guest`-Konto verwenden müssen, gewähren Sie ihm nur minimale Berechtigungen.  
  
 Weitere Informationen zu SQL Server-Anmeldungen, -Benutzern und -Rollen finden Sie in den folgenden Ressourcen:  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Identität und Zugriffssteuerung](http://msdn.microsoft.com/library/bb510418.aspx) in SQL Server-Onlinedokumentation|Enthält Links zu Themen, in denen Prinzipale, Rollen, Anmeldeinformationen, sicherungsfähige Elemente und Berechtigungen beschrieben werden.|  
|[Prinzipale](http://msdn.microsoft.com/library/ms181127.aspx) in SQL Server-Onlinedokumentation|Beschreibt Prinzipale und enthält Links zu Themen, in denen Server- und Datenbankrollen beschrieben werden.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Authentifizierung in SQL Server](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [Objektbesitz und Trennung von Benutzer und Schema in SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 [Autorisierung und Berechtigungen in SQL Server](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
