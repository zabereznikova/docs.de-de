---
title: GROUP BY-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: 71e0ffc7f03a27a878aeb48eda9fbc58e5faae82
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945326"
---
# <a name="group-by-clause-visual-basic"></a>GROUP BY-Klausel (Visual Basic)
Gruppiert die Elemente eines Abfrageergebnisses. Kann auch verwendet werden, um Aggregatfunktionen auf die einzelnen Gruppen anzuwenden. Der Gruppierungsvorgang basiert auf einem oder mehreren Schlüssel(n).  
  
## <a name="syntax"></a>Syntax  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a>Teile  
  
- `listField1`, `listField2`  
  
     Dies ist optional. Mindestens eins der Felder der einen oder mehreren Abfragevariablen, die explizit die in das gruppierte Ergebnis aufzunehmenden Felder bezeichnen. Wenn keine Felder angegeben werden, sind alle Felder der Abfragevariablen im gruppierten Ergebnis enthalten.  
  
- `keyExp1`  
  
     Erforderlich. Ein Ausdruck, der den Schlüssel zum Bestimmen der Elementgruppen bezeichnet. Zum Angeben eines zusammengesetzten Schlüssels können mehrere Schlüssel angegeben werden.  
  
- `keyExp2`  
  
     Dies ist optional. Mindestens ein zusätzlicher Schlüssel, die mit `keyExp1` kombiniert werden, um einen zusammengesetzten Schlüssel zu erstellen.  
  
- `aggregateList`  
  
     Erforderlich. Mindestens ein Ausdruck, der angibt, wie die Gruppen aggregiert werden. Zum Angeben eines Membernamens für die gruppierten Ergebnisse können Sie das Schlüsselwort `Group` in einer der folgenden Formen verwenden:  
  
    ```  
    Into Group  
    ```  
  
     - oder -   
  
    ```  
    Into <alias> = Group  
    ```  
  
     Sie können auch Aggregatfunktionen einschließen, die auf die Gruppe angewendet werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Group By` -Klausel verwenden, um die Ergebnisse einer Abfrage in Gruppen aufzuteilen. Die Gruppierung erfolgt auf der Basis eines Schlüssels oder eines zusammengesetzten Schlüssels, der aus mehreren Schlüsseln besteht. Elemente, die übereinstimmenden Schlüsselwerten zugeordnet sind werden in die gleiche Gruppe aufgenommen.  
  
 Sie verwenden den `aggregateList` -Parameter der `Into` -Klausel und das `Group` -Schlüsselwort, um den Membernamen zu bezeichnen, der zum Verweisen auf die Gruppe verwendet wird. Ferner kann die `Into` -Klausel Aggregatfunktionen beinhalten, um Werte für die gruppierten Elemente zu berechnen. Eine Liste der standardmäßigen Aggregatfunktionen finden Sie unter [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Liste von Kunden basierend auf ihrem Standort (Land) gruppiert und die Anzahl der Kunden in jeder Gruppe angegeben. Die Ergebnisse werden nach Ländernamen geordnet. Die gruppierten Ergebnisse sind nach Städtenamen geordnet.  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md)
