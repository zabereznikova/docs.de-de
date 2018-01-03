---
title: "SqlClient-Unterstützung für LocalDB"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
caps.latest.revision: "14"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 99845420549393829582ade11f38b75e3ebff484
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="sqlclient-support-for-localdb"></a>SqlClient-Unterstützung für LocalDB
Ab [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Codename "Denali" ist eine vereinfachte Version von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]mit dem Namen LocalDB verfügbar. In diesem Thema wird erläutert, wie eine Verbindung mit einer LocalDB-Datenbank hergestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu LocalDB, z. B. wie Sie LocalDB installieren und eine LocalDB-Instanz konfigurieren, finden Sie in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] -Onlinedokumentation.  
  
 Zusammenfassung der Verwendungsmöglichkeiten für LocalDB:  
  
-   Erstellen und Starten von LocalDB-Instanzen mit der Datei „sqllocaldb.exe“ oder „app.config“.  
  
-   Verwenden von „sqlcmd.exe“, um Datenbanken in einer LocalDB-Instanz hinzuzufügen oder zu ändern. Beispielsweise `sqlcmd -S (localdb)\myinst`.  
  
-   Verwenden des `AttachDBFilename` -Schlüsselworts für die Verbindungszeichenfolge, um der LocalDB-Instanz eine Datenbank hinzuzufügen. Wenn Sie `AttachDBFilename`verwenden und den Namen der Datenbank nicht mit dem `Database` -Schlüsselwort der Verbindungszeichenfolge angeben, wird die Datenbank beim Schließen der Anwendung aus der LocalDB-Instanz entfernt.  
  
-   Angeben einer LocalDB-Instanz in der Verbindungszeichenfolge. Wenn der Instanzname z. B. `myInstance`lautet, könnte die Verbindungszeichenfolge Folgendes enthalten:  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 `User Instance=True` ist bei einer Verbindung mit einer LocalDB-Datenbank nicht zulässig.  
  
 Sie können LocalDB aus dem [Microsoft SQL Server 2012 Feature Pack](http://www.microsoft.com/download/en/details.aspx?id=29065)herunterladen. Wenn Sie "sqlcmd.exe" verwenden, um Daten in der LocalDB-Instanz zu ändern, benötigen Sie "sqlcmd" von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012, das auch aus dem [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 Feature Pack abrufbar ist.  
  
## <a name="programmatically-create-a-named-instance"></a>Programmgesteuertes Erstellen einer benannten Instanz  
 Eine Anwendung kann eine benannte Instanz erstellen und eine Datenbank wie folgt angeben:  
  
-   Geben Sie die LocalDB-Instanzen, die in der Datei „app.config“ erstellt werden sollen, wie folgt an.  Die Versionsnummer der Instanz sollte identisch mit der Versionsnummer der LocalDB-Installation sein.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
-   Geben Sie den Namen der Instanz unter Verwendung des `server` -Schlüsselworts für die Verbindungszeichenfolge an.  Der im `server` -Schlüsselwort für die Verbindungszeichenfolge angegebene Instanzname muss mit dem Namen übereinstimmen, der in der Datei „app.config“ angegeben ist.  
  
-   Verwenden Sie das `AttachDBFilename` -Schlüsselwort für die Verbindungszeichenfolge, um die MDF-Datei anzugeben.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Features and ADO.NET (SQL Server-Features und ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
