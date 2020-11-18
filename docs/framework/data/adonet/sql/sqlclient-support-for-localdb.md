---
title: SqlClient-Unterstützung für LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 55ab1346de6f5c14f15d01344a984c18edf30e02
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824479"
---
# <a name="sqlclient-support-for-localdb"></a>SqlClient-Unterstützung für LocalDB

In diesem Artikel wird erläutert, wie eine Verbindung mit einer localdb-Datenbank hergestellt wird. Localdb ist eine vereinfachte Version von SQL Server.
  
## <a name="remarks"></a>Hinweise
  
 Sie können LocalDB für Folgendes nutzen:  
  
- Erstellen und Starten von LocalDB-Instanzen mit einer sqllocaldb.exe- oder einer app.config-Datei  
  
- Verwenden Sie „sqlcmd.exe“, um Datenbanken in einer LocalDB-Instanz hinzuzufügen und zu ändern. Beispiel: `sqlcmd -S (localdb)\myinst`.  
  
- Verwenden des `AttachDBFilename`-Schlüsselworts für eine Verbindungszeichenfolge zum Hinzufügen einer Datenbank zu Ihr LocalDB-Instanz. Wenn Sie `AttachDBFilename` verwenden und den Namen der Datenbank nicht mit dem Schlüsselwort der `Database`-Verbindungszeichenfolge angeben, wird die Datenbank aus der LocalDB-Instanz entfernt, wenn die Anwendung geschlossen wird.  
  
- Geben Sie in der Verbindungszeichenfolge eine LocalDB-Instanz an: Wenn Ihr Instanzname beispielsweise `myInstance` lautet, enthält die Verbindungszeichenfolge folgende Elemente:  
  
    `server=(localdb)\\myInstance`  
  
 `User Instance=True` ist nicht zulässig, wenn eine Verbindung mit einer LocalDB-Datenbank hergestellt wird.  
  
Weitere Informationen zum Installieren von localdb finden Sie unter [SQL Server Express localdb](/sql/database-engine/configure-windows/sql-server-express-localdb).
  
## <a name="programmatically-create-a-named-instance"></a>Programmgesteuertes Erstellen einer benannten Instanz  

 Eine Anwendung kann wie folgt eine benannte Instanz erstellen und eine Datenbank angeben:  
  
- Geben Sie wie folgt die LocalDB-Instanzen an, die in der Datei „app.config“ erstellt werden sollen.  Die Versionsnummer der Instanz sollte mit der Versionsnummer der LocalDB-Installation identisch sein.  
  
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
  
- Geben Sie den Namen der Instanz mithilfe des Schlüsselworts `server` für die Verbindungszeichenfolge an.  Der im `server`-Schlüsselwort für die Verbindungszeichenfolge angegebene Instanzname muss mit dem Namen übereinstimmen, der in der Datei app.config angegeben ist.  
  
- Verwenden Sie das Schlüsselwort `AttachDBFilename` für die Verbindungszeichenfolge, um die MDF-Datei anzugeben.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server-Funktionen und ADO.NET](sql-server-features-and-adonet.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
