---
title: Authentifizierung in SQL Server
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: 0fb92f9e854e2a7a800335390d0195243a749b33
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74959971"
---
# <a name="authentication-in-sql-server"></a>Authentifizierung in SQL Server
SQL Server unterstützt zwei Authentifizierungsmodi: den Windows-Authentifizierungsmodus und den gemischten Modus.  
  
- Die Windows-Authentifizierung ist der Standard. Sie wird häufig auch als "integrierte Sicherheit" bezeichnet, weil dieses SQL Server-Sicherheitsmodell eng in Windows integriert ist. Dabei gelten bestimmte Windows-Benutzer- und -Gruppenkonten als so vertrauenswürdig, dass sie sich bei SQL Server anmelden dürfen. Windows-Benutzer, die bereits authentifiziert wurden, müssen keine zusätzlichen Anmeldeinformationen zur Verfügung stellen.  
  
- Der gemischte Modus unterstützt die Authentifizierung durch Windows und durch SQL Server. Die Paare aus Benutzername und Kennwort werden innerhalb von SQL Server beibehalten.  
  
> [!IMPORTANT]
> Es wird empfohlen, möglichst immer die Windows-Authentifizierung zu verwenden. Die Windows-Authentifizierung verwendet zum Authentifizieren der Benutzer in SQL Server eine Reihe verschlüsselter Meldungen. Bei der Verwendung von SQL Server-Anmeldungen werden die SQL Server-Anmeldenamen und verschlüsselten Kennwörter über das Netzwerk übertragen und damit angreifbar.  
  
 Bei der Windows-Authentifizierung sind die Benutzer bereits bei Windows angemeldet und müssen sich nicht noch einmal bei SQL Server anmelden. Die folgende `SqlConnection.ConnectionString` legt Windows-Authentifizierung fest, bei der Benutzer weder Benutzernamen noch Kennwort angeben müssen.  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> Anmeldungen und Datenbankbenutzer sind nicht dasselbe. Sie müssen Anmeldungen oder Windows-Gruppen in einem separaten Vorgang Datenbankbenutzern oder Rollen zuordnen. Anschließend gewähren Sie den Benutzern oder Rollen Berechtigungen, damit diese auf die Datenbankobjekte zugreifen können.  
  
## <a name="authentication-scenarios"></a>Authentifizierungsszenarien  
 In den folgenden Situationen ist die Windows-Authentifizierung in der Regel die beste Wahl:  
  
- Es gibt einen Domänencontroller.  
  
- Die Anwendung und die Datenbank befinden sich auf demselben Computer.  
  
- Sie verwenden eine Instanz von SQL Server Express oder LocalDB.  
  
 SQL Server-Anmeldungen werden im Allgemeinen in den folgenden Situationen verwendet:  
  
- Wenn Sie über eine Arbeitsgruppe verfügen.  
  
- Die Benutzer stellen die Verbindung von unterschiedlichen, nicht vertrauenswürdigen Domänen aus her.  
  
- Internet Anwendungen, z. b. ASP.net.  
  
> [!NOTE]
> Das Angeben der Windows-Authentifizierung führt nicht zu einer Deaktivierung von SQL Server-Anmeldungen. Wenn Sie die SQL Server-Anmeldungen mit den weit reichenden Berechtigungen deaktivieren möchten, verwenden Sie die Transact-SQL-ALTER LOGIN DISABLE-Anweisung.  
  
## <a name="login-types"></a>Anmeldungstypen  
 SQL Server unterstützt die folgenden drei Anmeldungstypen:  
  
- Lokales Windows-Benutzerkonto oder vertrauenswürdiges Domänenkonto: SQL Server verlässt sich bei der Authentifizierung der Windows-Benutzerkonten auf Windows.  
  
- Windows-Gruppe: Wenn einer Windows-Gruppe Zugriff gewährt wird, gelten diese Zugriffsrechte für alle Windows-Benutzeranmeldungen, die dieser Gruppe angehören.  
  
- SQL Server-Anmeldung: SQL Server speichert in der Masterdatenbank den Benutzernamen und einen Hash des Kennworts. Für die Überprüfung der Anmeldungsversuche werden interne Authentifizierungsmethoden verwendet.  
  
> [!NOTE]
> SQL Server stellt auf Grundlage von Zertifikaten oder asymmetrischen Schlüsseln erstellte Anmeldungen bereit, die ausschließlich für die Codesignierung verwendet werden. Zum Herstellen einer Verbindung mit SQL Server können sie nicht verwendet werden.  
  
## <a name="mixed-mode-authentication"></a>Authentifizierung im gemischten Modus  
 Wenn die Authentifizierung im gemischten Modus verwendet werden soll, müssen Sie SQL Server-Anmeldungen erstellen, die in SQL Server gespeichert werden. Zur Laufzeit müssen dann der SQL Server-Benutzername und das Kennwort angegeben werden.  
  
> [!IMPORTANT]
> SQL Server wird mit einer SQL Server-Anmeldung mit dem Namen `sa` (kurz für "Systemadministrator") installiert. Weisen Sie der `sa`-Anmeldung ein starkes Kennwort zu, und verwenden Sie die `sa`-Anmeldung nicht in Ihrer Anwendung. Die `sa`-Anmeldung wird der festen Serverrolle `sysadmin` zugeordnet, die nicht widerrufbare administrative Anmeldeinformationen für den gesamten Server besitzt. Wenn es einem Angreifer gelingt, sich als Systemadministrator Zugriff zu verschaffen, stehen ihm Tür und Tor offen. Alle Member der Windows-Gruppe `BUILTIN\Administrators` (der lokalen Administratorgruppe) gehören standardmäßig der Rolle `sysadmin` an, können aber aus dieser Rolle entfernt werden.  
  
 SQL Server stellt Windows-Kenn Wort Richtlinien Mechanismen für SQL Server Anmeldungen bereit. Richtlinien zur Kennwortkomplexität werden als Maßnahme gegen Brute Force-Angriffe entworfen. Dabei wird die Anzahl der möglichen Kennwörter erhöht. SQL Server können die gleichen Komplexitäts-und Ablauf Richtlinien auf die in SQL Server verwendeten Kenn Wörter anwenden.  
  
> [!IMPORTANT]
> Das Verketten von Verbindungszeichenfolgen aus Benutzereingaben kann zu einer Anfälligkeit für Angriffe durch Einschleusung von Verbindungszeichenfolgen führen. Verwenden Sie zum Erstellen syntaktisch gültiger Verbindungszeichenfolgen zur Laufzeit den <xref:System.Data.SqlClient.SqlConnectionStringBuilder>. Weitere Informationen finden Sie in [Connection String Builders (Verbindungszeichenfolgengeneratoren)](../connection-string-builders.md).  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Principals](/sql/relational-databases/security/authentication-access/principals-database-engine)|Beschreibt Anmeldungen und andere Sicherheitsprinzipale in SQL Server.|  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Aufbauen der Verbindung zu einer Datenquelle](../connecting-to-a-data-source.md)
- [Verbindungszeichenfolgen](../connection-strings.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
