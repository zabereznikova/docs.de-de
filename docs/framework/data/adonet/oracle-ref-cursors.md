---
title: Oracle-REF CURSORs
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: cbf330ba381a825c2d16038c01d7bdc52bc8f482
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180880"
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="fcb45-102">Oracle-REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="fcb45-102">Oracle REF CURSORs</span></span>

<span data-ttu-id="fcb45-103">Der .NET Framework Datenanbieter für Oracle unterstützt den Oracle **ref Cursor** -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="fcb45-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="fcb45-104">Wenn Sie beim Arbeiten mit Oracle-REF CUSORS diesen Datenanbieter verwenden, müssen Sie das jeweilige Verhalten berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="fcb45-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fcb45-105">Das jeweilige Verhalten weicht von dem des Microsoft OLE DB-Anbieters für Oracle (MSDAORA) ab.</span><span class="sxs-lookup"><span data-stu-id="fcb45-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
- <span data-ttu-id="fcb45-106">Aus Leistungsgründen bindet die Datenanbieter für Oracle die **ref Cursor** -Datentypen nicht automatisch wie MSDAORA, es sei denn, Sie geben Sie explizit an.</span><span class="sxs-lookup"><span data-stu-id="fcb45-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
- <span data-ttu-id="fcb45-107">Der Datenanbieter unterstützt keine ODBC-Escapesequenzen, auch nicht das {resultset}-Escapezeichen für die Angabe von REF CURSOR-Parametern.</span><span class="sxs-lookup"><span data-stu-id="fcb45-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="fcb45-108">Zum Ausführen einer gespeicherten Prozedur, die Ref Cursors zurückgibt, müssen Sie die Parameter in <xref:System.Data.OracleClient.OracleParameterCollection> mit einem <xref:System.Data.OracleClient.OracleType> - **Cursor** und einem-Wert <xref:System.Data.OracleClient.OracleParameter.Direction%2A> von **Output**definieren.</span><span class="sxs-lookup"><span data-stu-id="fcb45-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="fcb45-109">Mit diesem Datenanbieter können REF CURSORs nur als Ausgabeparameter gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="fcb45-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="fcb45-110">Das Binden von REF CURSORs als Eingabeparameter wird von diesem Datenanbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fcb45-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
- <span data-ttu-id="fcb45-111">Das Abrufen eines <xref:System.Data.OracleClient.OracleDataReader> aus dem Parameterwert wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fcb45-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="fcb45-112">Nach dem Ausführen des Befehls weisen die Werte den Typ <xref:System.DBNull> auf.</span><span class="sxs-lookup"><span data-stu-id="fcb45-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
- <span data-ttu-id="fcb45-113">Der einzige **CommandBehavior** -Enumerationswert, der mit Ref Cursors funktioniert (z. b. beim Aufrufen von <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> ), ist **closeconnetction**; alle anderen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="fcb45-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
- <span data-ttu-id="fcb45-114">Die Reihenfolge der Ref Cursors in **OracleDataReader** hängt von der Reihenfolge der Parameter in der **OracleParameterCollection**ab.</span><span class="sxs-lookup"><span data-stu-id="fcb45-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="fcb45-115">Die <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A>-Eigenschaft wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="fcb45-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
- <span data-ttu-id="fcb45-116">Der Datentyp der PL/SQL- **Tabelle** wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fcb45-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="fcb45-117">REF CURSORs sind im Vergleich effizienter.</span><span class="sxs-lookup"><span data-stu-id="fcb45-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="fcb45-118">Wenn Sie einen **Tabellen** Datentyp verwenden müssen, verwenden Sie die OLE DB .NET-Datenanbieter mit MSDAORA.</span><span class="sxs-lookup"><span data-stu-id="fcb45-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fcb45-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fcb45-119">In This Section</span></span>  

 [<span data-ttu-id="fcb45-120">REF CURSOR-Beispiele</span><span class="sxs-lookup"><span data-stu-id="fcb45-120">REF CURSOR Examples</span></span>](ref-cursor-examples.md)  
 <span data-ttu-id="fcb45-121">Enthält drei Beispiele, in denen die Verwendung von REF CURSORs veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="fcb45-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="fcb45-122">REF CURSOR-Parameter in "OracleDataReader"</span><span class="sxs-lookup"><span data-stu-id="fcb45-122">REF CURSOR Parameters in an OracleDataReader</span></span>](ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="fcb45-123">Veranschaulicht, wie eine gespeicherte PL/SQL-Prozedur ausgeführt wird, die einen REF CURSOR-Parameter zurückgibt und den Wert als **OracleDataReader**liest.</span><span class="sxs-lookup"><span data-stu-id="fcb45-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="fcb45-124">Abrufen von Daten aus mehreren REF CURSORs mithilfe von "OracleDataReader"</span><span class="sxs-lookup"><span data-stu-id="fcb45-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="fcb45-125">Veranschaulicht, wie eine gespeicherte PL/SQL-Prozedur ausgeführt wird, die zwei REF CURSOR-Parameter zurückgibt und die Werte mithilfe eines **OracleDataReader**liest.</span><span class="sxs-lookup"><span data-stu-id="fcb45-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="fcb45-126">Auffüllen eines "DataSets" mit einem oder mehreren REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="fcb45-126">Filling a DataSet Using One or More REF CURSORs</span></span>](filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="fcb45-127">Veranschaulicht das Ausführen einer gespeicherten PL/SQL-Prozedur, die zwei REF CURSOR-Parameter zurückgibt. Das <xref:System.Data.DataSet> wird mit den zurückgegebenen Zeilen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fcb45-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb45-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fcb45-128">See also</span></span>

- [<span data-ttu-id="fcb45-129">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fcb45-129">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="fcb45-130">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fcb45-130">ADO.NET Overview</span></span>](ado-net-overview.md)
