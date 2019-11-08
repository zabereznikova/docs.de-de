---
title: Sicherer Datenzugriff
ms.date: 03/30/2017
ms.assetid: 473ebd69-21a3-4627-b95e-4e04d035c56f
ms.openlocfilehash: c08f41be67f5d87635021e86ba5a5b33af9304cd
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735280"
---
# <a name="secure-data-access"></a>Sicherer Datenzugriff
Wenn Sie sicheren ADO.NET-Code schreiben möchten, müssen Sie die Sicherheitsmechanismen kennen, die im zugrunde liegenden Datenspeicher oder der zugrundeliegenden Datenbank verfügbar sind. Außerdem müssen Sie die Auswirkungen anderer in Ihrer Anwendung enthaltenen Funktionen oder Komponenten auf die Sicherheit berücksichtigen.  
  
## <a name="authentication-authorization-and-permissions"></a>Authentifizierung, Autorisierung und Berechtigungen  
 Beim Herstellen einer Verbindung mit Microsoft SQL Server können Sie die Windows-Authentifizierung (auch als "Integrierte Sicherheit" bezeichnet) verwenden, bei der nicht die Benutzer-ID und das Kennwort übermittelt werden, sondern die Identität des jeweils aktiven Windows-Benutzers verwendet wird. Die Verwendung der Windows-Authentifizierung wird dringend empfohlen, da die dabei verwendete Verbindungszeichenfolge keinerlei Benutzeranmeldeinformationen enthält, sodass diese Informationen vor unbefugtem Zugriff geschützt sind. Wenn Sie für die Herstellung von Verbindungen mit SQL Server nicht auf die Windows-Authentifizierung zurückgreifen können, sollten Sie erwägen, die Verbindungszeichenfolgen zur Laufzeit mit dem <xref:System.Data.SqlClient.SqlConnectionStringBuilder> zu erstellen.  
  
 Die zur Authentifizierung verwendeten Anmeldeinformationen müssen je nach der Art der Anwendung unterschiedlich behandelt werden. In einer Windows Forms-Anwendung kann ein Benutzer beispielsweise aufgefordert werden, Authentifizierungsinformationen einzugeben, oder es können dessen Windows-Anmeldeinformationen verwendet werden. Eine Webanwendung hingegen greift auf Daten mithilfe von Anmeldeinformationen zu, die von der Anwendung selbst und nicht vom Benutzer bereitgestellt werden.  
  
 Welche Aktionen die Benutzer nach der Authentifizierung ausführen dürfen, hängt von den Berechtigungen ab, die ihnen erteilt wurden. Befolgen Sie dabei strikt das Prinzip der minimalen Rechtegewährung: Gewähren Sie immer nur die Berechtigungen, die absolut notwendig sind.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Protecting Connection Information (Schützen von Verbindungsinformationen)](protecting-connection-information.md)|Beschreibt bewährte Methoden und Techniken zum Schützen von Verbindungsinformationen, z. B. das Verwenden der geschützten Konfiguration zur Verschlüsselung von Verbindungszeichenfolgen.|  
|[Empfehlungen für Datenzugriffs Strategien](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/8fxztkff(v=vs.90))|Enthält Empfehlungen für das Zugreifen auf Daten und das Ausführen von Datenbankoperationen.|  
|[Verbindungszeichenfolgengeneratoren](connection-string-builders.md)|Beschreibt, wie aus Benutzereingabe zur Laufzeit Verbindungszeichenfolgen erstellt werden können.|  
|[Übersicht über die SQL Server-Sicherheit](./sql/overview-of-sql-server-security.md)|Beschreibt die SQL Server-Sicherheitsarchitektur.|  
  
## <a name="parameterized-commands-and-sql-injection"></a>Parametrisierte Befehle und SQL Injection  
 Die Verwendung parametrisierter Befehle hilft beim Schutz vor SQL Injection-Angriffen, bei denen ein Angreifer einen SQL-Befehl in eine SQL-Anweisung einschleust, der die Sicherheit auf dem Server gefährdet. Parametrisierte Befehle schützen vor solchen Angriffen, indem sie dafür sorgen, dass Werte aus einer externen Quelle lediglich als Werte und nicht als Bestandteil einer Transact-SQL-Anweisung weitergeleitet werden. In einen Wert eingefügte Transact-SQL-Befehle werden daher nicht in der Datenquelle ausgeführt. Stattdessen werden sie nur als Parameterwert ausgewertet. Parametrisierte Befehle sind aber nicht nur aus Sicherheitsgründen vorteilhaft, sondern sie stellen auch eine bequeme Methode zum Organisieren von Werten dar, die mit einer Transact-SQL-Anweisung weitergeleitet bzw. an eine gespeicherte Prozedur übergeben werden.  
  
 Weitere Informationen zur Verwendung parametrisierter Befehle finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[DataAdapter-Parameter](dataadapter-parameters.md)|Beschreibt die Verwendung von Parametern mit einem `DataAdapter`.|  
|[Ändern von Daten mit gespeicherten Prozeduren](modifying-data-with-stored-procedures.md)|Beschreibt das Angeben von Parametern und das Abrufen von Rückgabewerten.|  
|[Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](./sql/managing-permissions-with-stored-procedures-in-sql-server.md)|Beschreibt die Verwendung gespeicherter SQL Server-Prozeduren zum Kapseln des Datenzugriffs.|  
  
## <a name="script-exploits"></a>Skriptexploits  
 Ein Skriptexploit ist eine andere Form der Einschleusung, bei der in eine Webseite schädliche Zeichen eingeschleust werden. Der Browser überprüft die eingefügten Zeichen nicht und verarbeitet sie als Teil der Seite.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Übersicht über Skript Exploits](https://docs.microsoft.com/previous-versions/aspnet/w1sw53ds(v=vs.100))|Beschreibt, wie Sie sich vor Skript- und SQL-Anweisung-Exploits schützen können.|  
  
## <a name="probing-attacks"></a>Angriffe anhand von ausgewerteten Fehlerinformationen  
 Angreifer verwenden für ihre Angriffe häufig Informationen aus Fehlermeldungen. Diese können z. B. Aufschluss über den Namen des Servers, der Datenbank oder der Tabelle geben. Da Fehlermeldungen spezifische Informationen über eine Anwendung bzw. Datenquelle enthalten können, können Sie die Anwendung bzw. Datenquelle besser schützen, indem Sie lediglich Informationen verfügbar machen, die vom Client explizit angefordert werden.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Behandeln und Auslösen von Ausnahmen in .NET](../../../standard/exceptions/index.md)|Beschreibt die grundlegenden Formen der Behandlung von Ausnahmen mit der "try/catch/finally"-Struktur.|  
|[Bewährte Methoden für Ausnahmen](../../../standard/exceptions/best-practices-for-exceptions.md)|Beschreibt bewährte Vorgehensweisen bei der Behandlung von Ausnahmen.|  
  
## <a name="protecting-microsoft-access-and-excel-data-sources"></a>Schützen von Microsoft Access- und Excel-Datenquellen  
 Microsoft Access und Microsoft Excel können dort, wo die Sicherheitsanforderungen nur minimal sind, als Datenspeicher für ADO.NET-Anwendungen fungieren. Deren Sicherheitsfunktionen sind zwar zur Abschreckung unwissender Benutzer geeignet, können aber von erfahrenen Angreifern durchaus umgangen werden. Die physischen Datendateien für Access und Excel befinden sich im Dateisystem, und der Zugriff darauf muss für alle Benutzer gewährleistet sein. Sie sind daher für Angriffe anfällig, bei denen Daten gestohlen oder zerstört werden, denn sie können problemlos kopiert oder bearbeitet werden. Wenn also eine robustere Sicherheit verlangt wird, verwenden Sie SQL Server oder eine andere serverbasierte Datenbank, in der die physischen Datendateien nicht aus dem Dateisystem gelesen werden können.  
  
 Weitere Informationen zum Schützen von Access- und Excel-Daten finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Sicherheitsüberlegungen und Anleitungen für den Zugriff 2007](https://go.microsoft.com/fwlink/?LinkId=98354)|Beschreibt die Sicherheitsverfahren von Access 2007, wie die Verschlüsselung von Dateien, die Verwaltung von Kennwörtern und die Umwandlung von Datenbanken in die neuen Formate ACCDB und ACCDE sowie die Verwendung anderer Sicherheitsoptionen.|  
|[Grundlegendes zur Rolle der Arbeitsgruppen-Informationsdateien in Access Security](https://support.microsoft.com/kb/305542)|Erläutert die Rolle und die Beziehung der Arbeitsgruppeninformationsdatei in der Access 2003-Sicherheit.|  
|[Häufig gestellte Fragen zu Microsoft Access Security für Microsoft Access-Versionen 2,0 bis 2000](https://go.microsoft.com/fwlink/?LinkId=47698)|Herunterladbare Version der Antworten auf häufig gestellte Fragen (FAQ) zum Thema "Sicherheit in Microsoft Access".|  
## <a name="enterprise-services"></a>Enterprise Services  
 COM+ enthält ein eigenes Sicherheitsmodell, das auf die Windows NT-Konten und den Prozess-/Threadidentitätswechsel zurückgreift. Der <xref:System.EnterpriseServices>-Namespace stellt Wrapper bereit, die es .NET-Anwendungen ermöglichen, über die <xref:System.EnterpriseServices.ServicedComponent>-Klasse verwalteten Code mit COM+-Sicherheitsdiensten zu integrieren.  
  
 Weitere Informationen finden Sie in der folgenden Ressource:  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Rollenbasierte Sicherheit](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/s6y8k15h(v=vs.71))|Erläutert, wie verwalteter Code mit COM+-Sicherheitsdiensten integriert werden kann.|  
  
## <a name="interoperating-with-unmanaged-code"></a>Interoperation mit nicht verwaltetem Code  
 .NET Framework ermöglicht die Interaktion mit nicht verwaltetem Code, darunter COM-Komponenten, COM+-Diensten, externen Typbibliotheken und vielen Betriebssystemdiensten. Beim Arbeiten mit nicht verwaltetem Code wird die "Sicherheitszone" des verwalteten Codes verlassen. Sowohl Ihr Code als auch jeder Code, der Ihren Code aufruft, muss eine Berechtigung für nicht verwalteten Code besitzen (<xref:System.Security.Permissions.SecurityPermission> mit <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>-Flag). Nicht verwalteter Code kann für Ihre Anwendung unbeabsichtigte Sicherheitslücken bedeuten. Deshalb sollten Sie mit nicht verwaltetem Code nur interagieren, wenn dies absolut notwendig ist.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Interoperabilität mit nicht verwaltetem Code](../../interop/index.md)|Enthält Themen, die beschreiben, wie COM-Komponenten für .NET Framework und .NET Framework-Komponenten für COM verfügbar gemacht werden sollten.|
|[Erweiterte COM-Interoperabilität](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))|Enthält zusätzliche Themen, in denen es u. a. um primäre Interopassemblys, Threading und benutzerdefiniertes Marshalling geht.|

## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](securing-ado-net-applications.md)
- [SQL Server Security (SQL Server-Sicherheit)](./sql/sql-server-security.md)
- [Empfehlungen für Datenzugriffs Strategien](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/8fxztkff(v=vs.90))
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](protecting-connection-information.md)
- [Verbindungszeichenfolgengeneratoren](connection-string-builders.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
