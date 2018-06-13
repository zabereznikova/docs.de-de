---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 8692dc761f00e0ddc8ec9fad5a5df66b7fda7916
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762298"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="a1c14-102">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="a1c14-102">DbProviderFactories</span></span>
<span data-ttu-id="a1c14-103">Der <xref:System.Data.Common>-Namespace stellt Klassen zum Erstellen von <xref:System.Data.Common.DbProviderFactory>-Instanzen für die Arbeit mit bestimmten Datenquellen bereit.</span><span class="sxs-lookup"><span data-stu-id="a1c14-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="a1c14-104">Wenn Sie eine <xref:System.Data.Common.DbProviderFactory>-Instanz erstellen und Informationen zum Anbieter an die Instanz übergeben, kann die `DbProviderFactory` auf der Grundlage der ihr bereitgestellten Informationen das korrekte, stark typisierte Verbindungsobjekt bestimmen, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1c14-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="a1c14-105">Ab .NET Framework Version 4 werden Datenanbieter wie <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient> nicht mehr in der machine.config-Datei aufgeführt, aber benutzerdefinierte Anbieter werden dort weiterhin aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a1c14-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1c14-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a1c14-106">In This Section</span></span>  
 [<span data-ttu-id="a1c14-107">Übersicht über das Factorymodell</span><span class="sxs-lookup"><span data-stu-id="a1c14-107">Factory Model Overview</span></span>](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 <span data-ttu-id="a1c14-108">Bietet eine Übersicht über das Factoryentwurfsmuster und die Programmierschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a1c14-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="a1c14-109">Abrufen einer DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="a1c14-109">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="a1c14-110">Zeigt, wie die installierten Datenanbieter aufgelistet und aus einer <xref:System.Data.Common.DbConnection> eine `DbProviderFactory` erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a1c14-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="a1c14-111">DbConnection, DbCommand und DbException</span><span class="sxs-lookup"><span data-stu-id="a1c14-111">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="a1c14-112">Zeigt, wie ein <xref:System.Data.Common.DbCommand> und ein <xref:System.Data.Common.DbDataReader> erstellt und Datenfehler mit <xref:System.Data.Common.DbException> behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="a1c14-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="a1c14-113">Ändern von Daten mit DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="a1c14-113">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="a1c14-114">Zeigt, wie mit einem <xref:System.Data.Common.DbCommandBuilder> und einem <xref:System.Data.Common.DbDataAdapter> Daten abgerufen und geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="a1c14-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c14-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1c14-115">See Also</span></span>  
 [<span data-ttu-id="a1c14-116">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1c14-116">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="a1c14-117">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a1c14-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
