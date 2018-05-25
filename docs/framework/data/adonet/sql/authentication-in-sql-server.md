---
title: Authentifizierung in SQL Server
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: f2d290d22d27c43cf7fb3250bf7898e8260dce2b
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="authentication-in-sql-server"></a>Authentifizierung in SQL Server
SQL Server unterstützt zwei Authentifizierungsmodi: den Windows-Authentifizierungsmodus und den gemischten Modus.  
  
-   Die Windows-Authentifizierung ist der Standard. Sie wird häufig auch als "integrierte Sicherheit" bezeichnet, weil dieses SQL Server-Sicherheitsmodell eng in Windows integriert ist. Dabei gelten bestimmte Windows-Benutzer- und -Gruppenkonten als so vertrauenswürdig, dass sie sich bei SQL Server anmelden dürfen. Windows-Benutzer, die bereits authentifiziert wurden, müssen keine zusätzlichen Anmeldeinformationen zur Verfügung stellen.  
  
-   Der gemischte Modus unterstützt die Authentifizierung durch Windows und durch SQL Server. Die Paare aus Benutzername und Kennwort werden innerhalb von SQL Server beibehalten.  
  
> [!IMPORTANT]
>  Es wird empfohlen, möglichst immer die Windows-Authentifizierung zu verwenden. Die Windows-Authentifizierung verwendet zum Authentifizieren der Benutzer in SQL Server eine Reihe verschlüsselter Meldungen. Wenn SQL Server-Anmeldungen verwendet werden, sind SQL Server-Anmeldenamen und verschlüsselte Kennwörter über das Netzwerk übergeben, wodurch sie weniger sicher.  
  
 Bei der Windows-Authentifizierung sind die Benutzer bereits bei Windows angemeldet und müssen sich nicht noch einmal bei SQL Server anmelden. Die folgende `SqlConnection.ConnectionString` gibt die Windows-Authentifizierung an, bei der Benutzername und Kennwort nicht erforderlich sind.  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  Anmeldungen und Datenbankbenutzer sind nicht dasselbe. Sie müssen Anmeldungen oder Windows-Gruppen in einem separaten Vorgang Datenbankbenutzern oder Rollen zuordnen. Anschließend gewähren Sie den Benutzern oder Rollen Berechtigungen, damit diese auf die Datenbankobjekte zugreifen können.  
  
## <a name="authentication-scenarios"></a>Authentifizierungsszenarien  
 In den folgenden Situationen ist die Windows-Authentifizierung in der Regel die beste Wahl:  
  
-   Es gibt einen Domänencontroller.  
  
-   Die Anwendung und die Datenbank befinden sich auf demselben Computer.  
  
-   Verwenden Sie eine Instanz von SQL Server Express oder LocalDB.  
  
 SQL Server-Anmeldungen werden im Allgemeinen in den folgenden Situationen verwendet:  
  
-   Wenn Sie über eine Arbeitsgruppe verfügen.  
  
-   Die Benutzer stellen die Verbindung von unterschiedlichen, nicht vertrauenswürdigen Domänen aus her.  
  
-   Internetanwendungen, z. B. [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  
  
> [!NOTE]
>  Das Angeben der Windows-Authentifizierung führt nicht zu einer Deaktivierung von SQL Server-Anmeldungen. Verwenden Sie die ALTER LOGIN DISABLE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] Anweisung, um SQL Server-Anmeldungen für hoch privilegierten deaktivieren.  
  
## <a name="login-types"></a>Anmeldungstypen  
 SQL Server unterstützt drei Arten von Anmeldenamen:  
  
-   Lokales Windows-Benutzerkonto oder vertrauenswürdiges Domänenkonto: SQL Server verlässt sich bei der Authentifizierung der Windows-Benutzerkonten auf Windows.  
  
-   Windows-Gruppe: Wenn einer Windows-Gruppe Zugriff gewährt wird, gelten diese Zugriffsrechte für alle Windows-Benutzeranmeldungen, die dieser Gruppe angehören.  
  
-   SQL Server-Anmeldung: SQL Server speichert in der Masterdatenbank den Benutzernamen und einen Hash des Kennworts. Für die Überprüfung der Anmeldungsversuche werden interne Authentifizierungsmethoden verwendet.  
  
> [!NOTE]
>  SQL Server bietet Anmeldungen von Zertifikaten oder asymmetrischen Schlüsseln, die nur zum Signieren von Code verwendet werden. Zum Herstellen einer Verbindung mit SQL Server können sie nicht verwendet werden.  
  
## <a name="mixed-mode-authentication"></a>Authentifizierung im gemischten Modus  
 Wenn die Authentifizierung im gemischten Modus verwendet werden soll, müssen Sie SQL Server-Anmeldungen erstellen, die in SQL Server gespeichert werden. Zur Laufzeit müssen dann der SQL Server-Benutzername und das Kennwort angegeben werden.  
  
> [!IMPORTANT]
>  SQL Server wird mit einer SQL Server-Anmeldung mit dem Namen `sa` (kurz für "Systemadministrator") installiert. Weisen Sie der `sa`-Anmeldung ein starkes Kennwort zu, und verwenden Sie die `sa`-Anmeldung nicht in Ihrer Anwendung. Die `sa`-Anmeldung wird der festen Serverrolle `sysadmin` zugeordnet, die nicht widerrufbare administrative Anmeldeinformationen für den gesamten Server besitzt. Wenn es einem Angreifer gelingt, sich als Systemadministrator Zugriff zu verschaffen, stehen ihm Tür und Tor offen. Alle Member der Windows-Gruppe `BUILTIN\Administrators` (der lokalen Administratorgruppe) gehören standardmäßig der Rolle `sysadmin` an, können aber aus dieser Rolle entfernt werden.  
  
 SQL Server bietet Windows-kennwortrichtlinienmechanismen für SQL Server-Anmeldungen aus, wenn er ausgeführt wird, auf [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] oder höhere Versionen. Richtlinien zur Kennwortkomplexität werden als Maßnahme gegen Brute Force-Angriffe entworfen. Dabei wird die Anzahl der möglichen Kennwörter erhöht. SQL Server können die gleichen Komplexität und dieselben Ablaufrichtlinien verwendet anwenden [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] , Kennwörter, die in SQL Server verwendet.  
  
> [!IMPORTANT]
>  Das Verketten von Verbindungszeichenfolgen aus Benutzereingaben kann zu einer Anfälligkeit für Angriffe durch Einschleusung von Verbindungszeichenfolgen führen. Verwenden Sie zum Erstellen syntaktisch gültiger Verbindungszeichenfolgen zur Laufzeit den <xref:System.Data.SqlClient.SqlConnectionStringBuilder>. Weitere Informationen finden Sie unter [Verbindungszeichenfolgen-Generatoren](../../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Prinzipale](http://msdn.microsoft.com/library/bb543165.aspx) in SQL Server-Onlinedokumentation|Beschreibt Anmeldungen und andere Sicherheitsprinzipale in SQL Server.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
