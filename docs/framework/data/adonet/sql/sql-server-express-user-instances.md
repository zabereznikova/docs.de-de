---
title: SQL Server Express-Benutzerinstanzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 00c12376-cb26-4317-86ad-e6e9c089be57
ms.openlocfilehash: fabd9b94b8c0a3f0e0db220e84d6c2eca3537c50
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894420"
---
# <a name="sql-server-express-user-instances"></a>SQL Server Express-Benutzerinstanzen
Microsoft SQL Server Express Edition (SQL Server Express) unterstützt die Benutzerinstanzfunktion, die die Verwendung des .NET Framework-Datenanbieters für SQL Server (`SqlClient`) voraussetzt. Eine Benutzerinstanz ist eine separate Instanz der SQL Server Express-Datenbank-Engine, die von einer übergeordneten Instanz generiert wird. Mit Benutzerinstanzen können Benutzer, die auf ihrem lokalen Computer nicht mit Administratorrechten arbeiten, eine Verbindung zu SQL Server Express-Datenbanken herstellen. Jede Instanz wird im Sicherheitskontext des jeweiligen Benutzers ausgeführt, wobei für jeden Benutzer genau eine Instanz erstellt wird.  
  
## <a name="user-instance-capabilities"></a>Was können Benutzerinstanzen?  
 Benutzerinstanzen eignen sich für Benutzer, die Windows in einem Konto der untersten Berechtigungsebene (Least-Priviledged User Account, LUA) ausführen, da jeder Benutzer über SQL Server-Systemadministratorberechtigungen (`sysadmin`) für die Instanz verfügt, die auf seinem Computer ausgeführt wird, ohne dass dazu auch Windows mit Administratorrechten ausgeführt werden muss. Software, die in einer Benutzerinstanz mit eingeschränkten Berechtigungen ausgeführt wird, kann keine systemweiten Änderungen vornehmen, da die SQL Server Express-Instanz beim Benutzer über das Windows-Konto ohne Administratorberechtigung und nicht als Dienst ausgeführt wird. Jede Benutzerinstanz ist von ihrer übergeordneten Instanz und von allen anderen Benutzerinstanzen isoliert, die auf demselben Computer ausgeführt werden. Auf einer Benutzerinstanz installierte Datenbanken werden nur im Einzelbenutzermodus geöffnet. Es ist ausgeschlossen, dass mehrere Benutzer eine Verbindung mit einer Datenbank herstellen können, die auf einer Benutzerinstanz ausgeführt wird. Replikation und verteilte Abfragen sind für Benutzerinstanzen ebenfalls deaktiviert.  
  
 Weitere Informationen dazu finden Sie im Abschnitt zu Benutzerinstanzen in der SQL Server-Onlinedokumentation.  
  
> [!NOTE]
> Benutzer, die auf ihrem Computer bereits mit Administratorberechtigungen arbeiten, benötigen keine Benutzerinstanzen. Auch in Szenarien mit mehreren Datenbankbenutzern sind Benutzerinstanzen nicht erforderlich.  
  
## <a name="enabling-user-instances"></a>Aktivieren von Benutzerinstanzen  
 Zum Generieren von Benutzerinstanzen muss eine übergeordnete Instanz von SQL Server Express ausgeführt werden. Benutzer Instanzen werden standardmäßig aktiviert, wenn SQL Server Express installiert ist. Sie können von einem Systemadministrator, der die gespeicherte System Prozedur **sp_configure** auf der übergeordneten Instanz ausführt, explizit aktiviert oder deaktiviert werden.  
  
```sql  
-- Enable user instances.  
sp_configure 'user instances enabled','1'
  
-- Disable user instances.  
sp_configure 'user instances enabled','0'  
```  
  
 Als Netzwerkprotokoll für Benutzerinstanzen kommen lokale Named Pipes zum Einsatz. Benutzerinstanzen können nicht auf einer Remoteinstanz von SQL Server gestartet werden, und SQL Server-Anmeldungen sind ebenfalls nicht zulässig.  
  
## <a name="connecting-to-a-user-instance"></a>Herstellen einer Verbindung mit einer Benutzerinstanz  
 Mit `User Instance` den `AttachDBFilename` Schlüsselwörtern und <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> kann eine eine <xref:System.Data.SqlClient.SqlConnection> Verbindung mit einer Benutzer Instanz herstellen. Benutzerinstanzen werden auch von den <xref:System.Data.SqlClient.SqlConnectionStringBuilder>-Eigenschaften `UserInstance` und `AttachDBFilename` unterstützt.  
  
 Beachten Sie bei der unten genannten Beispielverbindungszeichenfolge Folgendes:  
  
- Das `Data Source`-Schlüsselwort verweist auf die übergeordnete Instanz von SQL Server Express, die die Benutzerinstanz generiert. Die Standardinstanz ist .\sqlexpress.  
  
- Für `Integrated Security` ist `true` festgelegt. Zur Herstellung einer Verbindung mit einer Benutzerinstanz ist die Windows-Authentifizierung erforderlich. SQL Server-Anmeldungen werden nicht unterstützt.  
  
- Für `User Instance` ist `true` festgelegt, wodurch eine Benutzerinstanz aufgerufen wird. (Der Standardwert ist `false`.)  
  
- Das Schlüsselwort für die `AttachDbFileName`-Verbindungszeichenfolge wird verwendet, um die primäre Datenbankdatei (.mdf) anzufügen. Diese muss den vollständigen Pfadnamen enthalten. `AttachDbFileName` entspricht auch den Schlüsseln "extended properties" und "initial file name" in einer <xref:System.Data.SqlClient.SqlConnection>-Verbindungszeichenfolge.  
  
- Die `|DataDirectory|`-Ersatzzeichenfolge zwischen den vertikalen Strichen (|) verweist auf das Datenverzeichnis der Anwendung, die die Verbindung öffnet, und gibt den relativen Pfad zum Speicherort der MDF- und LDF-Datenbank- und Protokolldateien an. Wenn sich diese Dateien woanders befinden, müssen Sie den vollständigen Pfad zu den Dateien angeben.  
  
```text
Data Source=.\\SQLExpress;Integrated Security=true;  
User Instance=true;AttachDBFilename=|DataDirectory|\InstanceDB.mdf;  
Initial Catalog=InstanceDB;  
```  
  
> [!NOTE]
> Sie können mit der <xref:System.Data.SqlClient.SqlConnectionStringBuilder><xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserInstance%2A>-Eigenschaft und der <xref:System.Data.SqlClient.SqlConnectionStringBuilder.AttachDBFilename%2A>-Eigenschaft eine Verbindungszeichenfolge zur Laufzeit erstellen.  
  
### <a name="using-the-124datadirectory124-substitution-string"></a>Verwenden der &#124;DataDirectory&#124; -Ersetzungs Zeichenfolge  
 `AttachDbFileName` wurde in ADO.NET 2.0 mit der Einführung der `|DataDirectory|`-Ersatzzeichenfolge (zwischen Pipesymbolen) erweitert. `DataDirectory` wird in Verbindung mit `AttachDbFileName` verwendet, um einen relativen Pfad zu einer Datendatei anzugeben. Damit wird es Entwicklern ermöglicht, Verbindungszeichenfolgen zu erstellen, die auf einem relativen Pfad zur Datenquelle basieren. Es muss kein vollständiger Pfad angegeben werden.  
  
 Auf welchen physischen Speicherort `DataDirectory` verweist, hängt von der Art der Anwendung ab. In diesem Beispiel befindet sich die anzufügende Datei Northwind.mdf im Ordner \app_data der Anwendung.  
  
```text
Data Source=.\\SQLExpress;Integrated Security=true;  
User Instance=true;  
AttachDBFilename=|DataDirectory|\app_data\Northwind.mdf;  
Initial Catalog=Northwind;  
```  
  
 Bei Verwendung von `DataDirectory` darf sich der resultierende Dateipfad in der Verzeichnisstruktur nicht über dem Verzeichnis befinden, auf das in der Ersatzzeichenfolge verwiesen wird. Wenn z. B. das vollständige Datenverzeichnis in C:\AppDirectory\app_data`DataDirectory` lautet, funktioniert die oben genannte Beispielverbindungszeichenfolge, weil sie sich unterhalb von C:\AppDirectory befindet. Wenn aber versucht wird, das `DataDirectory` als `|DataDirectory|\..\data` anzugeben, wird ein Fehler ausgelöst, weil &lt;legacyBold&gt;\data&lt;/legacyBold&gt; kein Unterverzeichnis von &lt;legacyBold&gt;\AppDirectory&lt;/legacyBold&gt; ist.  
  
 Wenn die Verbindungszeichenfolge eine nicht ordnungsgemäß formatierte Ersatzzeichenfolge enthält, wird eine <xref:System.ArgumentException> ausgelöst.  
  
> [!NOTE]
> <xref:System.Data.SqlClient> löst die Ersatzzeichenfolgen in vollständige Pfade des Dateisystems auf dem lokalen Computer auf. Deshalb werden Remoteserver-, HTTP- und UNC-Pfadnamen nicht unterstützt. Wenn sich der Server nicht auf dem lokalen Computer befindet und die Verbindung geöffnet wird, wird eine Ausnahme ausgelöst.  
  
 Wenn die <xref:System.Data.SqlClient.SqlConnection> geöffnet ist, wird sie von der standardmäßigen SQL Server Express-Instanz an eine Instanz umgeleitet, die zur Laufzeit initiiert und unter dem Konto des Aufrufers ausgeführt wird.  
  
> [!NOTE]
> Eventuell ist es notwendig, den Wert für <xref:System.Data.SqlClient.SqlConnection.ConnectionTimeout%2A> hoch zu setzen, da die Benutzerinstanzen u. U. mehr Zeit zum Laden benötigen als reguläre Instanzen.  
  
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
> Benutzerinstanzen werden von CLR-Code (Common Language Runtime), der innerhalb von SQL Server ausgeführt wird, nicht unterstützt. Es wird eine <xref:System.InvalidOperationException> ausgelöst, wenn `Open` für eine <xref:System.Data.SqlClient.SqlConnection> aufgerufen wird, deren Verbindungszeichenfolge `User Instance=true` enthält.  
  
## <a name="lifetime-of-a-user-instance-connection"></a>Lebensdauer einer Verbindung mit einer Benutzerinstanz  
 Im Unterschied zu SQL Server-Versionen, die als Dienst ausgeführt werden, müssen SQL Server Express-Instanzen nicht manuell gestartet und beendet werden. Die Benutzerinstanz wird gestartet, sobald sich ein Benutzer anmeldet und eine Verbindung mit einer Benutzerinstanz herstellt, sofern sie nicht bereits ausgeführt wird. Die `AutoClose`-Option ist bei Benutzerinstanzdatenbanken so eingerichtet, dass die Datenbank nach einer bestimmten Zeit der Inaktivität automatisch geschlossen wird. Der Prozess sqlservr.exe läuft nach dem Schließen der letzten Verbindung mit der Instanz für einen gewissen Zeitraum weiter und muss daher nicht neu gestartet werden, wenn innerhalb dieser Zeit eine andere Verbindung geöffnet wird. Wird innerhalb dieser Zeit keine neue Verbindung geöffnet wird, wird die Benutzerinstanz automatisch geschlossen. Ein Systemadministrator auf der übergeordneten Instanz kann die Dauer des Timeout Zeitraums für eine Benutzer Instanz mithilfe von **sp_configure** festlegen, um die Timeout Option für die **Benutzer Instanz** zu ändern. Der Standardwert ist 60 Minuten.  
  
> [!NOTE]
> Wenn in der Verbindungszeichenfolge `Min Pool Size` mit einem Wert größer als 0 verwendet wird, hält die Verbindungspoolfunktion stets einige geöffnete Verbindungen aufrecht, und die Benutzerinstanz wird nicht automatisch geschlossen.  
  
## <a name="how-user-instances-work"></a>So funktionieren Benutzerinstanzen  
 Wenn eine Benutzer Instanz zum ersten Mal für jeden Benutzer generiert wird, werden die System Datenbanken **Master** und **msdb** aus dem Ordner Vorlagen Daten in einen Pfad im Verzeichnis des lokalen Anwendungsdatenrepository des Benutzers kopiert, um die Benutzer Instanz exklusiv zu verwenden. Dieser Pfad lautet in der Regel `C:\Documents and Settings\<UserName>\Local Settings\Application Data\Microsoft\Microsoft SQL Server Data\SQLEXPRESS`. Wenn eine Benutzer Instanz gestartet wird, werden die **tempdb**-, Protokoll-und Ablauf Verfolgungs Dateien ebenfalls in dieses Verzeichnis geschrieben. Es wird ein Name für die Instanz generiert, der für jeden Benutzer garantiert eindeutig ist.  
  
 Standardmäßig sind alle Member der Gruppe &lt;legacyBold&gt;Windows Builtin\Users&lt;/legacyBold&gt; berechtigt, über die lokale Instanz Verbindungen herzustellen und die SQL Server-Binärdateien zu lesen und auszuführen. Nachdem die Anmeldeinformationen des Benutzers verifiziert wurden, der die Benutzerinstanz hostet, wird dieser Benutzer zum `sysadmin` für diese Instanz. Für Benutzerinstanzen ist nur ein gemeinsam genutzter Speicherbereich (Shared Memory) aktiviert, sodass der Benutzer nur Vorgänge auf seinem lokalen Computer ausführen kann.  
  
 Die Benutzer müssen sowohl Lese- als auch Schreibberechtigungen für die in der Verbindungszeichenfolge angegebenen MDF- und LDF-Dateien erhalten.  
  
> [!NOTE]
> Bei der MDF- und der LDF-Datei handelt es sich um die Datenbank- bzw. um die Protokolldatei. Diese beiden Dateien sind ein zusammengehöriger Satz, daher ist bei Sicherungs- und Wiederherstellungsvorgängen Vorsicht geboten. Die Datenbankdatei enthält Informationen zur exakten Version der Protokolldatei, und wenn die Datenbankdatei mit der falschen Protokolldatei gekoppelt wird, kann sie nicht geöffnet werden.  
  
 Um die Beschädigung von Daten zu vermeiden, werden Datenbanken in der Benutzerinstanz mit exklusivem Zugriff geöffnet. Wenn zwei verschiedene Benutzerinstanzen auf dieselbe Datenbank auf demselben Computer zugreifen, muss der Benutzer der ersten Benutzerinstanz die Datenbank schließen, bevor der Benutzer der zweiten Benutzerinstanz die Datenbank öffnen kann.  
  
## <a name="user-instance-scenarios"></a>Benutzerinstanzszenarien  
 Benutzerinstanzen stellen Entwicklern von Datenbankanwendungen einen SQL Server-Datenspeicher zur Verfügung, der nicht voraussetzt, dass die Entwickler auf ihren Entwicklungscomputern mit Administratorberechtigungen arbeiten. Benutzerinstanzen basieren auf dem Access/Jet-Modell, bei dem die Datenbankanwendung einfach eine Verbindung mit einer Datei herstellt und der Benutzer automatisch volle Berechtigungen für alle Datenbankobjekte erhält, ohne dass ein Systemadministrator eingreifen und diese Berechtigungen gewähren muss. Die Verwendung dieses Modells bietet sich für Situationen an, in denen der Benutzer mit einem Konto der untersten Berechtigungsebene (Least-Priviledged User Account, LUA) arbeitet und keine Administratorberechtigungen für den Server oder den lokalen Computer besitzt, dennoch aber Datenbankobjekte und Anwendungen erstellen können muss. Mit Benutzerinstanzen können Benutzer Laufzeitinstanzen erstellen, die im Sicherheitskontext des Benutzers und nicht im Sicherheitskontext eines Systemdienstes mit umfangreicheren Berechtigungen ausgeführt werden.  
  
> [!IMPORTANT]
> Benutzerinstanzen sollten nur in Szenarien eingesetzt werden, in denen alle Anwendungen, die die Instanzen verwenden, vollständig vertrauenswürdig sind.  
  
 Zu den Benutzerinstanzszenarien gehören folgende Szenarien:  
  
- alle Einzelbenutzeranwendungen, in denen keine Datenfreigabe erforderlich ist  
  
- ClickOnce-Bereitstellung: Auf Computern, auf denen .NET Framework 2.0 (oder höher) und SQL Server Express bereits installiert sind, kann das im Rahmen einer ClickOnce-Aktion heruntergeladene Installationspaket installiert und von Benutzern ohne Administratorberechtigung verwendet werden. Beachten Sie, dass die Installation von SQL Server Express, sofern diese Teil des Setups ist, von einem Administrator vorgenommen werden muss. Weitere Informationen finden Sie unter [ClickOnce-Bereitstellung für Windows Forms](../../../winforms/clickonce-deployment-for-windows-forms.md).
  
- dediziertes ASP.NET-Hosting mit Windows-Authentifizierung: Eine einzelne SQL Server Express-Instanz kann in einem Intranet gehostet werden. Die Anwendung stellt die Verbindung über das ASPNET-Windows-Konto und nicht durch einen Identitätswechsel her. Benutzerinstanzen dürfen nicht in Drittanbieterszenarien oder Szenarien mit gemeinsamem Hosting verwendet werden, in denen alle Anwendungen dieselbe Benutzerinstanz nutzen und damit nicht mehr voneinander isoliert sind.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server und ADO.NET](index.md)
- [Verbindungszeichenfolgen](../connection-strings.md)
- [Aufbauen der Verbindung zu einer Datenquelle](../connecting-to-a-data-source.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
