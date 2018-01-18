---
title: Oracle-REF CURSORs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f01ace7bc7dfe1191dac8990210032b60e16f255
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="c29cd-102">Oracle-REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="c29cd-102">Oracle REF CURSORs</span></span>
<span data-ttu-id="c29cd-103">Die .NET Framework-Datenanbieter für Oracle unterstützt Oracle **REF CURSOR** -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c29cd-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="c29cd-104">Wenn Sie beim Arbeiten mit Oracle-REF CUSORS diesen Datenanbieter verwenden, müssen Sie das jeweilige Verhalten berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="c29cd-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c29cd-105">Das jeweilige Verhalten weicht von dem des Microsoft OLE DB-Anbieters für Oracle (MSDAORA) ab.</span><span class="sxs-lookup"><span data-stu-id="c29cd-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
-   <span data-ttu-id="c29cd-106">Aus Gründen der Leistung der Datenanbieter für Oracle Bindung erfolgt nicht automatisch **REF CURSOR** -Datentypen, wie MSDAORA, es sei denn, Sie explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="c29cd-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
-   <span data-ttu-id="c29cd-107">Der Datenanbieter unterstützt keine ODBC-Escapesequenzen, auch nicht das {resultset}-Escapezeichen für die Angabe von REF CURSOR-Parametern.</span><span class="sxs-lookup"><span data-stu-id="c29cd-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
-   <span data-ttu-id="c29cd-108">Um eine gespeicherte Prozedur auszuführen, die REF CURSORs zurückgibt, müssen Sie definieren die Parameter in der <xref:System.Data.OracleClient.OracleParameterCollection> mit einer <xref:System.Data.OracleClient.OracleType> von **Cursor** und ein <xref:System.Data.OracleClient.OracleParameter.Direction%2A> von **Ausgabe**.</span><span class="sxs-lookup"><span data-stu-id="c29cd-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="c29cd-109">Mit diesem Datenanbieter können REF CURSORs nur als Ausgabeparameter gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="c29cd-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="c29cd-110">Das Binden von REF CURSORs als Eingabeparameter wird von diesem Datenanbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c29cd-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
-   <span data-ttu-id="c29cd-111">Das Abrufen eines <xref:System.Data.OracleClient.OracleDataReader> aus dem Parameterwert wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c29cd-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="c29cd-112">Nach dem Ausführen des Befehls weisen die Werte den Typ <xref:System.DBNull> auf.</span><span class="sxs-lookup"><span data-stu-id="c29cd-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
-   <span data-ttu-id="c29cd-113">Die einzige **CommandBehavior** -Enumerationswert ab, der mit REF CURSORs verwendet (z. B. beim Aufrufen von <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) ist **CloseConnection**; alle anderen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c29cd-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
-   <span data-ttu-id="c29cd-114">Die Reihenfolge der REF CURSORs in die **OracleDataReader** abhängt, die Reihenfolge der Parameter in der **OracleParameterCollection**.</span><span class="sxs-lookup"><span data-stu-id="c29cd-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="c29cd-115">Die <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A>-Eigenschaft wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c29cd-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
-   <span data-ttu-id="c29cd-116">Der PL/SQL **Tabelle** -Datentyp wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c29cd-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="c29cd-117">REF CURSORs sind im Vergleich effizienter.</span><span class="sxs-lookup"><span data-stu-id="c29cd-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="c29cd-118">Falls Sie benötigen eine **Tabelle** -Datentyp, verwenden die OLE DB-.NET-Datenanbieter mit MSDAORA.</span><span class="sxs-lookup"><span data-stu-id="c29cd-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c29cd-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c29cd-119">In This Section</span></span>  
 [<span data-ttu-id="c29cd-120">REF CURSOR-Beispiele</span><span class="sxs-lookup"><span data-stu-id="c29cd-120">REF CURSOR Examples</span></span>](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 <span data-ttu-id="c29cd-121">Enthält drei Beispiele, in denen die Verwendung von REF CURSORs veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="c29cd-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="c29cd-122">REF CURSOR-Parameter in OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="c29cd-122">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="c29cd-123">Veranschaulicht, wie eine gespeicherte PL/SQL-Prozedur ausgeführt, die einen REF CURSOR-Parameter zurückgibt und liest den Wert als ein **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="c29cd-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="c29cd-124">Abrufen von Daten aus mehreren REF CURSORs mithilfe von OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="c29cd-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="c29cd-125">Veranschaulicht, wie eine gespeicherte PL/SQL-Prozedur ausgeführt, die zwei REF CURSOR-Parameter zurückgibt und liest die Werte mithilfe einer **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="c29cd-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="c29cd-126">Auffüllen eines DataSets mit einem oder mehreren REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="c29cd-126">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="c29cd-127">Veranschaulicht das Ausführen einer gespeicherten PL/SQL-Prozedur, die zwei REF CURSOR-Parameter zurückgibt. Das <xref:System.Data.DataSet> wird mit den zurückgegebenen Zeilen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="c29cd-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29cd-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c29cd-128">See Also</span></span>  
 [<span data-ttu-id="c29cd-129">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c29cd-129">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="c29cd-130">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c29cd-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
