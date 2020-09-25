---
title: Binäre Daten und Daten mit umfangreichen Werten in SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: a9296e83b0f4e4352423470433670bb2cbe5a248
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183038"
---
# <a name="sql-server-binary-and-large-value-data"></a>Binäre Daten und Daten mit umfangreichen Werten in SQL Server

SQL Server stellt den `max`-Spezifizierer bereit, der die Speicherkapazität der Datentypen `varchar`, `nvarchar` und `varbinary` erweitert. `varchar(max)`, `nvarchar(max)` und `varbinary(max)` werden zusammenfassend als *Datentypen mit umfangreichen Werten* bezeichnet. Sie können die Datentypen mit umfangreichen Werten zum Speichern von bis zu 2^31-1 Bytes an Daten verwenden.  
  
 In SQL Server 2008 wurde das FILESTREAM-Attribut eingeführt, das kein Datentyp ist. Es ist ein Attribut, das für eine Spalte definiert werden kann, wodurch Daten mit umfangreichen Werten im Dateisystem anstatt in der Datenbank gespeichert werden können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Ändern von Daten mit umfangreichen Werten (max) in ADO.net](modifying-large-value-max-data.md)  
 Beschreibt das Arbeiten mit den Datentypen für große Werte.  
  
 [FILESTREAM-Daten](filestream-data.md)  
 Beschreibt, wie Sie mit Daten mit großen Werten arbeiten, die in SQL Server 2008 mit dem FILESTREAM-Attribut gespeichert sind.  
  
## <a name="see-also"></a>Weitere Informationen

- [SQL Server-Datentypen und ADO.NET](sql-server-data-types.md)
- [SQL Server von Daten Vorgängen in ADO.net](sql-server-data-operations.md)
- [Abrufen und Ändern von Daten in ADO.NET](../retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
