---
title: Authentifizierung in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e3b597d04ee53a094d9c50dff406f57e5fd57b00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="authentication-in-sql-server"></a>Authentifizierung in SQL Server
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] unterstützt zwei Authentifizierungsmodi: den Windows-Authentifizierungsmodus und den gemischten Modus.  
  
-   Die Windows-Authentifizierung ist der Standard. Sie wird häufig auch als "integrierte Sicherheit" bezeichnet, weil dieses [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Sicherheitsmodell eng in Windows integriert ist. Dabei gelten bestimmte Windows-Benutzer- und -Gruppenkonten als so vertrauenswürdig, dass sie sich bei SQL Server anmelden dürfen. Windows-Benutzer, die bereits authentifiziert wurden, müssen keine zusätzlichen Anmeldeinformationen zur Verfügung stellen.  
  
-   Der gemischte Modus unterstützt die Authentifizierung durch Windows und durch [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. Die Paare aus Benutzername und Kennwort werden innerhalb von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] verwaltet.  
  
> [!IMPORTANT]
>  Es wird empfohlen, möglichst immer die Windows-Authentifizierung zu verwenden. Die Windows-Authentifizierung verwendet zum Authentifizieren der Benutzer in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] eine Reihe verschlüsselter Nachrichten. Bei der Verwendung von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Anmeldungen werden die [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Anmeldenamen und -Kennwörter über das Netzwerk übertragen und damit angreifbar.  
  
 Bei der Windows-Authentifizierung sind die Benutzer bereits bei Windows angemeldet und müssen sich nicht noch einmal bei [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] anmelden. Die folgende `SqlConnection.ConnectionString` gibt die Windows-Authentifizierung an, bei der Benutzername und Kennwort nicht erforderlich sind.  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  Anmeldungen und Datenbankbenutzer sind nicht dasselbe. Sie müssen Anmeldungen oder Windows-Gruppen in einem separaten Vorgang Datenbankbenutzern oder Rollen zuordnen. Anschließend gewähren Sie den Benutzern oder Rollen Berechtigungen, damit diese auf die Datenbankobjekte zugreifen können.  
  
## <a name="authentication-scenarios"></a>Authentifizierungsszenarien  
 In den folgenden Situationen ist die Windows-Authentifizierung in der Regel die beste Wahl:  
  
-   Es gibt einen Domänencontroller.  
  
-   Die Anwendung und die Datenbank befinden sich auf demselben Computer.  
  
-   Sie verwenden eine Instanz von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express oder LocalDB.  
  
 SQL Server-Anmeldungen werden im Allgemeinen in den folgenden Situationen verwendet:  
  
-   Wenn Sie über eine Arbeitsgruppe verfügen.  
  
-   Die Benutzer stellen die Verbindung von unterschiedlichen, nicht vertrauenswürdigen Domänen aus her.  
  
-   Internetanwendungen, z. B. [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  
  
> [!NOTE]
>  Das Angeben der Windows-Authentifizierung führt nicht zu einer Deaktivierung von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Anmeldungen. Wenn Sie [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]-Anmeldungen mit hohen Berechtigungsstufen deaktivieren möchten, verwenden Sie die [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Anweisung ALTER LOGIN DISABLE.  
  
## <a name="login-types"></a>Anmeldungstypen  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] unterstützt die folgenden drei Anmeldetypen:  
  
-   Lokales Windows-Benutzerkonto oder vertrauenswürdiges Domänenkonto: [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] nutzt zur Authentifizierung der Windows-Benutzerkonten die Windows-Authentifizierung.  
  
-   Windows-Gruppe: Wenn einer Windows-Gruppe Zugriff gewährt wird, gelten diese Zugriffsrechte für alle Windows-Benutzeranmeldungen, die dieser Gruppe angehören.  
  
-   [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Anmeldung. [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] speichert den Benutzernamen und einen Hash des Kennworts in der master-Datenbank. Zur Überprüfung der Anmeldeversuche werden interne Authentifizierungsmethoden verwendet.  
  
> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] stellt auf Grundlage von Zertifikaten oder asymmetrischen Schlüsseln erstellte Anmeldungen bereit, die ausschließlich für die Codesignierung verwendet werden. Sie können nicht zum Herstellen einer Verbindung mit [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] verwendet werden.  
  
## <a name="mixed-mode-authentication"></a>Authentifizierung im gemischten Modus  
 Wenn die Authentifizierung im gemischten Modus erforderlich ist, müssen Sie [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Anmeldungen erstellen, die in SQL Server gespeichert werden. Zur Laufzeit müssen dann der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Benutzername und das Kennwort angegeben werden.  
  
> [!IMPORTANT]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] wird mit einer [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Anmeldung mit dem Namen `sa` (kurz für "Systemadministrator") installiert. Weisen Sie der `sa`-Anmeldung ein starkes Kennwort zu, und verwenden Sie die `sa`-Anmeldung nicht in Ihrer Anwendung. Die `sa`-Anmeldung wird der festen Serverrolle `sysadmin` zugeordnet, die nicht widerrufbare administrative Anmeldeinformationen für den gesamten Server besitzt. Wenn es einem Angreifer gelingt, sich als Systemadministrator Zugriff zu verschaffen, stehen ihm Tür und Tor offen. Alle Member der Windows-Gruppe `BUILTIN\Administrators` (der lokalen Administratorgruppe) gehören standardmäßig der Rolle `sysadmin` an, können aber aus dieser Rolle entfernt werden.  
  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] bietet die Möglichkeit, Windows-Kennwortrichtlinien auf [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Anmeldungen anzuwenden, sofern die Ausführung unter [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] oder höher erfolgt. Richtlinien zur Kennwortkomplexität werden als Maßnahme gegen Brute Force-Angriffe entworfen. Dabei wird die Anzahl der möglichen Kennwörter erhöht. [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] kann dieselben Komplexitäts- und Ablaufrichtlinien anwenden, die in [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] für Kennwörter in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] verwendet werden.  
  
> [!IMPORTANT]
>  Das Verketten von Verbindungszeichenfolgen aus Benutzereingaben kann zu einer Anfälligkeit für Angriffe durch Einschleusung von Verbindungszeichenfolgen führen. Verwenden Sie zum Erstellen syntaktisch gültiger Verbindungszeichenfolgen zur Laufzeit den <xref:System.Data.SqlClient.SqlConnectionStringBuilder>. Weitere Informationen finden Sie unter [Verbindungszeichenfolgen-Generatoren](../../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Prinzipale](http://msdn.microsoft.com/library/bb543165.aspx) in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] -Onlinedokumentation|Beschreibt Anmeldungen und andere Sicherheitsprinzipale in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Anwendungssicherheitsszenarios in SQLServer](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
