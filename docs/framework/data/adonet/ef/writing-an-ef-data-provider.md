---
title: Schreiben eines Entity Framework-Datenanbieters
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854162"
---
# <a name="writing-an-entity-framework-data-provider"></a>Schreiben eines Entity Framework-Datenanbieters
In diesem Abschnitt wird erläutert, wie Sie einen Entity Framework-Anbieter schreiben, um eine andere Datenquelle als SQL Server zu unterstützen. Die Entity Framework enthält einen Anbieter, der SQL Server unterstützt.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Einführung in das Entity Framework-Anbietermodell  
 Der Entity Framework ist datenbankunabhängig, und Sie können einen Anbieter mithilfe des ADO.NET-Anbieter Modells schreiben, um eine Verbindung mit einer Vielzahl von Datenquellen herzustellen.  
  
 Der mit dem ADO.NET-Datenanbietermodell erstellte Entity Framework-Datenanbieter führt die folgenden Funktionen aus:  
  
- Zuordnen von primitiven Typen des Entity Data Model (EDM) zu Anbietertypen.  
  
- Bereitstellen von anbieterspezifischen Funktionen.  
  
- Generiert anbieterspezifische Befehle für eine angegebene DbQueryCommandTree, um Entity Framework Abfragen zu unterstützen.  
  
- Generiert anbieterspezifische Aktualisierungs Befehle für eine angegebene DbModificationCommandTree, um Updates durch die Entity Framework zu unterstützen.  
  
- Bereitstellen von Zuordnungsdateien für die Speicherschemadefinition zur Unterstützung der Generierung eines Modells auf Grundlage einer Datenbank.  
  
- Bereitstellen von Metadaten (z. B. Tabellen und Sichten) über ein konzeptionelles Modell.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Beispiel  
 Eine Stichprobe eines Entity Framework Anbieters, der eine andere Datenquelle als SQL Server unterstützt, finden Sie unter [Entity Framework Beispiel Anbieter](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) .  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SQL-Generierung](sql-generation.md)  
  
 [Generierung von Änderungen in SQL](modification-sql-generation.md)  
  
 [Anbietermanifestspezifikation](provider-manifest-specification.md)  
  
## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Datenanbietern](working-with-data-providers.md)
