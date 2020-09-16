---
title: Gewähren zeilenspezifischer Berechtigungen in SQL Server
ms.date: 03/30/2017
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
ms.openlocfilehash: 0b34eaee4b66a2be82049816f0a98b9f53012303
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554852"
---
# <a name="granting-row-level-permissions-in-sql-server"></a>Gewähren zeilenspezifischer Berechtigungen in SQL Server

Es gibt Szenarien, in denen der Zugriff auf Daten genauer gesteuert werden muss, als dies durch einfaches Gewähren, Widerrufen oder Ablehnen von Berechtigungen möglich ist. Eine Anwendung für eine Krankenhausdatenbank kann z. B. für einzelne Ärzte erfordern, dass diese jeweils nur auf Daten der eigenen Patienten zugreifen dürfen. Ähnliche Anforderungen gibt es in vielen Umgebungen, vom Finanzwesen über die Justiz und die Behörden bis hin zum militärischen Bereich. SQL Server 2016 bietet ein Feature für die [zeilenbasierte Sicherheit](/sql/relational-databases/security/row-level-security) , die die zeilenbasierte Zugriffslogik in einer Sicherheitsrichtlinie vereinfacht und zentralisiert, um diese Szenarien besser zu unterstützen. Frühere Versionen von SQL Server können mithilfe von Ansichten eine ähnliche Funktionalität erreichen, um die Filterung auf Zeilenebene zu ermöglichen.

## <a name="implementing-row-level-filtering"></a>Implementieren der zeilenbasierter Filterung

Die zeilenbasierte Filterung wird für Anwendungen verwendet, die Informationen in einer einzelnen Tabelle wie im obigen Krankenhausbeispiel speichern. Um die zeilenbasierte Filterung zu implementieren, besitzt jede Zeile eine Spalte, die ein Unterscheidungsmerkmal (Differenzierungsparameter) definiert, z. B. den Benutzernamen, die Menge oder ein anderes Identifizierungsmerkmal. Sie erstellen entweder eine Sicherheitsrichtlinie oder eine Sicht auf die Tabelle, die die Zeilen filtert, auf die der Benutzer zugreifen kann. Sie können dann parametrisierte gespeicherte Prozeduren erstellen, die die Typen von Abfragen steuern, die vom Benutzer ausgeführt werden können.

Das folgende Beispiel beschreibt, wie die zeilenbasierte Filterung auf der Grundlage eines Benutzer- oder Anmeldenamens konfiguriert werden kann.

- Erstellen Sie die Tabelle, und fügen Sie eine Spalte zum Speichern des Namens hinzu.

- Aktivieren der zeilenbasierten Filterung:

  - Bei Verwendung von SQL Server 2016 oder höher oder [Azure SQL-Datenbank](/azure/sql-database/)erstellen Sie eine Sicherheitsrichtlinie, die der Tabelle ein Prädikat hinzufügt, das die Zeilen auf diejenigen einschränkt, die entweder mit dem aktuellen Datenbankbenutzer (mithilfe der integrierten CURRENT_USER()-Funktion) oder mit dem aktuellen Anmeldenamen (mithilfe der integrierten SUSER_SNAME()-Funktion) übereinstimmen:

      ```sql
      CREATE SCHEMA Security
      GO

      CREATE FUNCTION Security.userAccessPredicate(@UserName sysname)
          RETURNS TABLE
          WITH SCHEMABINDING
      AS
          RETURN SELECT 1 AS accessResult
          WHERE @UserName = SUSER_SNAME()
      GO

      CREATE SECURITY POLICY Security.userAccessPolicy
          ADD FILTER PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable,
          ADD BLOCK PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable
      GO
      ```

  - Wenn Sie eine Vorgängerversion von SQL Server 2016 verwenden, können Sie eine ähnliche Funktionalität mithilfe einer Sicht erzielen:

      ```sql
      CREATE VIEW vw_MyTable
      AS
          RETURN SELECT * FROM MyTable
          WHERE UserName = SUSER_SNAME()
      GO
      ```

- Erstellen Sie gespeicherte Prozeduren, um Daten auszuwählen, einzufügen, zu aktualisieren und zu löschen. Wenn die Filterung mithilfe einer Sicherheitsrichtlinie durchgeführt wird, sollten die gespeicherten Prozeduren diese Vorgänge direkt mit der Basistabelle durchführen. Wenn die Filterung mithilfe einer Sicht durchgeführt wird, sollten die gespeicherten Prozeduren stattdessen mit der Sicht arbeiten. Die Sicherheitsrichtlinie oder Sicht filtert die durch Benutzerabfragen zurückgegebenen oder geänderten Zeilen automatisch, und die gespeicherte Prozedur bietet eine stärkere Sicherheitsgrenze, um zu verhindern, dass Benutzer mit direktem Zugriff auf die Abfragen erfolgreich Abfragen ausführen, die die Existenz gefilterter Daten ableiten können.

- Erfassen Sie bei gespeicherten Prozeduren, die Daten einfügen, den Benutzernamen mit der in der Sicherheitsrichtlinie oder Sicht angegebenen Funktion, und fügen Sie diesen Wert in die Spalte „UserName“ ein.

- Verweigern Sie der Rolle `public` alle Berechtigungen für die Tabellen (und Sichten, falls zutreffend). Die Benutzer können keine Berechtigungen aus anderen Datenbankrollen erben, weil das Filterprädikat nicht auf Rollen, sondern auf Benutzer- oder Anmeldenamen basiert.

- Gewähren Sie den Datenbankrollen die Berechtigung EXECUTE für die gespeicherten Prozeduren. Die Benutzer können nur auf Daten zugreifen, die über die gespeicherten Prozeduren bereitgestellt werden.

## <a name="see-also"></a>Siehe auch

- [Sicherheit auf Zeilenebene](/sql/relational-databases/security/row-level-security)
- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Übersicht über die SQL Server-Sicherheit](overview-of-sql-server-security.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Schreiben von sicherem dynamischem SQL in SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
