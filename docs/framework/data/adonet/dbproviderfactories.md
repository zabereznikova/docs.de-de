---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: b5f2dbb687348afac98247cb21bae831dea26bfe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183311"
---
# <a name="dbproviderfactories"></a>DbProviderFactories

Der <xref:System.Data.Common>-Namespace stellt Klassen zum Erstellen von <xref:System.Data.Common.DbProviderFactory>-Instanzen für die Arbeit mit bestimmten Datenquellen bereit. Wenn Sie eine <xref:System.Data.Common.DbProviderFactory>-Instanz erstellen und Informationen zum Anbieter an die Instanz übergeben, kann die `DbProviderFactory` auf der Grundlage der ihr bereitgestellten Informationen das korrekte, stark typisierte Verbindungsobjekt bestimmen, das zurückgegeben werden soll.  
  
 Ab .NET Framework Version 4 werden Datenanbieter wie <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient> nicht mehr in der machine.config-Datei aufgeführt, aber benutzerdefinierte Anbieter werden dort weiterhin aufgeführt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Übersicht über das Factorymodell](factory-model-overview.md)  
 Bietet eine Übersicht über das Factoryentwurfsmuster und die Programmierschnittstelle.  
  
 [Abrufen einer "DbProviderFactory"](obtaining-a-dbproviderfactory.md)  
 Zeigt, wie die installierten Datenanbieter aufgelistet und aus einer <xref:System.Data.Common.DbConnection> eine `DbProviderFactory` erstellt werden kann.  
  
 ["DbConnection", "DbCommand" und "DbException"](dbconnection-dbcommand-and-dbexception.md)  
 Zeigt, wie ein <xref:System.Data.Common.DbCommand> und ein <xref:System.Data.Common.DbDataReader> erstellt und Datenfehler mit <xref:System.Data.Common.DbException> behandelt werden können.  
  
 [Ändern von Daten mit "DbDataAdapter"](modifying-data-with-a-dbdataadapter.md)  
 Zeigt, wie mit einem <xref:System.Data.Common.DbCommandBuilder> und einem <xref:System.Data.Common.DbDataAdapter> Daten abgerufen und geändert werden können.  
  
## <a name="see-also"></a>Weitere Informationen

- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
