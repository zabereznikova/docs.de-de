---
title: Schreiben eines Entity Framework-Datenanbieters
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 6c5e6e2859b48db6c982862381d223a4c9deb2c5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248191"
---
# <a name="writing-an-entity-framework-data-provider"></a>Schreiben eines Entity Framework-Datenanbieters
In diesem Abschnitt wird erläutert, wie [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Sie einen Anbieter schreiben, um eine andere Datenquelle als SQL Server zu unterstützen. Enthält [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] einen Anbieter, der SQL Server unterstützt.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Einführung in das Entity Framework-Anbietermodell  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist Datenbank-unabhängig. Sie können mit dem ADO.NET-Anbietermodell einen Anbieter schreiben, um eine Verbindung mit verschiedenen Datenquellen herzustellen.  
  
 Der mit dem ADO.NET-Datenanbietermodell erstellte Entity Framework-Datenanbieter führt die folgenden Funktionen aus:  
  
- Zuordnen von primitiven Typen des Entity Data Model (EDM) zu Anbietertypen.  
  
- Bereitstellen von anbieterspezifischen Funktionen.  
  
- Generieren von anbieterspezifischen Befehlen für einen angegebenen DbQueryCommandTree zur Unterstützung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Abfragen.  
  
- Generieren von anbieterspezifischen Updatebefehlen für einen angegebenen DbModificationCommandTree zur Unterstützung von Updates durch den [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
- Bereitstellen von Zuordnungsdateien für die Speicherschemadefinition zur Unterstützung der Generierung eines Modells auf Grundlage einer Datenbank.  
  
- Bereitstellen von Metadaten (z. B. Tabellen und Sichten) über ein konzeptionelles Modell.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Beispiel  
 Ein Beispiel [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] für einen Anbieter, der eine andere Datenquelle als SQL Server unterstützt, finden Sie unter [Entity Framework-Beispiel Anbieter](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) .  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SQL-Generierung](sql-generation.md)  
  
 [Generierung von Änderungen in SQL](modification-sql-generation.md)  
  
 [Anbietermanifestspezifikation](provider-manifest-specification.md)  
  
## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Datenanbietern](working-with-data-providers.md)
