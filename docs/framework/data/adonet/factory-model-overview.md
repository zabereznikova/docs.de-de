---
title: "Übersicht über das Factorymodell"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0194cd6789ae6ddebeeee65abf1a4fca4a2bc0d6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="factory-model-overview"></a><span data-ttu-id="c1f88-102">Übersicht über das Factorymodell</span><span class="sxs-lookup"><span data-stu-id="c1f88-102">Factory Model Overview</span></span>
<span data-ttu-id="c1f88-103">In ADO.NET 2.0 wurden im <xref:System.Data.Common>-Namespace neue Basisklassen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c1f88-103">ADO.NET 2.0 introduced new base classes in the <xref:System.Data.Common> namespace.</span></span> <span data-ttu-id="c1f88-104">Die Basisklassen sind abstrakt, können also nicht direkt instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="c1f88-104">The base classes are abstract, which means that they can't be directly instantiated.</span></span> <span data-ttu-id="c1f88-105">Zu ihnen gehören die Basisklassen <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand> und <xref:System.Data.Common.DbDataAdapter>. Sie werden von den .NET Framework-Datenanbietern, z. B. <xref:System.Data.SqlClient> und <xref:System.Data.OleDb>, gemeinsam genutzt.</span><span class="sxs-lookup"><span data-stu-id="c1f88-105">They include <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>, and <xref:System.Data.Common.DbDataAdapter> and are shared by the .NET Framework data providers, such as <xref:System.Data.SqlClient> and <xref:System.Data.OleDb>.</span></span> <span data-ttu-id="c1f88-106">Die neuen Basisklassen vereinfachen das Hinzufügen neuer Funktionen zu den .NET Framework-Datenanbietern, ohne dass dazu neue Schnittstellen erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c1f88-106">The addition of base classes simplifies adding functionality to the .NET Framework data providers without having to create new interfaces.</span></span>  
  
 <span data-ttu-id="c1f88-107">Außerdem wurden abstrakte Basisklassen in ADO.NET 2.0 eingeführt, mit denen Entwickler in der Lage sind, generischen Datenzugriffscode zu schreiben, der datenanbieterunabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="c1f88-107">ADO.NET 2.0 also introduced abstract base classes, which enable a developer to write generic data access code that does not depend on a specific data provider.</span></span>  
  
## <a name="the-factory-design-pattern"></a><span data-ttu-id="c1f88-108">Das Factoryentwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="c1f88-108">The Factory Design Pattern</span></span>  
 <span data-ttu-id="c1f88-109">Das Programmiermodell zum Schreiben anbieterunabhängigen Codes basiert auf der Verwendung des Factoryentwurfsmusters, das für den Zugriff auf Datenbanken mehrerer Anbieter eine einzige API vewendet.</span><span class="sxs-lookup"><span data-stu-id="c1f88-109">The programming model for writing provider-independent code is based on the use of the "factory" design pattern, which uses a single API to access databases across multiple providers.</span></span> <span data-ttu-id="c1f88-110">Dieses Muster ist geeignet benannt, da es die Verwendung eines spezialisierten Objekts nur zum Erstellen anderer Objekte bedingt, wie in einer realen Produktionsumgebung.</span><span class="sxs-lookup"><span data-stu-id="c1f88-110">This pattern is aptly named, as it calls for the use of a specialized object solely to create other objects, much like a real-world factory.</span></span> <span data-ttu-id="c1f88-111">Eine ausführlichere Beschreibung des Factoryentwurfsmusters finden Sie unter "[Schreiben von generischem Datenzugriffscode in ASP.NET 2.0 und ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" und "Generische Codierung mit den ADO.NET 2.0 Base Klassen und-Factorys" [http:// MSDN.Microsoft.com/library/default.asp?url=/library/dnvs05/HTML/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="c1f88-111">For a more detailed description of the factory design pattern, see "[Writing Generic Data Access Code in ASP.NET 2.0 and ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" and "Generic Coding with the ADO.NET 2.0 Base Classes and Factories" [http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) on MSDN.</span></span>  
  
 <span data-ttu-id="c1f88-112">Ab ADO.NET 2.0 stellt die <xref:System.Data.Common.DbProviderFactories>-Klasse zum Erstellen einer `static`-Instanz `Shared`-Methoden (in Visual Basic <xref:System.Data.Common.DbProviderFactory>-Methoden) bereit.</span><span class="sxs-lookup"><span data-stu-id="c1f88-112">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbProviderFactories> class provides `static` (or `Shared` in Visual Basic) methods for creating a <xref:System.Data.Common.DbProviderFactory> instance.</span></span> <span data-ttu-id="c1f88-113">Die Instanz gibt dann anhand der Anbieterinformationen und der zur Laufzeit bereitgestellten Verbindungszeichenfolge ein korrektes, stark typisiertes Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="c1f88-113">The instance then returns a correct strongly typed object based on provider information and the connection string supplied at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f88-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1f88-114">See Also</span></span>  
 [<span data-ttu-id="c1f88-115">Abrufen einer DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="c1f88-115">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [<span data-ttu-id="c1f88-116">DbConnection, DbCommand und DbException</span><span class="sxs-lookup"><span data-stu-id="c1f88-116">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="c1f88-117">Ändern von Daten mit DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="c1f88-117">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [<span data-ttu-id="c1f88-118">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c1f88-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
