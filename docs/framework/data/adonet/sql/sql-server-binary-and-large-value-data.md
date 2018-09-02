---
title: Binäre Daten und Daten mit umfangreichen Werten in SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 9ebbe23dfbcac7825ce449dd40f62b921d13ab4a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466197"
---
# <a name="sql-server-binary-and-large-value-data"></a>Binäre Daten und Daten mit umfangreichen Werten in SQL Server
SQL Server umfasst den `max`-Bezeichner, der die Speicherkapazität für die Datentypen `varchar`, `nvarchar` und `varbinary` erhöht. `varchar(max)`, `nvarchar(max)`, und `varbinary(max)` werden zusammenfassend als bezeichnet *Datentypen mit umfangreichen Werten*. Sie können die Datentypen mit umfangreichen Werten zum Speichern von bis zu 2^31-1 Bytes an Daten verwenden.  
  
 In SQL Server 2008 wird das FILESTREAM-Attribut eingeführt. Es ist kein Datentyp, sondern eher ein Attribut, das für eine Spalte definiert werden kann, damit Daten mit umfangreichen Werten im Dateisystem statt in der Datenbank gespeichert werden können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Ändern von Daten mit umfangreichen Werten (max) in ADO.NET](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 Beschreibt das Arbeiten mit Datentypen für hohe Werte.  
  
 [FILESTREAM-Daten](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 Beschreibt die Verwendung von Datentypen für große Werte, die mit dem FILESTREAM-Attribut in SQL Server 2008 gespeichert wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
