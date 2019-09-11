---
title: SQL-Generierung
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854352"
---
# <a name="sql-generation"></a>SQL-Generierung
Wenn Sie einen Anbieter für das Entity Framework schreiben, müssen Sie Entity Framework Befehlsstrukturen in SQL übersetzen, die von einer bestimmten Datenbank verstanden werden können, z. b. Transact-SQL für SQL Server oder PL/SQL für Oracle. In diesem Abschnitt erfahren Sie, wie Sie eine SQL-Generierungs Komponente (für SELECT-Abfragen) für einen Entity Framework-Anbieter entwickeln. Weitere Informationen zu INSERT-, Update-und DELETE-Abfragen finden Sie unter [Ändern der SQL-Generierung](modification-sql-generation.md).  
  
 Um diesen Abschnitt zu verstehen, sollten Sie mit dem Entity Framework und dem ADO.NET-Anbieter Modell vertraut sein. Außerdem sollten Sie Befehlsstrukturen und <xref:System.Data.Common.CommandTrees.DbExpression> verstehen.  
  
## <a name="the-role-of-the-sql-generation-module"></a>Die Rolle des SQL-Generierungsmoduls  
 Das SQL-Generierungs Modul eines Entity Framework Anbieters übersetzt eine angegebene Abfrage Befehlsstruktur in eine einzelne SQL SELECT-Anweisung, die auf eine SQL: 1999-kompatible Datenbank abzielt. Das generierte SQL sollte so wenige geschachtelte Abfragen wie möglich enthalten. Das SQL-Generierungsmodul sollte die Ausgabeabfrage-Befehlsstruktur nicht vereinfachen. Dies wird durch den Entity Framework erfolgt, beispielsweise durch das Eliminieren von Joins und das reduzieren aufeinander folgender Filter Knoten.  
  
 Die <xref:System.Data.Common.DbProviderServices>-Klasse ist der Ausgangspunkt für den Zugriff auf die SQL-Generierungsebene zur Umwandlung von Befehlsstrukturen in <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Form der Befehlsstrukturen](the-shape-of-the-command-trees.md)  
  
 [Generieren von SQL aus Befehlsstrukturen: Bewährte Methoden](generating-sql-from-command-trees-best-practices.md)  
  
 [SQL-Generierung im Beispielanbieter](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>Siehe auch

- [Schreiben eines Entity Framework-Datenanbieters](writing-an-ef-data-provider.md)
