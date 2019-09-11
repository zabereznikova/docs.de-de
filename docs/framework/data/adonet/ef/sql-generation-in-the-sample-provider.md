---
title: SQL-Generierung im Beispielanbieter
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: a59f1fecf85d63208c3388204c962b5838902ba7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854315"
---
# <a name="sql-generation-in-the-sample-provider"></a>SQL-Generierung im Beispielanbieter
Der [Entity Framework Beispiel Anbieter](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) veranschaulicht die neuen Komponenten von ADO.NET-Datenanbietern, die die Entity Framework unterstützen.  Es funktioniert mit einer SQL Server 2005-Datenbank und wird als Wrapper für den System.Data.SqlClient ADO.NET 2.0-Datenanbieter implementiert.  
  
 Das SQL-Generierungsmodul des Beispielanbieters (das sich abgesehen von der Datei DmlSqlGenerator.cs im Ordner SQL-Generierung befindet) verwendet einen Eingabe-DbQueryCommandTree und erzeugt eine einzelne SQL-SELECT-Anweisung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 Dieser Abschnitt schließt folgende Themen ein:  
  
 [Architektur und Entwurf](architecture-and-design.md)  
  
 [Exemplarische Vorgehensweise: SQL-Generierung](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>Siehe auch

- [SQL-Generierung](sql-generation.md)
