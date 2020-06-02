---
title: SQL Server und ADO.NET
description: Erfahren Sie mehr über Features und Verhalten der .NET Framework Datenanbieter für SQL Server, die datenbankspezifische Protokolle kapselt.
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: eeb0ab69a68dfc2fc0faa1b4e833f80b307fffe5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286442"
---
# <a name="sql-server-and-adonet"></a>SQL Server und ADO.NET
In diesem Abschnitt werden Funktionen und Verhaltensweisen beschrieben, die für den .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) spezifisch sind.  
  
 <xref:System.Data.SqlClient> bietet Zugriff auf SQL Server-Versionen, der datenbankspezifische Protokolle kapselt. Die Funktionen des Datenanbieters sind denen des .NET Framework-Datenanbieters für OLE DB, ODBC und Oracle angepasst. <xref:System.Data.SqlClient> beinhaltet einen TDS-Parser (Tabular Data Stream) für die direkte Kommunikation mit SQL Server.  
  
> [!NOTE]
> Damit eine Anwendung den .NET Framework-Datenanbieter für SQL Server verwenden kann, muss sie wie folgt auf den <xref:System.Data.SqlClient>-Namespace verweisen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SQL Server Sicherheit](sql-server-security.md)  
 Bietet eine Übersicht über die SQL Server-Sicherheitsfunktionen und Anwendungsszenarios zum Erstellen sicherer ADO.NET-Anwendungen, die auf SQL Server zugreifen.  
  
 [SQL Server-Datentypen und ADO.net](sql-server-data-types.md)  
 Beschreibt, wie mit SQL Server-Datentypen gearbeitet wird und wie die Interaktion mit .NET Framework-Datentypen aussieht.  
  
 [SQL Server von Binärdaten und Daten mit umfangreichen Werten](sql-server-binary-and-large-value-data.md)  
 Beschreibt das Arbeiten mit Daten mit umfangreichen Werten in SQL Server.  
  
 [SQL Server von Daten Vorgängen in ADO.net](sql-server-data-operations.md)  
 Beschreibt das Arbeiten mit Daten in SQL Server. Enthält Abschnitte zu Massenkopiervorgängen, MARS, asynchronen Vorgängen und Tabellenwertparametern.  
  
 [SQL Server Features und ADO.net](sql-server-features-and-adonet.md)  
 Beschreibt SQL Server-Features, die für ADO.NET-Anwendungsentwickler nützlich sind.  
  
 [LINQ to SQL](./linq/index.md)  
 Beschreibt die erforderlichen Grundbausteine, Prozesse und Techniken für das Erstellen von LINQ to SQL-Anwendungen.  
  
 Eine vollständige Dokumentation zur SQL Server-Datenbank-Engine finden Sie in der SQL Server-Onlinedokumentation für die SQL Server-Version, die Sie verwenden.  
  
 [SQL Server-Onlinedokumentation](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Datentypzuordnungen in ADO.NET](../data-type-mappings-in-ado-net.md)
- ["DataSets", "DataTables" und "DataViews"](../dataset-datatable-dataview/index.md)
- [Abrufen und Ändern von Daten in ADO.NET](../retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
