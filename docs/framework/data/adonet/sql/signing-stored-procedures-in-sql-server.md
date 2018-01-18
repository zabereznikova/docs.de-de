---
title: Signieren von gespeicherten Prozeduren in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a3f1ed66ed7caf2272ca27097dc9a838bec7d0ae
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="signing-stored-procedures-in-sql-server"></a>Signieren von gespeicherten Prozeduren in SQL Server
Sie können gespeicherte Prozeduren mit einem Zertifikat oder einem asymmetrischen Schlüssel signieren. Gedacht ist dies für Szenarien, in denen Berechtigungen nicht über die Besitzverkettung geerbt werden können oder in denen die Besitzkette unterbrochen ist, wie bei dynamischem SQL. In einem solchen Fall erstellen Sie einen Benutzer, der dem Zertifikat zugeordnet wird, wodurch ihm Berechtigungen für die Objekte gewährt werden, auf die die gespeicherte Prozedur zugreifen können muss.  
  
 Bei der Ausführung der gespeicherten Prozedur kombiniert SQL Server die Berechtigungen des Zertifikatsbenutzers mit den Berechtigungen des Aufrufers. Im Gegensatz zur EXECUTE AS-Klausel ändert sich der Ausführungskontext der Prozedur nicht. Integrierte Funktionen, die Anmelde- und Benutzernamen zurückgeben, geben den Namen des Aufrufers, und nicht den Namen des Zertifikatsbenutzers zurück.  
  
 Eine digitale Signatur ist ein mit dem privaten Schlüssel des Signaturgebers verschlüsselter Datendigest. Der private Schlüssel stellt sicher, dass die digitale Signatur für den Träger oder Besitzer eindeutig ist. Signiert werden können gespeicherte Prozeduren, Funktionen oder Trigger.  
  
> [!NOTE]
>  Sie können in der Masterdatenbank ein Zertifikat zum Gewähren von Berechtigungen auf Serverebene erstellen.  
  
## <a name="creating-certificates"></a>Erstellen von Zertifikaten  
 Beim Signieren einer gespeicherten Prozedur mit einem Zertifikat wird mithilfe des privaten Schlüssels ein Datendigest erstellt, der aus dem verschlüsselten Hash der gespeicherten Prozedur besteht. Zur Laufzeit wird der Datendigest mit dem öffentlichen Schlüssel entschlüsselt und mit dem Hashwert der gespeicherten Prozedur verglichen. Wenn die gespeicherte Prozedur geändert wird, wird der Hashwert ungültig, sodass die digitale Signatur nicht mehr übereinstimmt. Auf diese Weise wird verhindert, dass der Code der gespeicherten Prozedur durch einen Benutzer geändert wird, der keine Zugriffsberechtigung für den privaten Schlüssel besitzt. Daher muss die Prozedur nach jeder Änderung neu signiert werden.  
  
 Zum Signieren eines Moduls sind die folgenden vier Schritte auszuführen:  
  
1.  Erstellen Sie mit der Transact-SQL-`CREATE CERTIFICATE [certificateName]`-Anweisung ein Zertifikat. Diese Anweisung verfügt über mehrere Optionen, mit denen das Start- und Enddatum und ein Kennwort festgelegt werden können. Die Standardgültigkeitsdauer beträgt ein Jahr.  
  
2.  Erstellen Sie mit der Transact-SQL-`CREATE USER [userName] FROM CERTIFICATE [certificateName]`-Anweisung einen mit diesem Zertifikat verknüpften Datenbankbenutzer. Dieser Benutzer ist nur in der Datenbank vorhanden, und er wird keiner Anmeldung zugeordnet.  
  
3.  Gewähren Sie dem Zertifikatsbenutzer die erforderlichen Berechtigungen für die Datenbankobjekte.  
  
> [!NOTE]
>  Ein Zertifikat kann keine Berechtigungen für Benutzer gewähren, die Berechtigungen hatten, die mit der DENY-Anweisung widerrufen wurden. DENY hat immer Vorrang gegenüber GRANT und verhindert, dass der Aufrufer Berechtigungen erben kann, die dem Zertifikatsbenutzer gewährt wurden.  
  
1.  Signieren Sie die Prozedur mit dem Zertifikat. Verwenden Sie dazu die Transact-SQL-`ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]`-Anweisung.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Modulsignierung](http://go.microsoft.com/fwlink/?LinkId=98590) in SQL Server-Onlinedokumentation|Beschreibt die Modulsignierung und enthält ein Beispielszenario sowie Links zu den relevanten Transact-SQL-Themen.|  
|[Signieren von gespeicherten Prozeduren mit einem Zertifikat](http://msdn.microsoft.com/library/bb283630.aspx) in SQL Server-Onlinedokumentation|Enthält ein Lernprogramm zum Signieren einer gespeicherten Prozedur mit einem Zertifikat.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [Schreiben von sicherem dynamischen SQL in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [Ändern von Daten mit gespeicherten Prozeduren](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
