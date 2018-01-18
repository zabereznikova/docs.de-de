---
title: Sicherheit in LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0ee361c27bd14f0266b2b86f315f9c091e049c12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="security-in-linq-to-sql"></a><span data-ttu-id="86911-102">Sicherheit in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="86911-102">Security in LINQ to SQL</span></span>
<span data-ttu-id="86911-103">Beim Herstellen einer Datenbankverbindung müssen Sie stets mit Risiken rechnen.</span><span class="sxs-lookup"><span data-stu-id="86911-103">Security risks are always present when you connect to a database.</span></span> <span data-ttu-id="86911-104">Obwohl LINQ to SQL möglicherweise über einige neue Möglichkeiten zur Arbeit mit Daten in SQL Server verfügt, stellt es keine zusätzlichen Sicherheitsmechanismen bereit.</span><span class="sxs-lookup"><span data-stu-id="86911-104">Although LINQ to SQL may include some new ways to work with data in SQL Server, it does not provide any additional security mechanisms.</span></span>  
  
## <a name="access-control-and-authentication"></a><span data-ttu-id="86911-105">Zugriffssteuerung und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="86911-105">Access Control and Authentication</span></span>  
 <span data-ttu-id="86911-106">LINQ to SQL verfügt weder über ein eigenes Benutzermodell noch über Authentifizierungsmechanismen.</span><span class="sxs-lookup"><span data-stu-id="86911-106">LINQ to SQL does not have its own user model or authentication mechanisms.</span></span> <span data-ttu-id="86911-107">Verwenden Sie SQL Server-Sicherheit zum Steuern des Zugriffs auf die Datenbank, Datenbanktabellen, Ansichten und gespeicherte Prozeduren, die Ihrem Objektmodell zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="86911-107">Use SQL Server Security to control access to the database, database tables, views, and stored procedures that are mapped to your object model.</span></span> <span data-ttu-id="86911-108">Gewähren Sie die minimal erforderlichen Zugriffsrechte für Benutzer und fordern Sie sichere Kennwörter zur Benutzerauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="86911-108">Grant the minimally required access to users and require strong passwords for user authentication.</span></span>  
  
## <a name="mapping-and-schema-information"></a><span data-ttu-id="86911-109">Zuordnung und Schemainformationen</span><span class="sxs-lookup"><span data-stu-id="86911-109">Mapping and Schema Information</span></span>  
 <span data-ttu-id="86911-110">SQL-CLR-Typzuordnung und Datenbankschemainformationen im Objektmodell oder in der externen Zuordnungsdatei stehen allen Benutzern zur Verfügung, die auf die Dateien im Dateisystem zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="86911-110">SQL-CLR type mapping and database schema information in your object model or external mapping file is available for all with access to those files in the file system.</span></span> <span data-ttu-id="86911-111">Angenommen, die Schemainformationen stehen allen Benutzern zur Verfügung, die auf das Objektmodell oder die externe Zuordnungsdatei zugreifen können. Um den Zugriff von einer breiteren Benutzerbasis zu verhindern, können Sie die Quelldateien und Zuordnungsdateien mithilfe von Dateisicherheitsmechanismen sichern.</span><span class="sxs-lookup"><span data-stu-id="86911-111">Assume that schema information will be available to all who can access the object model or external mapping file.To prevent more widespread access to schema information, use file security mechanisms to secure source files and mapping files.</span></span>  
  
## <a name="connection-strings"></a><span data-ttu-id="86911-112">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="86911-112">Connection Strings</span></span>  
 <span data-ttu-id="86911-113">Vermeiden Sie nach Möglichkeit die Verwendung von Kennwörtern in Verbindungszeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="86911-113">Using passwords in connection strings should be avoided whenever possible.</span></span> <span data-ttu-id="86911-114">Eine Verbindungszeichenfolge ein nicht nur ein Sicherheitsrisiko an sich; die Verbindungszeichenfolge kann dem Objektmodell oder der externen Zuordnungsdatei auch als Klartext hinzugefügt werden, wenn der O/R-Designer oder das SQLMetal-Befehlszeilentool verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86911-114">Not only is a connection string a security risk in its own right, but the connection string may also be added in clear text to the object model or external mapping file when using the Object Relational Designer or SQLMetal command-line tool.</span></span> <span data-ttu-id="86911-115">Jeder Benutzer mit Zugriff auf das Objektmodell oder die externe Zuordnungsdatei über das Dateisystem kann das Verbindungskennwort erkennen, wenn es in der Verbindungszeichenfolge enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="86911-115">Anyone with access to the object model or external mapping file via the file system could see the connection password (if it is included in the connection string).</span></span>  
  
 <span data-ttu-id="86911-116">Um solche Risiken zu minimieren, verwenden Sie integrierte Sicherheit, um eine sichere Verbindung mit [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] herzustellen.</span><span class="sxs-lookup"><span data-stu-id="86911-116">To minimize such risks, use integrated security to make a trusted connection with [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86911-117">Bei diesem Ansatz müssen Sie kein Kennwort in der Verbindungszeichenfolge speichern.</span><span class="sxs-lookup"><span data-stu-id="86911-117">By using this approach, you do not have to store a password in the connection string.</span></span> <span data-ttu-id="86911-118">Weitere Informationen finden Sie unter [SQL Server-Sicherheit](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span><span class="sxs-lookup"><span data-stu-id="86911-118">For more information, see [SQL Server Security](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span></span>  
  
 <span data-ttu-id="86911-119">Wenn keine integrierte Sicherheit vorhanden ist, ist in der in der Verbindungszeichenfolge ein Kennwort im Klartext erforderlich.</span><span class="sxs-lookup"><span data-stu-id="86911-119">In the absence of integrated security, a clear-text password will be needed in the connection string.</span></span> <span data-ttu-id="86911-120">Folgendes sind die besten Möglichkeiten, die Verbindungszeichenfolge zu sichern (sicherste Möglichkeiten zuerst):</span><span class="sxs-lookup"><span data-stu-id="86911-120">The best way to help secure your connection string, in increasing order of risk, is as follows:</span></span>  
  
-   <span data-ttu-id="86911-121">Verwenden der integrierten Sicherheit</span><span class="sxs-lookup"><span data-stu-id="86911-121">Use integrated security.</span></span>  
  
-   <span data-ttu-id="86911-122">Sichern von Verbindungszeichenfolgen mit Kennwörtern und Minimieren der Weitergabe von Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="86911-122">Secure connection strings with passwords and minimize passing around connection strings.</span></span>  
  
-   <span data-ttu-id="86911-123">Verwenden einer <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType>-Klasse anstelle einer Verbindungszeichenfolge, da die Bereitstellung nur begrenzt ist</span><span class="sxs-lookup"><span data-stu-id="86911-123">Use a <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> class instead of a connection string since it limits the duration of exposure.</span></span> <span data-ttu-id="86911-124">Instanziieren der <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>-Klasse in LINQ to SQL mit einem <xref:System.Data.SqlClient.SqlConnection>-Objekt</span><span class="sxs-lookup"><span data-stu-id="86911-124">The LINQ to SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> class can be instantiated using a <xref:System.Data.SqlClient.SqlConnection>.</span></span>  
  
-   <span data-ttu-id="86911-125">Minimieren der Lebensdauer und Berührungsereignisse aller Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="86911-125">Minimize lifetimes and touch points for all connection strings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86911-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86911-126">See Also</span></span>  
 [<span data-ttu-id="86911-127">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="86911-127">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="86911-128">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="86911-128">Frequently Asked Questions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
