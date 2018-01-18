---
title: "Übersicht über das Factorymodell"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0194cd6789ae6ddebeeee65abf1a4fca4a2bc0d6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="factory-model-overview"></a>Übersicht über das Factorymodell
In ADO.NET 2.0 wurden im <xref:System.Data.Common>-Namespace neue Basisklassen eingeführt. Die Basisklassen sind abstrakt, können also nicht direkt instanziiert werden. Zu ihnen gehören die Basisklassen <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand> und <xref:System.Data.Common.DbDataAdapter>. Sie werden von den .NET Framework-Datenanbietern, z. B. <xref:System.Data.SqlClient> und <xref:System.Data.OleDb>, gemeinsam genutzt. Die neuen Basisklassen vereinfachen das Hinzufügen neuer Funktionen zu den .NET Framework-Datenanbietern, ohne dass dazu neue Schnittstellen erstellt werden müssen.  
  
 Außerdem wurden abstrakte Basisklassen in ADO.NET 2.0 eingeführt, mit denen Entwickler in der Lage sind, generischen Datenzugriffscode zu schreiben, der datenanbieterunabhängig ist.  
  
## <a name="the-factory-design-pattern"></a>Das Factoryentwurfsmuster  
 Das Programmiermodell zum Schreiben anbieterunabhängigen Codes basiert auf der Verwendung des Factoryentwurfsmusters, das für den Zugriff auf Datenbanken mehrerer Anbieter eine einzige API vewendet. Dieses Muster ist geeignet benannt, da es die Verwendung eines spezialisierten Objekts nur zum Erstellen anderer Objekte bedingt, wie in einer realen Produktionsumgebung. Eine ausführlichere Beschreibung des Factoryentwurfsmusters finden Sie unter "[Schreiben von generischem Datenzugriffscode in ASP.NET 2.0 und ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" und "Generische Codierung mit den ADO.NET 2.0 Base Klassen und-Factorys" [http:// MSDN.Microsoft.com/library/default.asp?url=/library/dnvs05/HTML/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) auf MSDN.  
  
 Ab ADO.NET 2.0 stellt die <xref:System.Data.Common.DbProviderFactories>-Klasse zum Erstellen einer `static`-Instanz `Shared`-Methoden (in Visual Basic <xref:System.Data.Common.DbProviderFactory>-Methoden) bereit. Die Instanz gibt dann anhand der Anbieterinformationen und der zur Laufzeit bereitgestellten Verbindungszeichenfolge ein korrektes, stark typisiertes Objekt zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Abrufen einer DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [DbConnection, DbCommand und DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [Ändern von Daten mit DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
