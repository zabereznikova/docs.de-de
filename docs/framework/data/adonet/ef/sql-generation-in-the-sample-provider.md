---
title: SQL-Generierung im Beispielanbieter
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: d0e058cdc4dd3f7a1a04ab6eea5acf4d3deabb89
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248512"
---
# <a name="sql-generation-in-the-sample-provider"></a>SQL-Generierung im Beispielanbieter
Der [Entity Framework Beispiel Anbieter](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) veranschaulicht die neuen Komponenten von ADO.NET-Datenanbietern, die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]unterstützen.  Es funktioniert mit einer SQL Server 2005-Datenbank und wird als Wrapper für den System.Data.SqlClient ADO.NET 2.0-Datenanbieter implementiert.  
  
 Das SQL-Generierungsmodul des Beispielanbieters (das sich abgesehen von der Datei DmlSqlGenerator.cs im Ordner SQL-Generierung befindet) verwendet einen Eingabe-DbQueryCommandTree und erzeugt eine einzelne SQL-SELECT-Anweisung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 Dieser Abschnitt schließt folgende Themen ein:  
  
 [Architektur und Entwurf](architecture-and-design.md)  
  
 [Exemplarische Vorgehensweise: SQL-Generierung](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>Siehe auch

- [SQL-Generierung](sql-generation.md)
