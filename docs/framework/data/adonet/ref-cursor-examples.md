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
# <a name="ref-cursor-examples"></a>REF CURSOR-Beispiele

Die REF CURSOR-Beispiele umfassen die folgenden drei Microsoft Visual Basic-Beispiele, mit denen die Verwendung von REF CURSOR veranschaulicht wird.  
  
|Beispiel|BESCHREIBUNG|  
|------------|-----------------|  
|[REF CURSOR-Parameter in "OracleDataReader"](ref-cursor-parameters-in-an-oracledatareader.md)|In diesem Beispiel wird eine gespeicherte PL/SQL-Prozedur ausgeführt, die einen REF CURSOR-Parameter zurückgibt. Der Wert wird als <xref:System.Data.OracleClient.OracleDataReader> gelesen.|  
|[Abrufen von Daten aus mehreren REF CURSORs mithilfe von "OracleDataReader"](retrieving-data-from-multiple-ref-cursors.md)|In diesem Beispiel wird eine gespeicherte PL/SQL-Prozedur ausgeführt, die zwei REF CURSOR-Parameter zurückgibt und die Werte mithilfe eines **OracleDataReader**liest.|  
|[Auffüllen eines "DataSets" mit einem oder mehreren REF CURSORs](filling-a-dataset-using-one-or-more-ref-cursors.md)|In diesem Beispiel wird eine gespeicherte PL/SQL-Prozedur ausgeführt, die zwei REF CURSOR-Parameter zurückgibt. <xref:System.Data.DataSet> wird mit den zurückgegebenen Zeilen gefüllt.|  
  
 Zur Verwendung dieser Beispiele müssen Sie möglicherweise die Oracle-Tabellen erstellen. Sie müssen außerdem ein PL/SQL-Paket sowie einen PL/SQL-Paketkörper erstellen.  
  
## <a name="creating-the-oracle-tables"></a>Erstellen der Oracle-Tabellen  

 In diesen Beispielen werden Tabellen verwendet, die im Oracle Scott/Tiger-Schema definiert sind. Das Oracle Scott/Tiger-Schema ist in den meisten Oracle-Installationen enthalten. Wenn dieses Schema nicht vorhanden ist, können Sie mithilfe der SQL-Befehlsdatei unter {OracleHome}\rdbms\admin\scott.sql die in diesen Beispielen verwendeten Tabellen und Indizes erstellen.  
  
## <a name="creating-the-oracle-package-and-package-body"></a>Erstellen des Oracle-Pakets und des Paketkörpers  

 Für diese Beispiele sind das folgende PL/SQL-Paket und der PL/SQL-Paketkörper auf Ihrem Server erforderlich. Erstellen Sie das folgende Oracle-Paket auf dem Oracle-Server.  
  
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
  
 Erstellen Sie den folgenden Oracle-Paketkörper auf dem Oracle-Server.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Oracle-REF CURSORs](oracle-ref-cursors.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
