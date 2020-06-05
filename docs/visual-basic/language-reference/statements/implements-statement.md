---
title: Implements-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 7fb43934d8c200ff29b1caf63cec830b2c6633ce
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404549"
---
# <a name="implements-statement"></a>Implements-Anweisung
Gibt eine oder mehrere Schnittstellen oder Schnittstellenmember an, die in der Klassen-oder Struktur Definition implementiert werden müssen, in der Sie angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Bestandteile  
 `interfacename`  
 Erforderlich. Eine Schnittstelle, deren Eigenschaften, Prozeduren und Ereignisse von entsprechenden Membern in der Klasse oder Struktur implementiert werden.  
  
 `interfacemember`  
 Erforderlich. Der Member einer Schnittstelle, die implementiert wird.  
  
## <a name="remarks"></a>Bemerkungen  
 Eine Schnittstelle ist eine Auflistung von Prototypen, die die Elemente (Eigenschaften, Prozeduren und Ereignisse) darstellen, die die Schnittstelle kapselt. Schnittstellen enthalten nur die Deklarationen für Member. Klassen und Strukturen implementieren diese Member. Weitere Informationen finden Sie unter [Schnittstellen](../../programming-guide/language-features/interfaces/index.md).  
  
 Die- `Implements` Anweisung muss direkt auf die- `Class` oder-Anweisung folgen `Structure` .  
  
 Wenn Sie eine Schnittstelle implementieren, müssen alle in der Schnittstelle deklarierten Member implementiert werden. Das Weglassen eines Members wird als Syntax Fehler betrachtet. Zum Implementieren eines einzelnen Members geben Sie das [implementierte](implements-clause.md) Schlüsselwort (das von der-Anweisung getrennt ist) an, `Implements` Wenn Sie den Member in der Klasse oder Struktur deklarieren. Weitere Informationen finden Sie unter [Schnittstellen](../../programming-guide/language-features/interfaces/index.md).  
  
 Klassen können [private](../modifiers/private.md) Implementierungen von Eigenschaften und Prozeduren verwenden, aber auf diese Member kann nur zugegriffen werden, indem eine Instanz der implementierenden Klasse in eine Variable umgewandelt wird, die als der Typ der Schnittstelle deklariert ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die-Anweisung verwendet wird `Implements` , um Member einer Schnittstelle zu implementieren. Er definiert eine Schnittstelle `ICustomerInfo` mit dem Namen mit einem Ereignis, einer Eigenschaft und einer Prozedur. Die-Klasse implementiert alle Member, die `customerInfo` in der-Schnittstelle definiert sind.  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 Beachten Sie, dass die-Klasse `customerInfo` die- `Implements` Anweisung in einer separaten Quell Code Zeile verwendet, um anzugeben, dass die-Klasse alle Member der- `ICustomerInfo` Schnittstelle implementiert. Dann verwendet jedes Element in der-Klasse das- `Implements` Schlüsselwort als Teil seiner Member-Deklaration, um anzugeben, dass dieses Schnittstellenmember implementiert.  
  
## <a name="example"></a>Beispiel  
 Die folgenden zwei Prozeduren zeigen, wie Sie die im vorherigen Beispiel implementierte-Schnittstelle verwenden können. Fügen Sie dem Projekt diese Prozeduren hinzu, und nennen Sie die-Prozedur, um die Implementierung zu testen `testImplements` .  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Implementiert](implements-clause.md)
- [Interface-Anweisung](interface-statement.md)
- [Schnittstellen](../../programming-guide/language-features/interfaces/index.md)
