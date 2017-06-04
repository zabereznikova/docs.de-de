---
title: "Aktivieren des datenbank&#252;bergreifenden Zugriffs in SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
caps.latest.revision: 10
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 10
---
# Aktivieren des datenbank&#252;bergreifenden Zugriffs in SQL Server
Von einer datenbankübergreifenden Besitzverkettung spricht man, wenn eine Prozedur in einer Datenbank von Objekten in einer anderen Datenbank abhängt.  Eine datenbankübergreifende Besitzkette funktioniert wie die Besitzkette innerhalb einer einzelnen Datenbank – mit dem Unterschied, dass eine durchgängige Besitzkette voraussetzt, dass alle Objektbesitzer demselben Anmeldekonto zugeordnet sind.  Wenn das Quellobjekt in der Quelldatenbank und das Zielobjekt in der Zieldatenbank zu ein und demselben Anmeldekonto gehören, nimmt SQL Server keine Prüfung der Berechtigungen für die Zielobjekte vor.  
  
## Standardmäßig deaktiviert  
 Die datenbankübergreifende Besitzverkettung ist standardmäßig deaktiviert.  Microsoft empfiehlt, dass Sie die datenbankübergreifende Besitzverkettung deaktivieren, da Sie sich sonst den folgenden Sicherheitsrisiken aussetzen:  
  
-   Datenbankbesitzer und Member der `db_ddladmin`\-Datenbankrolle bzw. `db_owners` können Objekte erstellen, deren Besitzer andere Benutzer sind.  Diese Objekte können potenziell auf Objekte in anderen Datenbanken zielen.  Das bedeutet: Wenn Sie die datenbankübergreifende Besitzverkettung aktivieren, müssen Sie sich dessen bewusst sein, dass diese Benutzer auf die Daten in allen verketteten Datenbanken zugreifen können.  
  
-   Benutzer mit der CREATE DATABASE\-Berechtigung können neue Datenbanken erstellen und vorhandene Datenbanken anfügen.  Wenn die datenbankübergreifende Besitzverkettung aktiviert ist, können diese Benutzer u. U. auf Objekte in anderen Datenbanken zugreifen, auf die sie von den Datenbanken aus, die sie selbst neu erstellen oder anhängen, keinen Zugriff hätten.  
  
## Aktivieren der datenbankübergreifenden Besitzverkettung  
 Die datenbankübergreifende Besitzverkettung sollte nur in Umgebungen aktiviert werden, in denen Sie Benutzern mit weitreichenden Berechtigungen voll vertrauen.  Sie kann bei der Einrichtung für alle Datenbanken oder mit den [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]\-Befehlen `sp_configure` und `ALTER DATABASE` nur für bestimmte Datenbanken konfiguriert werden.  
  
 Wenn Sie die datenbankübergreifende Besitzverkettung selektiv konfigurieren möchten, deaktivieren Sie sie mithilfe von `sp_configure` für den Server.  Konfigurieren Sie dann mit dem Befehl ALTER DATABASE und mit SET DB\_CHAINING ON die datenbankübergreifende Besitzverkettung für die gewünschten Datenbanken.  
  
 Im folgenden Beispiel wird die datenbankübergreifende Besitzverkettung für alle Datenbanken aktiviert:  
  
```  
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 Im folgenden Beispiel wird die datenbankübergreifende Besitzverkettung für bestimmte Datenbanken aktiviert:  
  
```  
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
  
```  
  
### Dynamisch erstellte SQL\-Anweisungen  
 Die datenbankübergreifende Besitzverkettung funktioniert nicht, wenn dynamisch erstellte SQL\-Anweisungen ausgeführt werden, sofern derselbe Benutzer nicht in beiden Datenbanken vorhanden ist.  Dieses Problem können Sie in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] umgehen, indem Sie eine gespeicherte Prozedur erstellen, die auf die Daten in einer anderen Datenbank zugreift, und die Prozedur mit einem Zertifikat signieren, das in beiden Datenbanken vorhanden ist.  Die Benutzer können dann auf die von der Prozedur verwendeten Datenbankressourcen zugreifen, ohne dass ihnen Zugriffsrechte für die Datenbank oder andere Berechtigungen erteilt werden müssen.  
  
## Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|---------------|------------------|  
|[Erweitern des Identitätswechsels bei Datenbanken durch Verwenden von EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) und [Cross DB Ownership Chaining \(Option\)](http://msdn.microsoft.com/library/ms188694.aspx) in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]\-Onlinedokumentation.|In den Themen wird das Konfigurieren einer datenbankübergreifenden Besitzverkettung für eine [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]\-Instanz beschrieben.|  
  
## Siehe auch  
 [Sichern von ADO.NET\-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Übersicht über die SQL Server\-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)   
 [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)   
 [Schreiben von sicherem dynamischen SQL in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)   
 [Signieren gespeicherter Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)   
 [Verwaltete Anbieter und DataSet Developer Center \(ADO.NET\)](http://go.microsoft.com/fwlink/?LinkId=217917)