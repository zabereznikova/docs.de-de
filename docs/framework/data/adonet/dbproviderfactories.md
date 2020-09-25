---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: b5f2dbb687348afac98247cb21bae831dea26bfe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183311"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="6ef46-102">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="6ef46-102">DbProviderFactories</span></span>

<span data-ttu-id="6ef46-103">Der <xref:System.Data.Common>-Namespace stellt Klassen zum Erstellen von <xref:System.Data.Common.DbProviderFactory>-Instanzen für die Arbeit mit bestimmten Datenquellen bereit.</span><span class="sxs-lookup"><span data-stu-id="6ef46-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="6ef46-104">Wenn Sie eine <xref:System.Data.Common.DbProviderFactory>-Instanz erstellen und Informationen zum Anbieter an die Instanz übergeben, kann die `DbProviderFactory` auf der Grundlage der ihr bereitgestellten Informationen das korrekte, stark typisierte Verbindungsobjekt bestimmen, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="6ef46-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="6ef46-105">Ab .NET Framework Version 4 werden Datenanbieter wie <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient> nicht mehr in der machine.config-Datei aufgeführt, aber benutzerdefinierte Anbieter werden dort weiterhin aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6ef46-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ef46-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6ef46-106">In This Section</span></span>  

 [<span data-ttu-id="6ef46-107">Übersicht über das Factorymodell</span><span class="sxs-lookup"><span data-stu-id="6ef46-107">Factory Model Overview</span></span>](factory-model-overview.md)  
 <span data-ttu-id="6ef46-108">Bietet eine Übersicht über das Factoryentwurfsmuster und die Programmierschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6ef46-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="6ef46-109">Abrufen einer "DbProviderFactory"</span><span class="sxs-lookup"><span data-stu-id="6ef46-109">Obtaining a DbProviderFactory</span></span>](obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="6ef46-110">Zeigt, wie die installierten Datenanbieter aufgelistet und aus einer <xref:System.Data.Common.DbConnection> eine `DbProviderFactory` erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6ef46-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="6ef46-111">"DbConnection", "DbCommand" und "DbException"</span><span class="sxs-lookup"><span data-stu-id="6ef46-111">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="6ef46-112">Zeigt, wie ein <xref:System.Data.Common.DbCommand> und ein <xref:System.Data.Common.DbDataReader> erstellt und Datenfehler mit <xref:System.Data.Common.DbException> behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="6ef46-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="6ef46-113">Ändern von Daten mit "DbDataAdapter"</span><span class="sxs-lookup"><span data-stu-id="6ef46-113">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="6ef46-114">Zeigt, wie mit einem <xref:System.Data.Common.DbCommandBuilder> und einem <xref:System.Data.Common.DbDataAdapter> Daten abgerufen und geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="6ef46-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef46-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ef46-115">See also</span></span>

- [<span data-ttu-id="6ef46-116">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6ef46-116">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="6ef46-117">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6ef46-117">ADO.NET Overview</span></span>](ado-net-overview.md)
