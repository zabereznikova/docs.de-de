---
title: Verbindungszeichenfolgen-Syntax
description: Erfahren Sie mehr über die Syntax der Verbindungs Zeichenfolgen in ADO.net. Die Syntax für jeden Anbieter ist in der ConnectionString-Eigenschaft dokumentiert.
ms.date: 05/22/2018
ms.assetid: 0977aeee-04d1-4cce-bbed-750c77fce06e
ms.openlocfilehash: bb29365a4729e731ddeffc7cfa61e379c3144a46
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287050"
---
# <a name="connection-string-syntax"></a>Verbindungszeichenfolgen-Syntax
Alle .NET Framework-Datenanbieter besitzen ein `Connection`-Objekt, das von <xref:System.Data.Common.DbConnection> erbt, sowie eine anbieterspezifische <xref:System.Data.Common.DbConnection.ConnectionString%2A>-Eigenschaft. Die spezifische Verbindungszeichenfolgensyntax für den jeweiligen Anbieter wird in dessen `ConnectionString`-Eigenschaft dokumentiert. In der folgenden Tabelle sind die vier Datenanbieter aufgelistet, die in .NET Framework enthalten sind.  
  
|.NET Framework-Datenanbieter|BESCHREIBUNG|  
|----------------------------------|-----------------|  
|<xref:System.Data.SqlClient>|Ermöglicht den Datenzugriff für Microsoft SQL Server. Weitere Informationen zur Verbindungszeichenfolgensyntax finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.|  
|<xref:System.Data.OleDb>|Ermöglicht den Datenzugriff für Datenquellen, die mit OLE DB verfügbar gemacht werden. Weitere Informationen zur Verbindungszeichenfolgensyntax finden Sie unter <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.|  
|<xref:System.Data.Odbc>|Ermöglicht den Datenzugriff für Datenquellen, die mit ODBC verfügbar gemacht werden. Weitere Informationen zur Verbindungszeichenfolgensyntax finden Sie unter <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>.|  
|<xref:System.Data.OracleClient>|Ermöglicht den Datenzugriff für Oracle 8.1.7 oder höher. Weitere Informationen zur Verbindungszeichenfolgensyntax finden Sie unter <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.|  
  
## <a name="connection-string-builders"></a>Verbindungszeichenfolgen-Generatoren  
 In ADO.NET 2.0 wurden die folgenden Verbindungszeichenfolgen-Generatoren für .NET Framework-Datenanbieter eingeführt.  
  
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder>  
  
- <xref:System.Data.OleDb.OleDbConnectionStringBuilder>  
  
- <xref:System.Data.Odbc.OdbcConnectionStringBuilder>  
  
- <xref:System.Data.OracleClient.OracleConnectionStringBuilder>  
  
 Mit den Verbindungszeichenfolgen-Generatoren können Sie zur Laufzeit syntaktisch gültige Verbindungszeichenfolgen erstellen, sodass Sie die Werte der Verbindungszeichenfolgen nicht manuell im Code verketten müssen. Weitere Informationen finden Sie in [Connection String Builders (Verbindungszeichenfolgengeneratoren)](connection-string-builders.md).  

## <a name="windows-authentication"></a>Windows-Authentifizierung  
 Wir empfehlen die Verwendung der Windows-Authentifizierung (auch als *integrierte Sicherheit*bezeichnet) zum Herstellen einer Verbindung mit Datenquellen, die diese unterstützen. Die in der Verbindungszeichenfolge zu verwendende Syntax richtet sich nach dem Datenanbieter. In der folgenden Tabelle wird die Syntax der Windows-Authentifizierung dargestellt, die bei .NET Framework-Datenanbietern verwendet wird.  
  
|Anbieter|Syntax|  
|--------------|------------|  
|`SqlClient`|`Integrated Security=true;`<br /><br /> `-- or --`<br /><br /> `Integrated Security=SSPI;`|  
|`OleDb`|`Integrated Security=SSPI;`|  
|`Odbc`|`Trusted_Connection=yes;`|  
|`OracleClient`|`Integrated Security=yes;`|  
  
> [!NOTE]
> Wenn der `Integrated Security=true`-Anbieter verwendet wird, wird bei `OleDb` eine Ausnahme ausgelöst.  
  
## <a name="sqlclient-connection-strings"></a>SqlClient-Verbindungszeichenfolgen  
Die Syntax für eine <xref:System.Data.SqlClient.SqlConnection>-Verbindungszeichenfolge wird in der <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType>-Eigenschaft dokumentiert. Mit der <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>-Eigenschaft können Sie eine Verbindungszeichenfolge für eine SQL Server-Datenbank abrufen oder festlegen. Wenn Sie eine Verbindung mit einer früheren Version von SQL Server herstellen müssen, müssen Sie den .NET Framework-Datenanbieter für OLE DB verwenden (<xref:System.Data.OleDb>). Für die meisten Schlüsselwörter in Verbindungszeichenfolgen gibt es bei den <xref:System.Data.SqlClient.SqlConnectionStringBuilder>-Eigenschaften passende Entsprechungen.  

> [!IMPORTANT]
> Die Standardeinstellung für das- `Persist Security Info` Schlüsselwort ist `false` . Wenn die Einstellung in `true` bzw. `yes` geändert wird, sind sicherheitsrelevante Informationen, die über diese Verbindung übertragen werden, wie Benutzer-ID und Kennwort, nicht mehr sicher. `Persist Security Info`Legen Sie auf fest, `false` um sicherzustellen, dass eine nicht vertrauenswürdige Quelle keinen Zugriff auf sensible Verbindungs Zeichen folgen Informationen hat.  

### <a name="windows-authentication-with-sqlclient"></a>Windows-Authentifizierung mit SqlClient
 Jede der folgenden Syntax Formen verwendet die Windows-Authentifizierung, um eine Verbindung mit der **AdventureWorks** -Datenbank auf einem lokalen Server herzustellen.  
  
```csharp  
"Persist Security Info=False;Integrated Security=true;  
    Initial Catalog=AdventureWorks;Server=MSSQL1"  
"Persist Security Info=False;Integrated Security=SSPI;  
    database=AdventureWorks;server=(local)"  
"Persist Security Info=False;Trusted_Connection=True;  
    database=AdventureWorks;server=(local)"  
```  
  
### <a name="sql-server-authentication-with-sqlclient"></a>SQL Server Authentifizierung mit SqlClient
 Zum Herstellen einer Verbindung mit SQL Server ist vorzugsweise die Windows-Authentifizierung zu verwenden. Wenn jedoch die SQL Server-Authentifizierung erforderlich ist, verwenden Sie zum Angeben eines Benutzernamens und Kennworts die im Folgenden beschriebene Syntax. In diesem Beispiel werden der Benutzername und das Kennwort durch Sternchen dargestellt.  
  
```csharp  
"Persist Security Info=False;User ID=*****;Password=*****;Initial Catalog=AdventureWorks;Server=MySqlServer"  
```  

Wenn Sie eine Verbindung mit der Azure SQL-Datenbank herstellen oder Azure SQL Data Warehouse und eine Anmeldung im Format bereitstellen `user@servername` , stellen Sie sicher, dass der `servername` Wert in der Anmeldung mit dem für angegebenen Wert übereinstimmt `Server=` .

> [!NOTE]
> Das Angeben der Windows-Authentifizierung hat Vorrang vor SQL Server-Anmeldungen. Wenn Sie sowohl die integrierte Sicherheit aktivieren als auch einen Benutzernamen und ein Kennwort angeben, werden Benutzername und Kennwort ignoriert, und die Windows-Authentifizierung wird verwendet.  

### <a name="connect-to-a-named-instance-of-sql-server"></a>Stellen Sie eine Verbindung mit einer benannten Instanz von her SQL Server
Verwenden Sie zum Herstellen einer Verbindung mit einer benannten Instanz von SQL Server die Syntax *Server Name \ Instanzname* .  
  
```csharp  
"Data Source=MySqlServer\MSSQL1;"  
```  

Sie können beim Erstellen einer Verbindungszeichenfolge auch die <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>-Eigenschaft von `SqlConnectionStringBuilder` auf den Instanznamen festlegen. Die <xref:System.Data.SqlClient.SqlConnection.DataSource%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlConnection>-Objekts ist schreibgeschützt.  
  
### <a name="type-system-version-changes"></a>Änderungen an der Typsystemversion  
 Das- `Type System Version` Schlüsselwort in einem <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> gibt die Client seitige Darstellung von SQL Server Typen an. Weitere Informationen zum <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType>-Schlüsselwort finden Sie unter `Type System Version`.  
  
## <a name="connecting-and-attaching-to-sql-server-express-user-instances"></a>Herstellen einer Verbindung mit und Anfügen an SQL Server Express-Benutzerinstanzen  
 Benutzerinstanzen sind eine Funktion in SQL Server Express. Mit ihrer Hilfe können Benutzer, die mit einem lokalen Windows-Konto der untersten Berechtigungsebene (LUA) arbeiten, eine SQL Server-Datenbank anfügen und ausführen, ohne dass dafür Administratorrechte erforderlich sind. Eine Benutzerinstanz wird mit den Windows-Anmeldeinformationen des Benutzers und nicht als Dienst ausgeführt.  
  
 Weitere Informationen zum Arbeiten mit Benutzer Instanzen finden Sie unter [SQL Server Express Benutzer Instanzen](./sql/sql-server-express-user-instances.md).  
  
## <a name="using-trustservercertificate"></a>Verwenden von "TrustServerCertificate"  
 Das `TrustServerCertificate` Schlüsselwort ist nur gültig, wenn eine Verbindung mit einer SQL Server Instanz mit einem gültigen Zertifikat hergestellt wird. Wenn `TrustServerCertificate` auf `true` gesetzt wird, verwendet die Transportschicht zum Verschlüsseln des Kanals SSL und umgeht beim Validieren der Vertrauenswürdigkeit die Zertifikatkette.  
  
```csharp  
"TrustServerCertificate=true;"
```  
  
> [!NOTE]
> Wenn `TrustServerCertificate` auf `true` gesetzt wird und die Verschlüsselung aktiviert ist, wird die auf dem Server angegebene Verschlüsselungsstufe auch dann verwendet, wenn `Encrypt` in der Verbindungszeichenfolge auf `false` gesetzt ist. Andernfalls schlägt die Verbindung fehl.  
  
### <a name="enabling-encryption"></a>Aktivieren der Verschlüsselung  
 Um die Verschlüsselung zu aktivieren, wenn ein Zertifikat nicht auf dem Server bereitgestellt wurde, müssen die Optionen **Protokoll Verschlüsselung erzwingen** und **Serverzertifikat vertrauen** in SQL Server-Konfigurations-Manager festgelegt werden. In diesem Fall wird bei der Verschlüsselung ein selbstsigniertes Serverzertifikat ohne Überprüfung verwendet, wenn kein überprüfbares Zertifikat auf dem Server bereitgestellt wurde.  
  
 Die Anwendungseinstellungen können nicht zu einer Einschränkung der in SQL Server konfigurierten Sicherheitsstufe führen, sondern verstärken sie sogar möglicherweise. Eine Anwendung kann die Verschlüsselung anfordern, indem `TrustServerCertificate` die `Encrypt` Schlüsselwörter und auf festgelegt `true` werden. Dadurch wird sichergestellt, dass die Verschlüsselung auch dann erfolgt, wenn kein Serverzertifikat bereitgestellt wurde und die **Protokoll Verschlüsselung** für den Client nicht konfiguriert wurde. Wenn jedoch `TrustServerCertificate` in der Clientkonfiguration nicht aktiviert wird, ist immer noch ein bereitgestelltes Serverzertifikat erforderlich.  
  
 In der folgenden Tabelle werden alle Fälle beschrieben.  
  
|Protokollverschlüsselung erzwingen - Clienteinstellung|Dem Serverzertifikat vertrauen|Verbindungszeichenfolge/Attribut "Encrypt"/"Use Encryption for Data"|Verbindungszeichenfolge/Attribut "TrustServerCertificate"|Ergebnis|  
|----------------------------------------------|---------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------|------------|  
|Nein|–|Nein (Standard)|Ignoriert|Keine Verschlüsselung.|  
|Nein|–|Ja|Nein (Standard)|Eine Verschlüsselung findet nur statt, wenn ein überprüfbares Serverzertifikat vorliegt, anderenfalls schlägt der Verbindungsversuch fehl.|  
|Nein|–|Ja|Ja|Verschlüsselung wird immer durchgeführt, es wird jedoch z. B. ein selbstsigniertes Serverzertifikat verwendet.|  
|Ja|Nein|Ignoriert|Ignoriert|Die Verschlüsselung erfolgt nur, wenn ein überprüfbares Serverzertifikat vorhanden ist. Andernfalls schlägt der Verbindungsversuch fehl.|  
|Ja|Ja|Nein (Standard)|Ignoriert|Verschlüsselung wird immer durchgeführt, es wird jedoch z. B. ein selbstsigniertes Serverzertifikat verwendet.|  
|Ja|Ja|Ja|Nein (Standard)|Die Verschlüsselung erfolgt nur, wenn ein überprüfbares Serverzertifikat vorhanden ist. Andernfalls schlägt der Verbindungsversuch fehl.|  
|Ja|Ja|Ja|Ja|Verschlüsselung wird immer durchgeführt, es wird jedoch z. B. ein selbstsigniertes Serverzertifikat verwendet.|  
  
 Weitere Informationen finden Sie unter [Verwenden von Verschlüsselung ohne Überprüfung](/sql/relational-databases/native-client/features/using-encryption-without-validation).
  
## <a name="oledb-connection-strings"></a>OLE DB-Verbindungszeichenfolgen  
 Mit der <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>-Eigenschaft von <xref:System.Data.OleDb.OleDbConnection> können Sie eine Verbindungszeichenfolge für eine OLE DB-Datenquelle wie Microsoft Access abrufen bzw. festlegen. Sie können auch zur Laufzeit mit der `OleDb`-Klasse eine <xref:System.Data.OleDb.OleDbConnectionStringBuilder>-Verbindungszeichenfolge erstellen.  
  
### <a name="oledb-connection-string-syntax"></a>Syntax für OLE DB-Verbindungszeichenfolgen  
 Sie müssen für eine <xref:System.Data.OleDb.OleDbConnection>-Verbindungszeichenfolge einen Anbieternamen angeben. Die folgende Verbindungszeichenfolge stellt mithilfe des Jet-Anbieters eine Verbindung mit einer Microsoft Access-Datenbank her. Beachten Sie, dass die Schlüsselwörter `User ID` und `Password` optional sind, wenn die Datenbank ungesichert (Standardeinstellung) ist.  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0; Data Source=d:\Northwind.mdb;User ID=Admin;Password=;
```  
  
 Wenn die Jet-Datenbank auf Benutzerebene gesichert ist, müssen Sie den Speicherort der Arbeitsgruppen-Informationsdatei (MDW) angeben. Mit der Arbeitsgruppen-Informationsdatei werden die Anmeldeinformationen in der Verbindungszeichenfolge validiert.  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=d:\Northwind.mdb;Jet OLEDB:System Database=d:\NorthwindSystem.mdw;User ID=*****;Password=*****;  
```  
  
> [!IMPORTANT]
> Es ist möglich, Verbindungsinformationen für eine **OleDbConnection** in einer Universal Data Link Datei (UDL) bereitzustellen. Sie sollten dies jedoch vermeiden. UDL-Dateien sind nicht verschlüsselt und machen Informationen zur Verbindungszeichenfolge im Klartext verfügbar. Da es sich bei einer UDL-Datei um eine externe Ressource der Anwendung handelt, kann sie nicht mit .NET Framework gesichert werden. UDL-Dateien werden für **SqlClient**nicht unterstützt.  
  
### <a name="using-datadirectory-to-connect-to-accessjet"></a>Verwenden von "DataDirectory" zum Herstellen einer Verbindung mit Access/Jet  
 `DataDirectory` steht nicht exklusiv für `SqlClient` zur Verfügung. Es kann auch für den <xref:System.Data.OleDb>- und den <xref:System.Data.Odbc>-.NET-Datenanbieter verwendet werden. Die folgende <xref:System.Data.OleDb.OleDbConnection>-Beispielzeichenfolge zeigt die Syntax, die erforderlich ist, um eine Verbindung mit der im Ordner &lt;legacyBold&gt;app_data&lt;/legacyBold&gt; der Anwendung befindlichen Datei &lt;legacyBold&gt;Northwind.mdb&lt;/legacyBold&gt; herzustellen. Die Systemdatenbank (System.mdw) ist ebenfalls an diesem Speicherort gespeichert.  
  
```csharp  
"Provider=Microsoft.Jet.OLEDB.4.0;  
Data Source=|DataDirectory|\Northwind.mdb;  
Jet OLEDB:System Database=|DataDirectory|\System.mdw;"  
```  
  
> [!IMPORTANT]
> Die Angabe des Speicherorts der Systemdatenbank in der Verbindungszeichenfolge ist nicht erforderlich, wenn die Access-/Jet-Datenbank ungesichert ist. Die Sicherheit ist standardmäßig deaktiviert, sodass alle Benutzer eine Verbindung als integrierter Admin-Benutzer mit einem leeren Kennwort herstellen. Selbst wenn die Sicherheit auf Benutzerebene ordnungsgemäß implementiert ist, bleibt eine Jet-Datenbank durch Angriffe verwundbar. Aufgrund der inhärenten Schwäche des dateibasierten Sicherheitsschemas von Access-/Jet-Datenbanken wird davon abgeraten, in solchen Datenbanken sicherheitsrelevante Informationen zu speichern.  
  
### <a name="connecting-to-excel"></a>Herstellen einer Verbindung mit Excel  
 Für die Verbindung mit einer Excel-Arbeitsmappe wird der Microsoft Jet-Anbieter verwendet. In der folgenden Verbindungszeichenfolge werden mit dem Schlüsselwort `Extended Properties` Excel-spezifische Eigenschaften festgelegt. HDR=Yes; gibt an, dass die erste Zeile Spaltennamen und keine Daten enthält, und IMEX=1; weist den Treiber an, miteinander vermischte Datenspalten immer als Text zu lesen.  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=D:\MyExcel.xls;Extended Properties=""Excel 8.0;HDR=Yes;IMEX=1""  
```  
  
 Beachten Sie, dass die für das `Extended Properties`-Schlüsselwort erforderlichen doppelten Anführungszeichen ihrerseits ebenfalls in doppelte Anführungszeichen gesetzt werden müssen.  
  
### <a name="data-shape-provider-connection-string-syntax"></a>Syntax für Verbindungszeichenfolgen für den MS Data Shape-Anbieter  
 Verwenden Sie für den MS Data Shape-Anbieter die Schlüsselwörter `Provider` und `Data Provider`. Im folgenden Beispiel wird mithilfe des Shape-Anbieters eine Verbindung mit einer lokalen Instanz von SQL Server hergestellt.  
  
```csharp  
"Provider=MSDataShape;Data Provider=SQLOLEDB;Data Source=(local);Initial Catalog=pubs;Integrated Security=SSPI;"
```  
  
## <a name="odbc-connection-strings"></a>ODBC-Verbindungszeichenfolgen  
 Mit der <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>-Eigenschaft einer <xref:System.Data.Odbc.OdbcConnection> können Sie eine Verbindungszeichenfolge für eine OLE DB-Datenquelle abrufen oder festlegen. ODBC-Verbindungszeichenfolgen werden auch vom <xref:System.Data.Odbc.OdbcConnectionStringBuilder> unterstützt.  
  
 In der folgenden Verbindungszeichenfolge wird der Microsoft-Texttreiber verwendet.  
  
```csharp  
Driver={Microsoft Text Driver (*.txt; *.csv)};DBQ=d:\bin  
```  
  
### <a name="using-datadirectory-to-connect-to-visual-foxpro"></a>Verwenden von "DataDirectory" zum Herstellen einer Verbindung mit Visual FoxPro  
 Das folgende Beispiel für eine <xref:System.Data.Odbc.OdbcConnection>-Verbindungszeichenfolge zeigt, wie mit `DataDirectory` eine Verbindung mit einer Microsoft Visual FoxPro-Datei hergestellt werden kann.  
  
```csharp  
"Driver={Microsoft Visual FoxPro Driver};  
SourceDB=|DataDirectory|\MyData.DBC;SourceType=DBC;"  
```  
  
## <a name="oracle-connection-strings"></a>Oracle-Verbindungszeichenfolgen  
 Mit der <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>-Eigenschaft einer <xref:System.Data.OracleClient.OracleConnection> können Sie eine Verbindungszeichenfolge für eine OLE DB-Datenquelle abrufen oder festlegen. Oracle-Verbindungszeichenfolgen werden auch vom <xref:System.Data.OracleClient.OracleConnectionStringBuilder> unterstützt.  
  
```csharp
Data Source=Oracle9i;User ID=*****;Password=*****;  
```  
  
 Weitere Informationen zur Syntax für ODBC-Verbindungszeichenfolgen finden Sie unter <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.  
  
## <a name="see-also"></a>Siehe auch

- [Verbindungs Zeichenfolgen](connection-strings.md)
- [Herstellen der Verbindung mit einer Datenquelle](connecting-to-a-data-source.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
