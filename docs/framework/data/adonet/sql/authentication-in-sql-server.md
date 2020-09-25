---
title: Authentifizierung in SQL Server
description: Erfahren Sie mehr über die Authentifizierung mit SQL Server für ADO.net, einschließlich Windows-Authentifizierungsmodus und gemischter Modus.
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: 2c4f62391a0d9b5ada27f56eef4c3467d99b4c6d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197529"
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="2a94d-103">Authentifizierung in SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a94d-103">Authentication in SQL Server</span></span>

<span data-ttu-id="2a94d-104">SQL Server unterstützt zwei Authentifizierungsmodi: den Windows-Authentifizierungsmodus und den gemischten Modus.</span><span class="sxs-lookup"><span data-stu-id="2a94d-104">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
- <span data-ttu-id="2a94d-105">Die Windows-Authentifizierung ist der Standard. Sie wird häufig auch als "integrierte Sicherheit" bezeichnet, weil dieses SQL Server-Sicherheitsmodell eng in Windows integriert ist.</span><span class="sxs-lookup"><span data-stu-id="2a94d-105">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="2a94d-106">Bestimmte Benutzer- und Gruppenkonten in Windows werden für die Anmeldung bei SQL Server als vertrauenswürdig eingestuft.</span><span class="sxs-lookup"><span data-stu-id="2a94d-106">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="2a94d-107">Windows-Benutzer, die bereits authentifiziert wurden, müssen keine zusätzlichen Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-107">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
- <span data-ttu-id="2a94d-108">Der gemischte Modus unterstützt die Authentifizierung durch Windows und durch SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2a94d-108">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="2a94d-109">Die Paare aus Benutzername und Kennwort werden innerhalb von SQL Server verwaltet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-109">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2a94d-110">Es wird empfohlen, wenn möglich stets die Windows-Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-110">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="2a94d-111">Die Windows-Authentifizierung verwendet zum Authentifizieren der Benutzer in SQL Server eine Reihe verschlüsselter Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2a94d-111">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="2a94d-112">Bei der Verwendung von SQL Server-Anmeldungen werden die SQL Server-Anmeldenamen und verschlüsselten Kennwörter über das Netzwerk übertragen und damit angreifbar.</span><span class="sxs-lookup"><span data-stu-id="2a94d-112">When SQL Server logins are used, SQL Server login names and encrypted passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="2a94d-113">Bei der Windows-Authentifizierung sind die Benutzer bereits bei Windows angemeldet und müssen sich nicht noch einmal bei SQL Server anmelden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-113">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="2a94d-114">Die folgende `SqlConnection.ConnectionString` legt Windows-Authentifizierung fest, bei der Benutzer weder Benutzernamen noch Kennwort angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-114">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring users to provide a user name or password.</span></span>  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="2a94d-115">Anmeldungen sind nicht mit Datenbankbenutzern identisch.</span><span class="sxs-lookup"><span data-stu-id="2a94d-115">Logins are distinct from database users.</span></span> <span data-ttu-id="2a94d-116">Sie müssen Anmeldungen oder Windows-Gruppen separat zu Datenbankbenutzern oder -rollen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-116">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="2a94d-117">Anschließend erteilen Sie Benutzern oder Rollen Berechtigungen für den Zugriff auf Datenbankobjekte.</span><span class="sxs-lookup"><span data-stu-id="2a94d-117">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="2a94d-118">Authentifizierungsszenarien</span><span class="sxs-lookup"><span data-stu-id="2a94d-118">Authentication Scenarios</span></span>  

 <span data-ttu-id="2a94d-119">Die Windows-Authentifizierung ist üblicherweise in den folgenden Situationen die beste Wahl:</span><span class="sxs-lookup"><span data-stu-id="2a94d-119">Windows authentication is usually the best choice in the following situations:</span></span>  
  
- <span data-ttu-id="2a94d-120">Es gibt einen Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="2a94d-120">There is a domain controller.</span></span>  
  
- <span data-ttu-id="2a94d-121">Die Anwendung und die Datenbank befinden sich auf demselben Computer.</span><span class="sxs-lookup"><span data-stu-id="2a94d-121">The application and the database are on the same computer.</span></span>  
  
- <span data-ttu-id="2a94d-122">Sie verwenden eine Instanz von SQL Server Express oder LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2a94d-122">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="2a94d-123">SQL Server-Anmeldungen werden häufig in den folgenden Situationen verwendet:</span><span class="sxs-lookup"><span data-stu-id="2a94d-123">SQL Server logins are often used in the following situations:</span></span>  
  
- <span data-ttu-id="2a94d-124">Sie verfügen über eine Arbeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="2a94d-124">If you have a workgroup.</span></span>  
  
- <span data-ttu-id="2a94d-125">Benutzer verbinden sich über unterschiedliche, nicht vertrauenswürdige Domänen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-125">Users connect from different, non-trusted domains.</span></span>  
  
- <span data-ttu-id="2a94d-126">Internetanwendungen wie ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2a94d-126">Internet applications, such as ASP.NET.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a94d-127">Das Angeben der Windows-Authentifizierung führt nicht zu einer Deaktivierung von SQL Server-Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-127">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="2a94d-128">Wenn Sie die SQL Server-Anmeldungen mit den weit reichenden Berechtigungen deaktivieren möchten, verwenden Sie die Transact-SQL-ALTER LOGIN DISABLE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2a94d-128">Use the ALTER LOGIN DISABLE Transact-SQL statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="2a94d-129">Anmeldungstypen</span><span class="sxs-lookup"><span data-stu-id="2a94d-129">Login Types</span></span>  

 <span data-ttu-id="2a94d-130">SQL Server unterstützt die folgenden drei Anmeldungstypen:</span><span class="sxs-lookup"><span data-stu-id="2a94d-130">SQL Server supports three types of logins:</span></span>  
  
- <span data-ttu-id="2a94d-131">Ein lokales Windows-Benutzerkonto oder ein vertrauenswürdiges Domänenkonto.</span><span class="sxs-lookup"><span data-stu-id="2a94d-131">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="2a94d-132">SQL Server nutzt zur Authentifizierung der Windows-Benutzerkonten die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2a94d-132">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
- <span data-ttu-id="2a94d-133">Windows-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="2a94d-133">Windows group.</span></span> <span data-ttu-id="2a94d-134">Wenn Sie Zugriff für eine Windows-Gruppe gewähren, wird der Zugriff für alle Windows-Benutzeranmeldungen gewährt, die Mitglieder der Gruppe sind.</span><span class="sxs-lookup"><span data-stu-id="2a94d-134">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
- <span data-ttu-id="2a94d-135">SQL Server-Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="2a94d-135">SQL Server login.</span></span> <span data-ttu-id="2a94d-136">SQL Server speichert den Benutzernamen und einen Hash des Kennworts in der Masterdatenbank. Zur Überprüfung der Anmeldeversuche werden interne Authentifizierungsmethoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-136">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a94d-137">SQL Server stellt auf Grundlage von Zertifikaten oder asymmetrischen Schlüsseln erstellte Anmeldungen bereit, die ausschließlich für die Codesignierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-137">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="2a94d-138">Sie können nicht verwendet werden, um eine Verbindung mit SQL Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-138">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="2a94d-139">Authentifizierung im gemischten Modus</span><span class="sxs-lookup"><span data-stu-id="2a94d-139">Mixed Mode Authentication</span></span>  

 <span data-ttu-id="2a94d-140">Wenn die Authentifizierung im gemischten Modus erforderlich ist, müssen Sie SQL Server-Anmeldungen erstellen, die in SQL Server gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-140">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="2a94d-141">Zur Laufzeit müssen dann der SQL Server-Benutzername und das Kennwort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-141">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2a94d-142">SQL Server wird mit der SQL Server-Anmeldung `sa` installiert (eine Abkürzung für „Systemadministrator“).</span><span class="sxs-lookup"><span data-stu-id="2a94d-142">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="2a94d-143">Weisen Sie der Anmeldung `sa` ein sicheres Kennwort zu, und verwenden Sie die Anmeldung `sa` nicht in Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2a94d-143">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="2a94d-144">Die Anmeldung `sa` ist der festen Serverrolle `sysadmin` zugeordnet, die über unwiderrufliche Administratoranmeldeinformationen auf dem gesamten Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-144">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="2a94d-145">Wenn ein Angreifer Zugriff als Systemadministrator erhält, ist der potenzielle Schaden enorm.</span><span class="sxs-lookup"><span data-stu-id="2a94d-145">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="2a94d-146">Alle Member der Windows-Gruppe `BUILTIN\Administrators` (der lokalen Administratorgruppe) gehören standardmäßig der Rolle `sysadmin` an, können aber aus dieser Rolle entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-146">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="2a94d-147">SQL Server stellt Windows-Kenn Wort Richtlinien Mechanismen für SQL Server Anmeldungen bereit.</span><span class="sxs-lookup"><span data-stu-id="2a94d-147">SQL Server provides Windows password policy mechanisms for SQL Server logins.</span></span> <span data-ttu-id="2a94d-148">Richtlinien zur Kennwortkomplexität werden als Maßnahme gegen Brute Force-Angriffe entworfen. Dabei wird die Anzahl der möglichen Kennwörter erhöht.</span><span class="sxs-lookup"><span data-stu-id="2a94d-148">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="2a94d-149">SQL Server können die gleichen Komplexitäts-und Ablauf Richtlinien auf die in SQL Server verwendeten Kenn Wörter anwenden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-149">SQL Server can apply the same complexity and expiration policies to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2a94d-150">Durch das Verketten von Verbindungszeichenfolgen aus Benutzereingaben kann ein System anfällig für Angriffe durch Einschleusung von Verbindungszeichenfolgen werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-150">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="2a94d-151">Verwenden Sie <xref:System.Data.SqlClient.SqlConnectionStringBuilder>, um zur Laufzeit Verbindungszeichenfolgen mit gültiger Syntax zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-151">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="2a94d-152">Weitere Informationen finden Sie in [Connection String Builders (Verbindungszeichenfolgengeneratoren)](../connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="2a94d-152">For more information, see [Connection String Builders](../connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="2a94d-153">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="2a94d-153">External Resources</span></span>  

 <span data-ttu-id="2a94d-154">Weitere Informationen finden Sie in den folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-154">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="2a94d-155">Resource</span><span class="sxs-lookup"><span data-stu-id="2a94d-155">Resource</span></span>|<span data-ttu-id="2a94d-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a94d-156">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="2a94d-157">Principals</span><span class="sxs-lookup"><span data-stu-id="2a94d-157">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="2a94d-158">Beschreibt Anmeldungen und andere Sicherheitsprinzipale in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2a94d-158">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a94d-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a94d-159">See also</span></span>

- [<span data-ttu-id="2a94d-160">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2a94d-160">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="2a94d-161">Anwendungssicherheitsszenarios in SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a94d-161">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="2a94d-162">Herstellen der Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="2a94d-162">Connecting to a Data Source</span></span>](../connecting-to-a-data-source.md)
- [<span data-ttu-id="2a94d-163">Verbindungs Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="2a94d-163">Connection Strings</span></span>](../connection-strings.md)
- [<span data-ttu-id="2a94d-164">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2a94d-164">ADO.NET Overview</span></span>](../ado-net-overview.md)
