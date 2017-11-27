---
title: CLR-Integrationssicherheit in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: de4f4b1ae5ba252778d9463cba43a9ccb419600a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="clr-integration-security-in-sql-server"></a>CLR-Integrationssicherheit in SQL Server
Die CLR (Common Language Runtime)-Komponente von .NET Framework ist in Microsoft SQL Server integriert. Dank CLR-Integration können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (Streaming Table-Valued Function, STVF) in jeder beliebigen .NET Framework-Sprache (wie Microsoft Visual Basic .NET oder Microsoft Visual C#) schreiben.  
  
 Die CLR unterstützt das Sicherheitsmodell der Codezugriffssicherheit (Code Access Security, CAS) für verwalteten Code. In diesem Modell werden Assemblys Berechtigungen auf der Basis des Codes in Metadaten gewährt. SQL Server sorgt für eine enge Zusammenarbeit zwischen dem SQL Server-Modell der benutzerbasierten Sicherheit und dem CLR-Modell der Codezugriffssicherheit.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen zur CLR-Integration mit SQL Server finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Codezugriffssicherheit](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)|Enthält Themen, in denen die CAS in .NET Framework beschrieben wird.|  
|[Sicherheit der CLR-Integration](http://go.microsoft.com/fwlink/?LinkId=59998)|Beschreibt das Sicherheitsmodell für verwalteten Code, der innerhalb von SQL Server ausgeführt wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Anwendungssicherheitsszenarios in SQLServer](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [SQL Server Common Language Runtime-Integration](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
