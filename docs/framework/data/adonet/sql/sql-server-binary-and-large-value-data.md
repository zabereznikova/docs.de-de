---
title: "Binäre Daten und Daten mit umfangreichen Werten in SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9065f467cd353c17471db2c0d67001a188459819
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-binary-and-large-value-data"></a>Binäre Daten und Daten mit umfangreichen Werten in SQL Server
SQL Server umfasst den `max`-Bezeichner, der die Speicherkapazität für die Datentypen `varchar`, `nvarchar` und `varbinary` erhöht. `varchar(max)`, `nvarchar(max)`, und `varbinary(max)` werden insgesamt als *Datentypen mit umfangreichen Werten*. Sie können die Datentypen mit umfangreichen Werten zum Speichern von bis zu 2^31-1 Bytes an Daten verwenden.  
  
 In SQL Server 2008 wird das FILESTREAM-Attribut eingeführt. Es ist kein Datentyp, sondern eher ein Attribut, das für eine Spalte definiert werden kann, damit Daten mit umfangreichen Werten im Dateisystem statt in der Datenbank gespeichert werden können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Ändern von umfangreichen Werten (max) Daten in ADO.NET](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 Beschreibt das Arbeiten mit Datentypen für hohe Werte.  
  
 [FILESTREAM-Daten](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 Beschreibt die Verwendung von Datentypen für große Werte, die mit dem FILESTREAM-Attribut in SQL Server 2008 gespeichert wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
