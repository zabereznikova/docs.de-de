---
title: "SqlClient für Entity Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3cb7880621a849b7162ea5f86ee0786f6184ea58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="9b6e8-102">SqlClient für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="9b6e8-102">SqlClient for the Entity Framework</span></span>
<span data-ttu-id="9b6e8-103">Dieser Abschnitt beschreibt den .NET Framework-Datenanbieter für SQL Server (SqlClient), der dem Entity Framework die Arbeit mit Microsoft SQL Server ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="9b6e8-104">Anbieterschemaattribut</span><span class="sxs-lookup"><span data-stu-id="9b6e8-104">Provider Schema Attribute</span></span>  
 <span data-ttu-id="9b6e8-105">`Provider` ist ein Attribut des `Schema`-Elements der Datenspeicherschema-Definitionssprache (Store Schema Definition Language, SSDL).</span><span class="sxs-lookup"><span data-stu-id="9b6e8-105">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="9b6e8-106">Um SqlClient zu verwenden, weisen Sie dem `Provider`-Attribut des `Schema`-Elements die Zeichenfolge "System.Data.SqlClient" zu.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="9b6e8-107">'ProviderManifestToken'-Schemaattribut</span><span class="sxs-lookup"><span data-stu-id="9b6e8-107">ProviderManifestToken Schema Attribute</span></span>  
 <span data-ttu-id="9b6e8-108">Das `ProviderManifestToken`-Element ist ein erforderliches Attribut des `Schema`-Elements.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-108">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="9b6e8-109">Dieses Token wird verwendet, um das Anbietermanifest für Offlineszenarien zu laden.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="9b6e8-110">Weitere Informationen zu `ProviderManifestToken` -Attribut angegeben wird, finden Sie unter [Schema-Element (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222).</span><span class="sxs-lookup"><span data-stu-id="9b6e8-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222).</span></span>  
  
 <span data-ttu-id="9b6e8-111">SqlClient kann als Datenanbieter für verschiedene Versionen von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-111">SqlClient can be used as a data provider for different versions of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9b6e8-112">Diese Versionen haben verschiedene Funktionen.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-112">These versions have different capabilities.</span></span> <span data-ttu-id="9b6e8-113">Beispielsweise unterstützt [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] die mit `varchar(max)` eingeführten Typen `nvarchar(max)` und [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)] nicht.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-113">For example, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] does not support `varchar(max)` and `nvarchar(max)` types that were introduced with [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="9b6e8-114">SqlClient erzeugt und akzeptiert die folgenden Anbietermanifesttoken für die verschiedenen Versionen von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="9b6e8-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="9b6e8-115">SQL Server 2000</span></span>|<span data-ttu-id="9b6e8-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="9b6e8-116">SQL Server 2005</span></span>|<span data-ttu-id="9b6e8-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="9b6e8-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="9b6e8-118">2000</span><span class="sxs-lookup"><span data-stu-id="9b6e8-118">2000</span></span>|<span data-ttu-id="9b6e8-119">2005</span><span class="sxs-lookup"><span data-stu-id="9b6e8-119">2005</span></span>|<span data-ttu-id="9b6e8-120">2008</span><span class="sxs-lookup"><span data-stu-id="9b6e8-120">2008</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9b6e8-121">Beginnend mit [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, die [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527) SQL Server 2000 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-121">Starting with [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, the [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="9b6e8-122">Anbieternamespacename</span><span class="sxs-lookup"><span data-stu-id="9b6e8-122">Provider Namespace Name</span></span>  
 <span data-ttu-id="9b6e8-123">Alle Anbieter müssen einen Namespace angeben.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-123">All providers must specify a namespace.</span></span> <span data-ttu-id="9b6e8-124">Anhand dieser Eigenschaft ermittelt Entity Framework, welches Präfix von diesem Anbieter für spezifische Konstrukte wie Typen und Funktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="9b6e8-125">Der Namespace für SqlClient-Anbietermanifeste lautet `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="9b6e8-126">Weitere Informationen zu Namespaces finden Sie unter [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9b6e8-126">For more information about namespaces, see [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="9b6e8-127">Typen</span><span class="sxs-lookup"><span data-stu-id="9b6e8-127">Types</span></span>  
 <span data-ttu-id="9b6e8-128">Der SqlClient-Anbieter für das Entity Framework stellt Zuordnungsinformationen zwischen Typen des konzeptionellen Modells und SQL Server-Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="9b6e8-129">Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Typen](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span><span class="sxs-lookup"><span data-stu-id="9b6e8-129">For more information, see [SqlClient for Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="9b6e8-130">Funktionen</span><span class="sxs-lookup"><span data-stu-id="9b6e8-130">Functions</span></span>  
 <span data-ttu-id="9b6e8-131">Der SqlClient-Anbieter für das Entity Framework definiert die Liste der vom Anbieter unterstützten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="9b6e8-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="9b6e8-132">Eine Liste der unterstützten Funktionen finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="9b6e8-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9b6e8-133">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9b6e8-133">In This Section</span></span>  
 [<span data-ttu-id="9b6e8-134">SqlClient für Entity Framework-Funktionen</span><span class="sxs-lookup"><span data-stu-id="9b6e8-134">SqlClient for Entity Framework Functions</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="9b6e8-135">SqlClient für Entity Framework-Typen</span><span class="sxs-lookup"><span data-stu-id="9b6e8-135">SqlClient for Entity FrameworkTypes</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="9b6e8-136">Bekannte Probleme in SqlClient für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="9b6e8-136">Known Issues in SqlClient for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="9b6e8-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b6e8-137">See Also</span></span>  
 [<span data-ttu-id="9b6e8-138">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="9b6e8-138">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [<span data-ttu-id="9b6e8-139">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="9b6e8-139">Language Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [<span data-ttu-id="9b6e8-140">Bekannte Probleme in SqlClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="9b6e8-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
