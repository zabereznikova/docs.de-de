---
title: SQL Server Express-Benutzerinstanzen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 00c12376-cb26-4317-86ad-e6e9c089be57
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4b8b795454ab038b9e992c5e1187a0c4dcb46c76
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="sql-server-express-user-instances"></a>SQL Server Express-Benutzerinstanzen
Microsoft SQL Server Express Edition (SQL Server Express) unterstützt die Benutzerinstanzfunktion, die die Verwendung des .NET Framework-Datenanbieters für SQL Server (`SqlClient`) voraussetzt. Eine Benutzerinstanz ist eine separate Instanz des SQL Server Express-Datenbankmoduls, die von einer übergeordneten Instanz generiert wird. Mit Benutzerinstanzen können Benutzer, die auf ihrem lokalen Computer nicht mit Administratorrechten arbeiten, eine Verbindung zu SQL Server Express-Datenbanken herstellen. Jede Instanz wird im Sicherheitskontext des jeweiligen Benutzers ausgeführt, wobei für jeden Benutzer genau eine Instanz erstellt wird.  
  
## <a name="user-instance-capabilities"></a>Was können Benutzerinstanzen?  
 Benutzerinstanzen eignen sich für Benutzer, die Windows in einem Konto der untersten Berechtigungsebene (Least-Priviledged User Account, LUA) ausführen, da jeder Benutzer über SQL Server-Systemadministratorberechtigungen (`sysadmin`) für die Instanz verfügt, die auf seinem Computer ausgeführt wird, ohne dass dazu auch Windows mit Administratorrechten ausgeführt werden muss. Software, die in einer Benutzerinstanz mit eingeschränkten Berechtigungen ausgeführt wird, kann keine systemweiten Änderungen vornehmen, da die SQL Server Express-Instanz beim Benutzer über das Windows-Konto ohne Administratorberechtigung und nicht als Dienst ausgeführt wird. Jede Benutzerinstanz ist von ihrer übergeordneten Instanz und von allen anderen Benutzerinstanzen isoliert, die auf demselben Computer ausgeführt werden. Auf einer Benutzerinstanz installierte Datenbanken werden nur im Einzelbenutzermodus geöffnet. Es ist ausgeschlossen, dass mehrere Benutzer eine Verbindung mit einer Datenbank herstellen können, die auf einer Benutzerinstanz ausgeführt wird. Replikation und verteilte Abfragen sind für Benutzerinstanzen ebenfalls deaktiviert.  
  
 Weitere Informationen dazu finden Sie im Abschnitt zu Benutzerinstanzen in der SQL Server-Onlinedokumentation.  
  
> [!NOTE]
>  Benutzer, die auf ihrem Computer bereits mit Administratorberechtigungen arbeiten, benötigen keine Benutzerinstanzen. Auch in Szenarien mit mehreren Datenbankbenutzern sind Benutzerinstanzen nicht erforderlich.  
  
## <a name="enabling-user-instances"></a>Aktivieren von Benutzerinstanzen  
 Zum Generieren von Benutzerinstanzen muss eine übergeordnete Instanz von SQL Server Express ausgeführt werden. Benutzerinstanzen sind standardmäßig aktiviert, wenn SQL Server Express installiert ist, und sie explizit aktiviert oder deaktiviert, die von einem Systemadministrator ausgeführt werden können die **Sp_configure** gespeicherte Systemprozedur für die übergeordnete Instanz.  
  
```  
-- Enable user instances.  
sp_configure 'user instances enabled','1'   
  
-- Disable user instances.  
sp_configure 'user instances enabled','0'  
```  
  
 Als Netzwerkprotokoll für Benutzerinstanzen kommen lokale Named Pipes zum Einsatz. Benutzerinstanzen können nicht auf einer Remoteinstanz von SQL Server gestartet werden, und SQL Server-Anmeldungen sind ebenfalls nicht zulässig.  
  
## <a name="connecting-to-a-user-instance"></a>Herstellen einer Verbindung mit einer Benutzerinstanz  
 Die `User Instance` und `AttachDBFilename` <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> Schlüsselwörter ermöglichen eine <xref:System.Data.SqlClient.SqlConnection> eine Verbindung mit einer Benutzerinstanz herstellen. Benutzerinstanzen werden auch von den <xref:System.Data.SqlClient.SqlConnectionStringBuilder>-Eigenschaften `UserInstance` und `AttachDBFilename` unterstützt.  
  
 Beachten Sie bei der unten genannten Beispielverbindungszeichenfolge Folgendes:  
  
-   Das `Data Source`-Schlüsselwort verweist auf die übergeordnete Instanz von SQL Server Express, die die Benutzerinstanz generiert. Die Standardinstanz ist .\sqlexpress.  
  
-   Für `Integrated Security` ist `true` festgelegt. Zur Herstellung einer Verbindung mit einer Benutzerinstanz ist die Windows-Authentifizierung erforderlich. SQL Server-Anmeldungen werden nicht unterstützt.  
  
-   Für `User Instance` ist `true` festgelegt, wodurch eine Benutzerinstanz aufgerufen wird. (Der Standardwert ist `false`.)  
  
-   Das Schlüsselwort für die `AttachDbFileName`-Verbindungszeichenfolge wird verwendet, um die primäre Datenbankdatei (.mdf) anzufügen. Diese muss den vollständigen Pfadnamen enthalten. `AttachDbFileName` entspricht auch den Schlüsseln "extended properties" und "initial file name" in einer <xref:System.Data.SqlClient.SqlConnection>-Verbindungszeichenfolge.  
  
-   Die `|DataDirectory|`-Ersatzzeichenfolge zwischen den vertikalen Strichen (|) verweist auf das Datenverzeichnis der Anwendung, die die Verbindung öffnet, und gibt den relativen Pfad zum Speicherort der MDF- und LDF-Datenbank- und Protokolldateien an. Wenn sich diese Dateien woanders befinden, müssen Sie den vollständigen Pfad zu den Dateien angeben.  
  
```  
Data Source=.\\SQLExpress;Integrated Security=true;  
User Instance=true;AttachDBFilename=|DataDirectory|\InstanceDB.mdf;  
Initial Catalog=InstanceDB;  
```  
  
> [!NOTE]
>  Sie können auch die <xref:System.Data.SqlClient.SqlConnectionStringBuilder> <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserInstance%2A> und <xref:System.Data.SqlClient.SqlConnectionStringBuilder.AttachDBFilename%2A> Eigenschaften erstellen Sie eine Verbindungszeichenfolge zur Laufzeit.  
  
### <a name="using-the-124datadirectory124-substitution-string"></a>Mithilfe der &#124; "DataDirectory" &#124; Ersatzzeichenfolge  
 `AttachDbFileName` wurde in ADO.NET 2.0 mit der Einführung der `|DataDirectory|`-Ersatzzeichenfolge (zwischen Pipesymbolen) erweitert. `DataDirectory` wird in Verbindung mit `AttachDbFileName` verwendet, um einen relativen Pfad zu einer Datendatei anzugeben. Damit wird es Entwicklern ermöglicht, Verbindungszeichenfolgen zu erstellen, die auf einem relativen Pfad zur Datenquelle basieren. Es muss kein vollständiger Pfad angegeben werden.  
  
 Auf welchen physischen Speicherort `DataDirectory` verweist, hängt von der Art der Anwendung ab. In diesem Beispiel befindet sich die anzufügende Datei <legacyBold>Northwind.mdf</legacyBold> im Ordner <legacyBold>\app_data</legacyBold> der Anwendung.  
  
```  
Data Source=.\\SQLExpress;Integrated Security=true;  
User Instance=true;  
AttachDBFilename=|DataDirectory|\app_data\Northwind.mdf;  
Initial Catalog=Northwind;  
```  
  
 Bei Verwendung von `DataDirectory` darf sich der resultierende Dateipfad in der Verzeichnisstruktur nicht über dem Verzeichnis befinden, auf das in der Ersatzzeichenfolge verwiesen wird. Wenn z. B. das vollständige Datenverzeichnis in `DataDirectory` <legacyBold>C:\AppDirectory\app_data</legacyBold> lautet, funktioniert die oben genannte Beispielverbindungszeichenfolge, weil sie sich unterhalb von <legacyBold>C:\AppDirectory</legacyBold> befindet. Wenn aber versucht wird, das `DataDirectory` als `|DataDirectory|\..\data` anzugeben, wird ein Fehler ausgelöst, weil <legacyBold>\data</legacyBold> kein Unterverzeichnis von <legacyBold>\AppDirectory</legacyBold> ist.  
  
 Wenn die Verbindungszeichenfolge eine nicht ordnungsgemäß formatierte Ersatzzeichenfolge enthält, wird eine <xref:System.ArgumentException> ausgelöst.  
  
> [!NOTE]
>  <xref:System.Data.SqlClient> löst die Ersatzzeichenfolgen in vollständige Pfade des Dateisystems auf dem lokalen Computer auf. Deshalb werden Remoteserver-, HTTP- und UNC-Pfadnamen nicht unterstützt. Wenn sich der Server nicht auf dem lokalen Computer befindet und die Verbindung geöffnet wird, wird eine Ausnahme ausgelöst.  
  
 Wenn die <xref:System.Data.SqlClient.SqlConnection> geöffnet ist, wird sie von der standardmäßigen SQL Server Express-Instanz an eine Instanz umgeleitet, die zur Laufzeit initiiert und unter dem Konto des Aufrufers ausgeführt wird.  
  
> [!NOTE]
>  Eventuell ist es notwendig, den Wert für <xref:System.Data.SqlClient.SqlConnection.ConnectionTimeout%2A> hoch zu setzen, da die Benutzerinstanzen u. U. mehr Zeit zum Laden benötigen als reguläre Instanzen.  
  
 Das folgende Codefragment öffnet eine neue `SqlConnection`, zeigt die Verbindungszeichenfolge im Konsolenfenster an und schließt dann beim Beenden des `using`-Codeblocks die Verbindung.  
  
```vb  
Private Sub OpenSqlConnection()  
    ' Retrieve the connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    Using connection As New SqlConnection(connectionString)  
        connection.Open()  
        Console.WriteLine("ConnectionString: {0}", _  
           connection.ConnectionString)  
    End Using  
End Sub  
```  
  
```csharp  
private static void OpenSqlConnection()  
{  
    // Retrieve the connection string.  
    string connectionString = GetConnectionString();  
  
    using (SqlConnection connection =   
        new SqlConnection(connectionString))  
    {  
        connection.Open();  
        Console.WriteLine("ConnectionString: {0}",   
             connection.ConnectionString);  
    }  
}  
```  
  
> [!NOTE]
>  Benutzerinstanzen werden von CLR-Code (Common Language Runtime), der innerhalb von SQL Server ausgeführt wird, nicht unterstützt. Es wird eine <xref:System.InvalidOperationException> ausgelöst, wenn `Open` für eine <xref:System.Data.SqlClient.SqlConnection> aufgerufen wird, deren Verbindungszeichenfolge `User Instance=true` enthält.  
  
## <a name="lifetime-of-a-user-instance-connection"></a>Lebensdauer einer Verbindung mit einer Benutzerinstanz  
 Im Unterschied zu SQL Server-Versionen, die als Dienst ausgeführt werden, müssen SQL Server Express-Instanzen nicht manuell gestartet und beendet werden. Die Benutzerinstanz wird gestartet, sobald sich ein Benutzer anmeldet und eine Verbindung mit einer Benutzerinstanz herstellt, sofern sie nicht bereits ausgeführt wird. Die `AutoClose`-Option ist bei Benutzerinstanzdatenbanken so eingerichtet, dass die Datenbank nach einer bestimmten Zeit der Inaktivität automatisch geschlossen wird. Der Prozess sqlservr.exe läuft nach dem Schließen der letzten Verbindung mit der Instanz für einen gewissen Zeitraum weiter und muss daher nicht neu gestartet werden, wenn innerhalb dieser Zeit eine andere Verbindung geöffnet wird. Wird innerhalb dieser Zeit keine neue Verbindung geöffnet wird, wird die Benutzerinstanz automatisch geschlossen. Ein Systemadministrator für die übergeordnete Instanz kann die Dauer des Timeoutzeitraums für eine Benutzerinstanz festlegen, mit **Sp_configure** so ändern Sie die **Timeout für Benutzerinstanz** Option. Der Standardwert ist 60 Minuten.  
  
> [!NOTE]
>  Wenn in der Verbindungszeichenfolge `Min Pool Size` mit einem Wert größer als 0 verwendet wird, hält die Verbindungspoolfunktion stets einige geöffnete Verbindungen aufrecht, und die Benutzerinstanz wird nicht automatisch geschlossen.  
  
## <a name="how-user-instances-work"></a>So funktionieren Benutzerinstanzen  
 Zum ersten Mal eine Benutzerinstanz wird für jeden Benutzer generiert die **master** und **Msdb** Systemdatenbanken aus dem Ordner für Vorlagendaten in einen Pfad im lokalen Anwendung-Datenrepository des Benutzers kopiert werden Verzeichnis für die ausschließliche Verwendung durch die Benutzerinstanz. Dieser Pfad lautet in der Regel `C:\Documents and Settings\<UserName>\Local Settings\Application Data\Microsoft\Microsoft SQL Server Data\SQLEXPRESS`. Wenn eine Benutzerinstanz gestartet wurde, die **Tempdb**, Protokoll- und Ablaufverfolgungsdateien Dateien auch in dieses Verzeichnis geschrieben. Es wird ein Name für die Instanz generiert, der für jeden Benutzer garantiert eindeutig ist.  
  
 Standardmäßig sind alle Member der Gruppe <legacyBold>Windows Builtin\Users</legacyBold> berechtigt, über die lokale Instanz Verbindungen herzustellen und die SQL Server-Binärdateien zu lesen und auszuführen. Nachdem die Anmeldeinformationen des Benutzers verifiziert wurden, der die Benutzerinstanz hostet, wird dieser Benutzer zum `sysadmin` für diese Instanz. Für Benutzerinstanzen ist nur ein gemeinsam genutzter Speicherbereich (Shared Memory) aktiviert, sodass der Benutzer nur Vorgänge auf seinem lokalen Computer ausführen kann.  
  
 Die Benutzer müssen sowohl Lese- als auch Schreibberechtigungen für die in der Verbindungszeichenfolge angegebenen MDF- und LDF-Dateien erhalten.  
  
> [!NOTE]
>  Bei der MDF- und der LDF-Datei handelt es sich um die Datenbank- bzw. um die Protokolldatei. Diese beiden Dateien sind ein zusammengehöriger Satz, daher ist bei Sicherungs- und Wiederherstellungsvorgängen Vorsicht geboten. Die Datenbankdatei enthält Informationen zur exakten Version der Protokolldatei, und wenn die Datenbankdatei mit der falschen Protokolldatei gekoppelt wird, kann sie nicht geöffnet werden.  
  
 Um die Beschädigung von Daten zu vermeiden, werden Datenbanken in der Benutzerinstanz mit exklusivem Zugriff geöffnet. Wenn zwei verschiedene Benutzerinstanzen auf dieselbe Datenbank auf demselben Computer zugreifen, muss der Benutzer der ersten Benutzerinstanz die Datenbank schließen, bevor der Benutzer der zweiten Benutzerinstanz die Datenbank öffnen kann.  
  
## <a name="user-instance-scenarios"></a>Benutzerinstanzszenarien  
 Benutzerinstanzen stellen Entwicklern von Datenbankanwendungen einen SQL Server-Datenspeicher zur Verfügung, der nicht voraussetzt, dass die Entwickler auf ihren Entwicklungscomputern mit Administratorberechtigungen arbeiten. Benutzerinstanzen basieren auf dem Access/Jet-Modell, bei dem die Datenbankanwendung einfach eine Verbindung mit einer Datei herstellt und der Benutzer automatisch volle Berechtigungen für alle Datenbankobjekte erhält, ohne dass ein Systemadministrator eingreifen und diese Berechtigungen gewähren muss. Die Verwendung dieses Modells bietet sich für Situationen an, in denen der Benutzer mit einem Konto der untersten Berechtigungsebene (Least-Priviledged User Account, LUA) arbeitet und keine Administratorberechtigungen für den Server oder den lokalen Computer besitzt, dennoch aber Datenbankobjekte und Anwendungen erstellen können muss. Mit Benutzerinstanzen können Benutzer Laufzeitinstanzen erstellen, die im Sicherheitskontext des Benutzers und nicht im Sicherheitskontext eines Systemdienstes mit umfangreicheren Berechtigungen ausgeführt werden.  
  
> [!IMPORTANT]
>  Benutzerinstanzen sollten nur in Szenarien eingesetzt werden, in denen alle Anwendungen, die die Instanzen verwenden, vollständig vertrauenswürdig sind.  
  
 Zu den Benutzerinstanzszenarien gehören folgende Szenarien:  
  
-   alle Einzelbenutzeranwendungen, in denen keine Datenfreigabe erforderlich ist  
  
-   ClickOnce-Bereitstellung: Auf Computern, auf denen .NET Framework 2.0 (oder höher) und SQL Server Express bereits installiert sind, kann das im Rahmen einer ClickOnce-Aktion heruntergeladene Installationspaket installiert und von Benutzern ohne Administratorberechtigung verwendet werden. Beachten Sie, dass die Installation von SQL Server Express, sofern diese Teil des Setups ist, von einem Administrator vorgenommen werden muss. Weitere Informationen finden Sie unter [ClickOnce-Bereitstellung für Windows Forms-Anwendungen](http://msdn.microsoft.com/library/34d8c770-48f2-460c-8d67-4ea5684511df).  
  
-   dediziertes ASP.NET-Hosting mit Windows-Authentifizierung: Eine einzelne SQL Server Express-Instanz kann in einem Intranet gehostet werden. Die Anwendung stellt die Verbindung über das ASPNET-Windows-Konto und nicht durch einen Identitätswechsel her. Benutzerinstanzen dürfen nicht in Drittanbieterszenarien oder Szenarien mit gemeinsamem Hosting verwendet werden, in denen alle Anwendungen dieselbe Benutzerinstanz nutzen und damit nicht mehr voneinander isoliert sind.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
