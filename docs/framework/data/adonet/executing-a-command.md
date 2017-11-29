---
title: "Ausführen eines Befehls"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e09685c92652e1fcac2486031ecb49bf8399be59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="executing-a-command"></a><span data-ttu-id="75f02-102">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="75f02-102">Executing a Command</span></span>
<span data-ttu-id="75f02-103">Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter besitzt ein eigenes Befehlsobjekt, das von <xref:System.Data.Common.DbCommand> erbt.</span><span class="sxs-lookup"><span data-stu-id="75f02-103">Each .NET Framework data provider included with the .NET Framework has its own command object that inherits from <xref:System.Data.Common.DbCommand>.</span></span> <span data-ttu-id="75f02-104">Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbCommand>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlCommand>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcCommand>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleCommand>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="75f02-104">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span> <span data-ttu-id="75f02-105">Jedes dieser Objekte macht Methoden für das Ausführen von Befehlen auf der Grundlage des Befehlstyps und des gewünschten Rückgabewerts verfügbar. Die folgende Tabelle enthält eine Beschreibung der einzelnen Befehle.</span><span class="sxs-lookup"><span data-stu-id="75f02-105">Each of these objects exposes methods for executing commands based on the type of command and desired return value, as described in the following table.</span></span>  
  
|<span data-ttu-id="75f02-106">Befehl</span><span class="sxs-lookup"><span data-stu-id="75f02-106">Command</span></span>|<span data-ttu-id="75f02-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="75f02-107">Return Value</span></span>|  
|-------------|------------------|  
|`ExecuteReader`|<span data-ttu-id="75f02-108">Gibt ein `DataReader`-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="75f02-108">Returns a `DataReader` object.</span></span>|  
|`ExecuteScalar`|<span data-ttu-id="75f02-109">Gibt einen einzelnen Skalarwert zurück.</span><span class="sxs-lookup"><span data-stu-id="75f02-109">Returns a single scalar value.</span></span>|  
|`ExecuteNonQuery`|<span data-ttu-id="75f02-110">Führt einen Befehl aus, der keine Zeilen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="75f02-110">Executes a command that does not return any rows.</span></span>|  
|`ExecuteXMLReader`|<span data-ttu-id="75f02-111">Gibt einen <xref:System.Xml.XmlReader> zurück.</span><span class="sxs-lookup"><span data-stu-id="75f02-111">Returns an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="75f02-112">Nur für ein `SqlCommand`-Objekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75f02-112">Available for a `SqlCommand` object only.</span></span>|  
  
 <span data-ttu-id="75f02-113">Jedes stark typisierte Befehlsobjekt unterstützt auch eine <xref:System.Data.CommandType>-Enumeration, die angibt, wie eine Befehlszeichenfolge interpretiert wird. Nähere Informationen dazu finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="75f02-113">Each strongly typed command object also supports a <xref:System.Data.CommandType> enumeration that specifies how a command string is interpreted, as described in the following table.</span></span>  
  
|<span data-ttu-id="75f02-114">CommandType</span><span class="sxs-lookup"><span data-stu-id="75f02-114">CommandType</span></span>|<span data-ttu-id="75f02-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75f02-115">Description</span></span>|  
|-----------------|-----------------|  
|`Text`|<span data-ttu-id="75f02-116">SQL-Befehl, der die an der Datenquelle auszuführenden Anweisungen definiert</span><span class="sxs-lookup"><span data-stu-id="75f02-116">An SQL command defining the statements to be executed at the data source.</span></span>|  
|`StoredProcedure`|<span data-ttu-id="75f02-117">Der Name der gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="75f02-117">The name of the stored procedure.</span></span> <span data-ttu-id="75f02-118">Mit der `Parameters`-Befehlseigenschaft können Sie auf die Eingabe- und Ausgabeparameter sowie auf die Rückgabewerte zugreifen, und dies unabhängig davon, welche `Execute`-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="75f02-118">You can use the `Parameters` property of a command to access input and output parameters and return values, regardless of which `Execute` method is called.</span></span> <span data-ttu-id="75f02-119">Wenn Sie die `ExecuteReader`-Methode aufrufen, stehen die Rückgabewerte und die Ausgabeparameter jedoch erst zur Verfügung, wenn das `DataReader`-Objekt geschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="75f02-119">When using `ExecuteReader`, return values and output parameters will not be accessible until the `DataReader` is closed.</span></span>|  
|`TableDirect`|<span data-ttu-id="75f02-120">Name der Tabelle</span><span class="sxs-lookup"><span data-stu-id="75f02-120">The name of a table.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="75f02-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75f02-121">Example</span></span>  
 <span data-ttu-id="75f02-122">Das folgende Codebeispiel zeigt, wie durch Festlegen seiner Eigenschaften ein <xref:System.Data.SqlClient.SqlCommand>-Objekt zum Ausführen einer gespeicherten Prozedur erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="75f02-122">The following code example demonstrates how to create a <xref:System.Data.SqlClient.SqlCommand> object to execute a stored procedure by setting its properties.</span></span> <span data-ttu-id="75f02-123">Ein <xref:System.Data.SqlClient.SqlParameter>-Objekt wird zur Angabe des Eingabeparameters für die gespeicherte Prozedur verwendet.</span><span class="sxs-lookup"><span data-stu-id="75f02-123">A <xref:System.Data.SqlClient.SqlParameter> object is used to specify the input parameter to the stored procedure.</span></span> <span data-ttu-id="75f02-124">Der Befehl wird mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>-Methode ausgeführt, und die Ausgabe des <xref:System.Data.SqlClient.SqlDataReader> wird im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75f02-124">The command is executed using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method, and the output from the <xref:System.Data.SqlClient.SqlDataReader> is displayed in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a><span data-ttu-id="75f02-125">Befehle für die Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="75f02-125">Troubleshooting Commands</span></span>  
 <span data-ttu-id="75f02-126">Der .NET Framework-Datenanbieter für SQL Server enthält Leistungsindikatoren, mit denen Sie Probleme ermitteln können, die mit fehlgeschlagenen Befehlsausführungen im Zusammenhang stehen.</span><span class="sxs-lookup"><span data-stu-id="75f02-126">The .NET Framework Data Provider for SQL Server adds performance counters to enable you to detect intermittent problems related to failed command executions.</span></span> <span data-ttu-id="75f02-127">Weitere Informationen finden Sie unter [Leistungsindikatoren](../../../../docs/framework/data/adonet/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="75f02-127">For more information see [Performance Counters](../../../../docs/framework/data/adonet/performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f02-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75f02-128">See Also</span></span>  
 [<span data-ttu-id="75f02-129">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="75f02-129">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="75f02-130">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="75f02-130">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="75f02-131">Arbeiten mit DataReaders</span><span class="sxs-lookup"><span data-stu-id="75f02-131">Working with DataReaders</span></span>](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="75f02-132">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="75f02-132">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
