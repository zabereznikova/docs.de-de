---
title: CLR-Integrationssicherheit in SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 4756d13ff52a4c55b48c3ea56d26111029c8a7e4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794559"
---
# <a name="clr-integration-security-in-sql-server"></a>CLR-Integrationssicherheit in SQL Server
Die CLR (Common Language Runtime)-Komponente von .NET Framework ist in Microsoft SQL Server integriert. Dank CLR-Integration können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (Streaming Table-Valued Function, STVF) in jeder beliebigen .NET Framework-Sprache (wie Microsoft Visual Basic .NET oder Microsoft Visual C#) schreiben.  
  
 Die CLR unterstützt das Sicherheitsmodell der Codezugriffssicherheit (Code Access Security, CAS) für verwalteten Code. In diesem Modell werden Assemblys Berechtigungen auf der Basis des Codes in Metadaten gewährt. SQL Server sorgt für eine enge Zusammenarbeit zwischen dem SQL Server-Modell der benutzerbasierten Sicherheit und dem CLR-Modell der Codezugriffssicherheit.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen zur CLR-Integration mit SQL Server finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Codezugriffssicherheit](../../../misc/code-access-security.md)|Enthält Themen, in denen die CAS in .NET Framework beschrieben wird.|  
|[Sicherheit der CLR-Integration](/sql/relational-databases/clr-integration/security/clr-integration-security)|Beschreibt das Sicherheitsmodell für verwalteten Code, der innerhalb von SQL Server ausgeführt wird.|  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Common Language Runtime-Integration in SQL Server](sql-server-common-language-runtime-integration.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
