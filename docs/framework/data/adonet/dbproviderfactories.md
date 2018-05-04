---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 8692dc761f00e0ddc8ec9fad5a5df66b7fda7916
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="dbproviderfactories"></a>DbProviderFactories
Der <xref:System.Data.Common>-Namespace stellt Klassen zum Erstellen von <xref:System.Data.Common.DbProviderFactory>-Instanzen für die Arbeit mit bestimmten Datenquellen bereit. Wenn Sie eine <xref:System.Data.Common.DbProviderFactory>-Instanz erstellen und Informationen zum Anbieter an die Instanz übergeben, kann die `DbProviderFactory` auf der Grundlage der ihr bereitgestellten Informationen das korrekte, stark typisierte Verbindungsobjekt bestimmen, das zurückgegeben werden soll.  
  
 Ab .NET Framework Version 4 werden Datenanbieter wie <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient> nicht mehr in der machine.config-Datei aufgeführt, aber benutzerdefinierte Anbieter werden dort weiterhin aufgeführt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über das Factorymodell](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 Bietet eine Übersicht über das Factoryentwurfsmuster und die Programmierschnittstelle.  
  
 [Abrufen einer DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 Zeigt, wie die installierten Datenanbieter aufgelistet und aus einer <xref:System.Data.Common.DbConnection> eine `DbProviderFactory` erstellt werden kann.  
  
 [DbConnection, DbCommand und DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 Zeigt, wie ein <xref:System.Data.Common.DbCommand> und ein <xref:System.Data.Common.DbDataReader> erstellt und Datenfehler mit <xref:System.Data.Common.DbException> behandelt werden können.  
  
 [Ändern von Daten mit DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 Zeigt, wie mit einem <xref:System.Data.Common.DbCommandBuilder> und einem <xref:System.Data.Common.DbDataAdapter> Daten abgerufen und geändert werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
