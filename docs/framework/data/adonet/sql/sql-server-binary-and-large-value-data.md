---
title: Binäre Daten und Daten mit umfangreichen Werten in SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 4d941ad6b7865112b45fd8c20ad89e9236e17b9d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791675"
---
# <a name="sql-server-binary-and-large-value-data"></a>Binäre Daten und Daten mit umfangreichen Werten in SQL Server
SQL Server umfasst den `max`-Bezeichner, der die Speicherkapazität für die Datentypen `varchar`, `nvarchar` und `varbinary` erhöht. `varchar(max)`, `nvarchar(max)` und`varbinary(max)` werden zusammen mit *Datentypen mit umfangreichen Werten*bezeichnet. Sie können die Datentypen mit umfangreichen Werten zum Speichern von bis zu 2^31-1 Bytes an Daten verwenden.  
  
 In SQL Server 2008 wird das FILESTREAM-Attribut eingeführt. Es ist kein Datentyp, sondern eher ein Attribut, das für eine Spalte definiert werden kann, damit Daten mit umfangreichen Werten im Dateisystem statt in der Datenbank gespeichert werden können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Ändern von Daten mit umfangreichen Werten (max) in ADO.NET](modifying-large-value-max-data.md)  
 Beschreibt das Arbeiten mit Datentypen für hohe Werte.  
  
 [FILESTREAM-Daten](filestream-data.md)  
 Beschreibt die Verwendung von Datentypen für große Werte, die mit dem FILESTREAM-Attribut in SQL Server 2008 gespeichert wurden.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](sql-server-data-types.md)
- [SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)](sql-server-data-operations.md)
- [Abrufen und Ändern von Daten in ADO.NET](../retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
