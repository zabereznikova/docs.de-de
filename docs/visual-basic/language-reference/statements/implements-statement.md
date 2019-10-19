---
title: Implementierende Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 865e99aa0e27591d10fde1465047a2e6bf183bbf
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581793"
---
# <a name="implements-statement"></a>Implements-Anweisung
Gibt eine oder mehrere Schnittstellen oder Schnittstellenmember an, die in der Klassen-oder Struktur Definition implementiert werden müssen, in der Sie angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Teile  
 `interfacename`  
 Erforderlich. Eine Schnittstelle, deren Eigenschaften, Prozeduren und Ereignisse von entsprechenden Membern in der Klasse oder Struktur implementiert werden.  
  
 `interfacemember`  
 Erforderlich. Der Member einer Schnittstelle, die implementiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Eine Schnittstelle ist eine Auflistung von Prototypen, die die Elemente (Eigenschaften, Prozeduren und Ereignisse) darstellen, die die Schnittstelle kapselt. Schnittstellen enthalten nur die Deklarationen für Member. Klassen und Strukturen implementieren diese Member. Weitere Informationen finden Sie unter [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Die `Implements`-Anweisung muss direkt auf die `Class`-oder `Structure`-Anweisung folgen.  
  
 Wenn Sie eine Schnittstelle implementieren, müssen alle in der Schnittstelle deklarierten Member implementiert werden. Das Weglassen eines Members wird als Syntax Fehler betrachtet. Um einen einzelnen Member zu implementieren, geben Sie das [implementierte](../../../visual-basic/language-reference/statements/implements-clause.md) Schlüsselwort (das von der `Implements` Anweisung getrennt ist) an, wenn Sie den Member in der Klasse oder Struktur deklarieren. Weitere Informationen finden Sie unter [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Klassen können [private](../../../visual-basic/language-reference/modifiers/private.md) Implementierungen von Eigenschaften und Prozeduren verwenden, aber auf diese Member kann nur zugegriffen werden, indem eine Instanz der implementierenden Klasse in eine Variable umgewandelt wird, die als der Typ der Schnittstelle deklariert ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die `Implements`-Anweisung verwendet wird, um Member einer Schnittstelle zu implementieren. Er definiert eine Schnittstelle mit dem Namen `ICustomerInfo` mit einem Ereignis, einer Eigenschaft und einer Prozedur. Die-Klasse `customerInfo` die alle in der-Schnittstelle definierten Member implementiert.  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 Beachten Sie, dass die-Klasse `customerInfo` die `Implements`-Anweisung in einer separaten Quell Code Zeile verwendet, um anzugeben, dass die-Klasse alle Member der `ICustomerInfo`-Schnittstelle implementiert. Dann verwendet jedes Element in der-Klasse das `Implements`-Schlüsselwort als Teil seiner Member-Deklaration, um anzugeben, dass dieses Schnittstellenmember implementiert.  
  
## <a name="example"></a>Beispiel  
 Die folgenden zwei Prozeduren zeigen, wie Sie die im vorherigen Beispiel implementierte-Schnittstelle verwenden können. Um die Implementierung zu testen, fügen Sie dem Projekt diese Prozeduren hinzu, und nennen Sie die `testImplements` Prozedur.  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Siehe auch

- [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
