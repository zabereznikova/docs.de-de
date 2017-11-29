---
title: Schreiben eines Entity Framework-Datenanbieters
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6cbb6d4c11c06c1771cb32021c6c148564a6034a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="writing-an-entity-framework-data-provider"></a>Schreiben eines Entity Framework-Datenanbieters
In diesem Abschnitt wird erläutert, wie ein [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anbieter zur Unterstützung einer anderen Datenquelle als [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] geschrieben wird. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält einen Anbieter, der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] unterstützt.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Einführung in das Entity Framework-Anbietermodell  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist Datenbank-unabhängig. Sie können mit dem ADO.NET-Anbietermodell einen Anbieter schreiben, um eine Verbindung mit verschiedenen Datenquellen herzustellen.  
  
 Der mit dem ADO.NET-Datenanbietermodell erstellte Entity Framework-Datenanbieter führt die folgenden Funktionen aus:  
  
-   Zuordnen von primitiven Typen des Entity Data Model (EDM) zu Anbietertypen.  
  
-   Bereitstellen von anbieterspezifischen Funktionen.  
  
-   Generieren von anbieterspezifischen Befehlen für einen angegebenen DbQueryCommandTree zur Unterstützung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Abfragen.  
  
-   Generieren von anbieterspezifischen Updatebefehlen für einen angegebenen DbModificationCommandTree zur Unterstützung von Updates durch den [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
-   Bereitstellen von Zuordnungsdateien für die Speicherschemadefinition zur Unterstützung der Generierung eines Modells auf Grundlage einer Datenbank.  
  
-   Bereitstellen von Metadaten (z. B. Tabellen und Sichten) über ein konzeptionelles Modell.  
  
 ![b42a7a5c &#45; 0ac0 &#45;4911 &#45; 86be &#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Beispiel  
 Finden Sie unter der [Entity Framework-Beispielanbieter](http://go.microsoft.com/fwlink/?LinkId=180616) ein Beispiel für eine [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Anbieter, der eine Datenquelle außer unterstützt [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SQL-Generierung](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [SQL-Generierung von Änderungen](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [Anbietermanifestspezifikation](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Datenanbietern](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
