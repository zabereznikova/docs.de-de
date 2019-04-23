---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 2376cf39228cb5e8208112333ba06bb80070de84
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208813"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="bb650-102">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="bb650-102">DbProviderFactories</span></span>
<span data-ttu-id="bb650-103">Der <xref:System.Data.Common>-Namespace stellt Klassen zum Erstellen von <xref:System.Data.Common.DbProviderFactory>-Instanzen für die Arbeit mit bestimmten Datenquellen bereit.</span><span class="sxs-lookup"><span data-stu-id="bb650-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="bb650-104">Wenn Sie eine <xref:System.Data.Common.DbProviderFactory>-Instanz erstellen und Informationen zum Anbieter an die Instanz übergeben, kann die `DbProviderFactory` auf der Grundlage der ihr bereitgestellten Informationen das korrekte, stark typisierte Verbindungsobjekt bestimmen, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb650-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="bb650-105">Ab .NET Framework Version 4 werden Datenanbieter wie <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient> nicht mehr in der machine.config-Datei aufgeführt, aber benutzerdefinierte Anbieter werden dort weiterhin aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb650-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb650-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bb650-106">In This Section</span></span>  
 [<span data-ttu-id="bb650-107">Übersicht über das Factorymodell</span><span class="sxs-lookup"><span data-stu-id="bb650-107">Factory Model Overview</span></span>](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 <span data-ttu-id="bb650-108">Bietet eine Übersicht über das Factoryentwurfsmuster und die Programmierschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bb650-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="bb650-109">Abrufen einer DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="bb650-109">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="bb650-110">Zeigt, wie die installierten Datenanbieter aufgelistet und aus einer <xref:System.Data.Common.DbConnection> eine `DbProviderFactory` erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb650-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="bb650-111">DbConnection, DbCommand und DbException</span><span class="sxs-lookup"><span data-stu-id="bb650-111">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="bb650-112">Zeigt, wie ein <xref:System.Data.Common.DbCommand> und ein <xref:System.Data.Common.DbDataReader> erstellt und Datenfehler mit <xref:System.Data.Common.DbException> behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="bb650-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="bb650-113">Ändern von Daten mit DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="bb650-113">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="bb650-114">Zeigt, wie mit einem <xref:System.Data.Common.DbCommandBuilder> und einem <xref:System.Data.Common.DbDataAdapter> Daten abgerufen und geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="bb650-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb650-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb650-115">See also</span></span>

- [<span data-ttu-id="bb650-116">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bb650-116">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="bb650-117">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="bb650-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
