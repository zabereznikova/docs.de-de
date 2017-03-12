---
title: "GROUP BY-Klausel (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryGroupByInto"
  - "vb.QueryGroupBy"
  - "vb.QueryGroupRef"
  - "vb.QueryGroupInto"
  - "vb.QueryGroup"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Abfragen [Visual Basic], Group By"
  - "Group By-Anweisung"
  - "Group By-Klausel"
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# GROUP BY-Klausel (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gruppiert die Elemente eines Abfrageergebnisses. Kann auch verwendet werden, um Aggregatfunktionen auf die einzelnen Gruppen anzuwenden. Der Gruppierungsvorgang basiert auf einem oder mehreren Schlüssel(n).  
  
## <a name="syntax"></a>Syntax  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a>Teile  
  
-   `listField1`, `listField2`  
  
     Dies ist optional. Mindestens eins der Felder der einen oder mehreren Abfragevariablen, die explizit die in das gruppierte Ergebnis aufzunehmenden Felder bezeichnen. Wenn keine Felder angegeben werden, sind alle Felder der Abfragevariablen im gruppierten Ergebnis enthalten.  
  
-   `keyExp1`  
  
     Erforderlich. Ein Ausdruck, der den Schlüssel zum Bestimmen der Elementgruppen bezeichnet. Zum Angeben eines zusammengesetzten Schlüssels können mehrere Schlüssel angegeben werden.  
  
-   `keyExp2`  
  
     Dies ist optional. Mindestens ein zusätzlicher Schlüssel, die mit `keyExp1` kombiniert werden, um einen zusammengesetzten Schlüssel zu erstellen.  
  
-   `aggregateList`  
  
     Erforderlich. Mindestens ein Ausdruck, der angibt, wie die Gruppen aggregiert werden. Zum Angeben eines Membernamens für die gruppierten Ergebnisse können Sie das Schlüsselwort `Group` in einer der folgenden Formen verwenden:  
  
    ```  
    Into Group  
    ```  
  
     - oder -  
  
    ```  
    Into <alias> = Group  
    ```  
  
     Sie können auch Aggregatfunktionen einschließen, die auf die Gruppe angewendet werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Group By` -Klausel verwenden, um die Ergebnisse einer Abfrage in Gruppen aufzuteilen. Die Gruppierung erfolgt auf der Basis eines Schlüssels oder eines zusammengesetzten Schlüssels, der aus mehreren Schlüsseln besteht. Elemente, die übereinstimmenden Schlüsselwerten zugeordnet sind werden in die gleiche Gruppe aufgenommen.  
  
 Sie verwenden den `aggregateList` -Parameter der `Into` -Klausel und das `Group` -Schlüsselwort, um den Membernamen zu bezeichnen, der zum Verweisen auf die Gruppe verwendet wird. Ferner kann die `Into` -Klausel Aggregatfunktionen beinhalten, um Werte für die gruppierten Elemente zu berechnen. Eine Liste der standardmäßigen Aggregatfunktionen finden Sie unter [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Liste von Kunden basierend auf ihrem Standort (Land) gruppiert und die Anzahl der Kunden in jeder Gruppe angegeben. Die Ergebnisse werden nach Ländernamen geordnet. Die gruppierten Ergebnisse sind nach Städtenamen geordnet.  
  
 [!code-vb[VbSimpleQuerySamples#11](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)   
 [SELECT-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)   
 [FROM-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md)