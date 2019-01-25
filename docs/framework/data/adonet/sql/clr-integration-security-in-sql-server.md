---
title: CLR-Integrationssicherheit in SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: af3ec1f8dba375082a9838f10fa63c9348f725b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681052"
---
# <a name="clr-integration-security-in-sql-server"></a>CLR-Integrationssicherheit in SQL Server
Die CLR (Common Language Runtime)-Komponente von .NET Framework ist in Microsoft SQL Server integriert. Dank CLR-Integration können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (Streaming Table-Valued Function, STVF) in jeder beliebigen .NET Framework-Sprache (wie Microsoft Visual Basic .NET oder Microsoft Visual C#) schreiben.  
  
 Die CLR unterstützt das Sicherheitsmodell der Codezugriffssicherheit (Code Access Security, CAS) für verwalteten Code. In diesem Modell werden Assemblys Berechtigungen auf der Basis des Codes in Metadaten gewährt. SQL Server sorgt für eine enge Zusammenarbeit zwischen dem SQL Server-Modell der benutzerbasierten Sicherheit und dem CLR-Modell der Codezugriffssicherheit.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen zur CLR-Integration mit SQL Server finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Codezugriffssicherheit](../../../../../docs/framework/misc/code-access-security.md)|Enthält Themen, in denen die CAS in .NET Framework beschrieben wird.|  
|[Sicherheit der CLR-Integration](/sql/relational-databases/clr-integration/security/clr-integration-security)|Beschreibt das Sicherheitsmodell für verwalteten Code, der innerhalb von SQL Server ausgeführt wird.|  
  
## <a name="see-also"></a>Siehe auch
- [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [Common Language Runtime-Integration in SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)
- [Übersicht über ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)
