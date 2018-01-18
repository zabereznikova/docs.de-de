---
title: Sicherheit in LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0ee361c27bd14f0266b2b86f315f9c091e049c12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="security-in-linq-to-sql"></a>Sicherheit in LINQ to SQL
Beim Herstellen einer Datenbankverbindung müssen Sie stets mit Risiken rechnen. Obwohl LINQ to SQL möglicherweise über einige neue Möglichkeiten zur Arbeit mit Daten in SQL Server verfügt, stellt es keine zusätzlichen Sicherheitsmechanismen bereit.  
  
## <a name="access-control-and-authentication"></a>Zugriffssteuerung und Authentifizierung  
 LINQ to SQL verfügt weder über ein eigenes Benutzermodell noch über Authentifizierungsmechanismen. Verwenden Sie SQL Server-Sicherheit zum Steuern des Zugriffs auf die Datenbank, Datenbanktabellen, Ansichten und gespeicherte Prozeduren, die Ihrem Objektmodell zugeordnet sind. Gewähren Sie die minimal erforderlichen Zugriffsrechte für Benutzer und fordern Sie sichere Kennwörter zur Benutzerauthentifizierung.  
  
## <a name="mapping-and-schema-information"></a>Zuordnung und Schemainformationen  
 SQL-CLR-Typzuordnung und Datenbankschemainformationen im Objektmodell oder in der externen Zuordnungsdatei stehen allen Benutzern zur Verfügung, die auf die Dateien im Dateisystem zugreifen können. Angenommen, die Schemainformationen stehen allen Benutzern zur Verfügung, die auf das Objektmodell oder die externe Zuordnungsdatei zugreifen können. Um den Zugriff von einer breiteren Benutzerbasis zu verhindern, können Sie die Quelldateien und Zuordnungsdateien mithilfe von Dateisicherheitsmechanismen sichern.  
  
## <a name="connection-strings"></a>Verbindungszeichenfolgen  
 Vermeiden Sie nach Möglichkeit die Verwendung von Kennwörtern in Verbindungszeichenfolgen. Eine Verbindungszeichenfolge ein nicht nur ein Sicherheitsrisiko an sich; die Verbindungszeichenfolge kann dem Objektmodell oder der externen Zuordnungsdatei auch als Klartext hinzugefügt werden, wenn der O/R-Designer oder das SQLMetal-Befehlszeilentool verwendet wird. Jeder Benutzer mit Zugriff auf das Objektmodell oder die externe Zuordnungsdatei über das Dateisystem kann das Verbindungskennwort erkennen, wenn es in der Verbindungszeichenfolge enthalten ist.  
  
 Um solche Risiken zu minimieren, verwenden Sie integrierte Sicherheit, um eine sichere Verbindung mit [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] herzustellen. Bei diesem Ansatz müssen Sie kein Kennwort in der Verbindungszeichenfolge speichern. Weitere Informationen finden Sie unter [SQL Server-Sicherheit](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).  
  
 Wenn keine integrierte Sicherheit vorhanden ist, ist in der in der Verbindungszeichenfolge ein Kennwort im Klartext erforderlich. Folgendes sind die besten Möglichkeiten, die Verbindungszeichenfolge zu sichern (sicherste Möglichkeiten zuerst):  
  
-   Verwenden der integrierten Sicherheit  
  
-   Sichern von Verbindungszeichenfolgen mit Kennwörtern und Minimieren der Weitergabe von Verbindungszeichenfolgen  
  
-   Verwenden einer <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType>-Klasse anstelle einer Verbindungszeichenfolge, da die Bereitstellung nur begrenzt ist Instanziieren der <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>-Klasse in LINQ to SQL mit einem <xref:System.Data.SqlClient.SqlConnection>-Objekt  
  
-   Minimieren der Lebensdauer und Berührungsereignisse aller Verbindungszeichenfolgen  
  
## <a name="see-also"></a>Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Häufig gestellte Fragen](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
