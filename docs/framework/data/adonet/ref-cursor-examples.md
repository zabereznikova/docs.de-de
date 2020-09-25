---
title: REF CURSOR-Beispiele
ms.date: 03/30/2017
ms.assetid: c257da03-c6c9-4cf8-b591-b7740a962c40
ms.openlocfilehash: b45ef971ccb6b785988cc351d02be9e0844f6e11
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200536"
---
# <a name="ref-cursor-examples"></a><span data-ttu-id="3ac65-102">REF CURSOR-Beispiele</span><span class="sxs-lookup"><span data-stu-id="3ac65-102">REF CURSOR Examples</span></span>

<span data-ttu-id="3ac65-103">Die REF CURSOR-Beispiele umfassen die folgenden drei Microsoft Visual Basic-Beispiele, mit denen die Verwendung von REF CURSOR veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="3ac65-103">The REF CURSOR examples are comprised of the following three Microsoft Visual Basic examples that demonstrate using REF CURSORs.</span></span>  
  
|<span data-ttu-id="3ac65-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ac65-104">Sample</span></span>|<span data-ttu-id="3ac65-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3ac65-105">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ac65-106">REF CURSOR-Parameter in "OracleDataReader"</span><span class="sxs-lookup"><span data-stu-id="3ac65-106">REF CURSOR Parameters in an OracleDataReader</span></span>](ref-cursor-parameters-in-an-oracledatareader.md)|<span data-ttu-id="3ac65-107">In diesem Beispiel wird eine gespeicherte PL/SQL-Prozedur ausgeführt, die einen REF CURSOR-Parameter zurückgibt. Der Wert wird als <xref:System.Data.OracleClient.OracleDataReader> gelesen.</span><span class="sxs-lookup"><span data-stu-id="3ac65-107">This example executes a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>|  
|[<span data-ttu-id="3ac65-108">Abrufen von Daten aus mehreren REF CURSORs mithilfe von "OracleDataReader"</span><span class="sxs-lookup"><span data-stu-id="3ac65-108">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](retrieving-data-from-multiple-ref-cursors.md)|<span data-ttu-id="3ac65-109">In diesem Beispiel wird eine gespeicherte PL/SQL-Prozedur ausgeführt, die zwei REF CURSOR-Parameter zurückgibt und die Werte mithilfe eines **OracleDataReader**liest.</span><span class="sxs-lookup"><span data-stu-id="3ac65-109">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>|  
|[<span data-ttu-id="3ac65-110">Auffüllen eines "DataSets" mit einem oder mehreren REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="3ac65-110">Filling a DataSet Using One or More REF CURSORs</span></span>](filling-a-dataset-using-one-or-more-ref-cursors.md)|<span data-ttu-id="3ac65-111">In diesem Beispiel wird eine gespeicherte PL/SQL-Prozedur ausgeführt, die zwei REF CURSOR-Parameter zurückgibt. <xref:System.Data.DataSet> wird mit den zurückgegebenen Zeilen gefüllt.</span><span class="sxs-lookup"><span data-stu-id="3ac65-111">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>|  
  
 <span data-ttu-id="3ac65-112">Zur Verwendung dieser Beispiele müssen Sie möglicherweise die Oracle-Tabellen erstellen. Sie müssen außerdem ein PL/SQL-Paket sowie einen PL/SQL-Paketkörper erstellen.</span><span class="sxs-lookup"><span data-stu-id="3ac65-112">To use these examples, you may need to create the Oracle tables, and you must create a PL/SQL package and package body.</span></span>  
  
## <a name="creating-the-oracle-tables"></a><span data-ttu-id="3ac65-113">Erstellen der Oracle-Tabellen</span><span class="sxs-lookup"><span data-stu-id="3ac65-113">Creating the Oracle Tables</span></span>  

 <span data-ttu-id="3ac65-114">In diesen Beispielen werden Tabellen verwendet, die im Oracle Scott/Tiger-Schema definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3ac65-114">These examples use tables that are defined in the Oracle Scott/Tiger schema.</span></span> <span data-ttu-id="3ac65-115">Das Oracle Scott/Tiger-Schema ist in den meisten Oracle-Installationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ac65-115">The Oracle Scott/Tiger schema is included with most Oracle installations.</span></span> <span data-ttu-id="3ac65-116">Wenn dieses Schema nicht vorhanden ist, können Sie mithilfe der SQL-Befehlsdatei unter {OracleHome}\rdbms\admin\scott.sql die in diesen Beispielen verwendeten Tabellen und Indizes erstellen.</span><span class="sxs-lookup"><span data-stu-id="3ac65-116">If this schema does not exist, you can use the SQL commands file in {OracleHome}\rdbms\admin\scott.sql to create the tables and indexes used by these examples.</span></span>  
  
## <a name="creating-the-oracle-package-and-package-body"></a><span data-ttu-id="3ac65-117">Erstellen des Oracle-Pakets und des Paketkörpers</span><span class="sxs-lookup"><span data-stu-id="3ac65-117">Creating the Oracle Package and Package Body</span></span>  

 <span data-ttu-id="3ac65-118">Für diese Beispiele sind das folgende PL/SQL-Paket und der PL/SQL-Paketkörper auf Ihrem Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3ac65-118">These examples require the following PL/SQL package and package body on your server.</span></span> <span data-ttu-id="3ac65-119">Erstellen Sie das folgende Oracle-Paket auf dem Oracle-Server.</span><span class="sxs-lookup"><span data-stu-id="3ac65-119">Create the following Oracle package on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS
    TYPE T_CURSOR IS REF CURSOR;
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,
                               IO_CURSOR IN OUT T_CURSOR);
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,
                                DEPTCURSOR OUT T_CURSOR);  
END CURSPKG;  
/
```  
  
 <span data-ttu-id="3ac65-120">Erstellen Sie den folgenden Oracle-Paketkörper auf dem Oracle-Server.</span><span class="sxs-lookup"><span data-stu-id="3ac65-120">Create the following Oracle package body on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE BODY CURSPKG AS  
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,  
                               IO_CURSOR IN OUT T_CURSOR)  
    IS
        V_CURSOR T_CURSOR;
    BEGIN
        IF N_EMPNO <> 0
        THEN  
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO
                  AND EMP.EMPNO = N_EMPNO;  
  
        ELSE
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO;  
  
        END IF;  
        IO_CURSOR := V_CURSOR;
    END OPEN_ONE_CURSOR;
  
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,  
                                DEPTCURSOR OUT T_CURSOR)  
    IS
        V_CURSOR1 T_CURSOR;
        V_CURSOR2 T_CURSOR;
    BEGIN
        OPEN V_CURSOR1 FOR SELECT * FROM EMP;  
        OPEN V_CURSOR2 FOR SELECT * FROM DEPT;  
        EMPCURSOR  := V_CURSOR1;
        DEPTCURSOR := V_CURSOR2;
    END OPEN_TWO_CURSORS;
END CURSPKG;  
/  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ac65-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ac65-121">See also</span></span>

- [<span data-ttu-id="3ac65-122">Oracle-REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="3ac65-122">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)
- [<span data-ttu-id="3ac65-123">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3ac65-123">ADO.NET Overview</span></span>](ado-net-overview.md)
