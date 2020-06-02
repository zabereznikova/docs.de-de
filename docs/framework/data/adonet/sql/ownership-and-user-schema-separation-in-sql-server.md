---
title: Objektbesitz und Trennung von Benutzer und Schema in SQL Server
description: Erfahren Sie, wie Sie durch die Trennung von Benutzer Schemas Flexibilität beim Verwalten von SQL Server Berechtigungen für Datenbankobjekte Schemas gruppieren Objekte in separaten Namespaces.
ms.date: 03/30/2017
ms.assetid: 242830c1-31b5-4427-828c-cc22ff339f30
ms.openlocfilehash: 97e742979785fedd922dc887295b63e2d93bd147
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286261"
---
# <a name="ownership-and-user-schema-separation-in-sql-server"></a>Objektbesitz und Trennung von Benutzer und Schema in SQL Server
Eines der Hauptkonzepte der SQL Server-Sicherheit besteht darin, dass die Besitzer von Objekten unwiderrufbare Berechtigungen für deren Verwaltung besitzen. Es ist nicht möglich, dem Besitzer eines Objekts dessen Privilegien zu entziehen, und Sie können auch keine Besitzer aus der Datenbank entfernen, wenn diese Objekte in der Datenbank besitzen.  
  
## <a name="user-schema-separation"></a>Trennung von Benutzer und Schema  
 Durch die Trennung von Benutzer und Schema können die Berechtigungen für Datenbankobjekte flexibler verwaltet werden. Ein *Schema* ist ein benannter Container für Datenbankobjekte, der es Ihnen ermöglicht, Objekte in separaten Namespaces zu gruppieren. So enthält die AdventureWorks-Beispieldatenbank z. B. Schemas wie Production, Sales und HumanResources.  
  
 Die vierteilige Benennungssyntax zum Verweisen auf Objekte gibt den Schemanamen an.  
  
```text
Server.Database.DatabaseSchema.DatabaseObject  
```  
  
### <a name="schema-owners-and-permissions"></a>Schemabesitzer und Berechtigungen  
 Schemas können jedem beliebigen Datenbankprinzipal gehören, und ein einzelner Prinzipal kann Besitzer mehrerer Schemas sein. Sie können Sicherheitsregeln auf ein Schema anwenden, die dann von allen Objekten im Schema geerbt werden. Wenn Sie die Zugriffsberechtigungen für ein Schema eingerichtet haben, werden diese Berechtigungen automatisch auf alle neuen Objekte angewendet, die dem Schema hinzugefügt werden. Benutzer können einem Standardschema zugewiesen werden, und mehrere Datenbankbenutzer können gemeinsam dasselbe Schema verwenden.  
  
 Wenn Entwickler Objekte in einem Schema erstellen, gehen diese Objekte standardmäßig nicht in den Besitz des Entwicklers über, sondern in den Besitz des Sicherheitsprinzipals, dem das Schema gehört. Der Objektbesitz kann mit der Transact-SQL-ALTER AUTHORIZATION-Anweisung übertragen werden. Ein Schema kann auch Objekte enthalten, die unterschiedlichen Besitzern gehören und im Vergleich zu den dem Schema zugewiesenen Berechtigungen detailliertere Berechtigungen besitzen. Eine solche Strukturierung wird jedoch nicht empfohlen, da sie die Verwaltung der Berechtigungen erschwert. Objekte können zwischen Schemas verschoben werden, und der Schemabesitz kann zwischen den Prinzipalen übertragen werden. Datenbankbenutzer lassen sich löschen, ohne dass sich dies auf die Schemas auswirkt.  
  
### <a name="built-in-schemas"></a>Integrierte Schemas  
 SQL Server enthält zehn vordefinierte Schemas, deren Namen mit den integrierten Datenbankbenutzern und Rollen übereinstimmen. Diese Schemas wurden hauptsächlich aus Gründen der Abwärtskompatibilität bereitgestellt. Sie können die Schemas, die denselben Namen wie die festen Datenbankrollen haben, löschen, wenn Sie sie nicht benötigen. Die folgenden Schemas können nicht gelöscht werden:  
  
- `dbo`  
  
- `guest`  
  
- `sys`  
  
- `INFORMATION_SCHEMA`  
  
 Wenn Sie sie aus der Modelldatenbank entfernen, werden sie in neuen Datenbanken nicht mehr angezeigt.  
  
> [!NOTE]
> Die Schemas `sys` und `INFORMATION_SCHEMA` sind für Systemobjekte reserviert. Sie können in diesen Schemas keine Objekte erstellen, und Sie können die Schemas nicht löschen.  
  
#### <a name="the-dbo-schema"></a>Das "dbo"-Schema  
 Das `dbo`-Schema ist das Standardschema für neu erstellte Datenbanken. Das `dbo`-Schema gehört dem `dbo`-Benutzerkonto. Für Benutzer, die mit dem Transact-SQL-CREATE USER-Befehl erstellt werden, ist `dbo` standardmäßig das Standardschema.  
  
 Benutzer, denen das `dbo`-Schema zugewiesen ist, erben nicht die Berechtigungen des `dbo`-Benutzerkontos. Es werden keine Berechtigungen aus einem Schema an die Benutzer vererbt; die Schemaberechtigungen werden von den im Schema enthaltenen Datenbankobjekten geerbt.  
  
> [!NOTE]
> Wenn mit einem einteiligen Namen auf Datenbankobjekte verwiesen wird, durchsucht SQL Server zunächst das Standardschema des Benutzers. Wenn das Objekt dort nicht gefunden wird, sucht SQL Server als Nächstes im `dbo`-Schema. Wenn sich das Objekt nicht im `dbo`-Schema befindet, wird eine Fehlermeldung zurückgegeben.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen zu Objektbesitz und Schemas finden Sie in den folgenden Ressourcen:  
  
|Resource|BESCHREIBUNG|  
|--------------|-----------------|  
|[Trennung von Benutzer und Schema](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))|Beschreibt die Änderungen, die die Trennung von Benutzer und Schema zur Folge hat. Enthält Informationen zum neuen Verhalten, seinen Auswirkungen auf den Objektbesitz, zu Katalogsichten und zu Berechtigungen.|  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Authentifizierung in SQL Server](authentication-in-sql-server.md)
- [Server- und Datenbankrollen in SQL Server](server-and-database-roles-in-sql-server.md)
- [Autorisierung und Berechtigungen in SQL Server](authorization-and-permissions-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
