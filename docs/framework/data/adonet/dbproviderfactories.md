---
title: "&#39;DbProviderFactory&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# &#39;DbProviderFactory&#39;
Der <xref:System.Data.Common>\-Namespace stellt Klassen zum Erstellen von <xref:System.Data.Common.DbProviderFactory>\-Instanzen für die Arbeit mit bestimmten Datenquellen bereit.  Wenn Sie eine <xref:System.Data.Common.DbProviderFactory>\-Instanz erstellen und Informationen zum Anbieter an die Instanz übergeben, kann die `DbProviderFactory` auf der Grundlage der ihr bereitgestellten Informationen das korrekte, stark typisierte Verbindungsobjekt bestimmen, das zurückgegeben werden soll.  
  
 Ab .NET Framework Version 4 werden Datenanbieter wie <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient> nicht mehr in der machine.config\-Datei aufgeführt, aber benutzerdefinierte Anbieter werden dort weiterhin aufgeführt.  
  
## In diesem Abschnitt  
 [Übersicht über das Factorymodell](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 Bietet eine Übersicht über das Factoryentwurfsmuster und die Programmierschnittstelle.  
  
 [Abrufen einer 'DbProviderFactory'](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 Zeigt, wie die installierten Datenanbieter aufgelistet und aus einer `DbProviderFactory` eine <xref:System.Data.Common.DbConnection> erstellt werden kann.  
  
 ['DbConnection', 'DbCommand' und 'DbException'](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 Zeigt, wie ein <xref:System.Data.Common.DbCommand> und ein <xref:System.Data.Common.DbDataReader> erstellt und Datenfehler mit <xref:System.Data.Common.DbException> behandelt werden können.  
  
 [Ändern von Daten mit einem 'DbDataAdapter'](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 Zeigt, wie mit einem <xref:System.Data.Common.DbCommandBuilder> und einem <xref:System.Data.Common.DbDataAdapter> Daten abgerufen und geändert werden können.  
  
## Siehe auch  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)