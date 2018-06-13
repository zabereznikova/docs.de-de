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
ms.openlocfilehash: 5afc7e4e3a03dfab1288e50e65e5076bdd438f7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604210"
---
# <a name="implements-statement"></a>Implements-Anweisung
Gibt eine oder mehrere Schnittstellen oder Schnittstellenmember wird, die in der Klasse implementiert werden müssen oder Strukturdefinition, die in dem er angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Teile  
 `interfacename`  
 Erforderlich. Eine Schnittstelle, deren Eigenschaften, Prozeduren und Ereignisse werden von den entsprechenden Elementen in der Klasse oder Struktur implementiert werden.  
  
 `interfacemember`  
 Erforderlich. Die Member einer Schnittstelle, die implementiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Eine Schnittstelle ist eine Auflistung von Prototypen, der Member (Eigenschaften, Prozeduren und Ereignisse) darstellen die Schnittstelle kapselt. Schnittstellen enthalten nur die Deklarationen für Elemente. implementieren diese Member, Klassen und Strukturen. Weitere Informationen finden Sie unter [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Die `Implements` Anweisung muss unmittelbar folgen der `Class` oder `Structure` Anweisung.  
  
 Wenn Sie eine Schnittstelle implementieren, müssen Sie alle in der Schnittstelle deklarierten Member implementieren. Auslassen von einem beliebigen Mitglied gilt einen Syntaxfehler. Um einen einzelnen Member implementieren zu können, geben Sie die [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md) Schlüsselwort (unterscheidet sich von der `Implements` Anweisung) Wenn Sie das Element in der Klasse oder Struktur deklarieren. Weitere Informationen finden Sie unter [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Klassen können [Private](../../../visual-basic/language-reference/modifiers/private.md) Implementierungen von Eigenschaften und Prozeduren, sondern diese Member nur eine Instanz der implementierenden Klasse in eine Variable deklariert den Typ der Schnittstelle umwandeln zugänglich sind.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `Implements` Anweisung, um die Member einer Schnittstelle zu implementieren. Definiert eine Schnittstelle mit dem Namen `ICustomerInfo` mit einem Ereignis, eine Eigenschaft und einer Prozedur. Die Klasse `customerInfo` implementiert alle in der Schnittstelle definierten Member.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 Beachten Sie, dass die Klasse `customerInfo` verwendet die `Implements` Anweisung auf einer separaten Quellcodezeile um anzugeben, dass die Klasse alle Member implementiert die `ICustomerInfo` Schnittstelle. Klicken Sie dann auf jedes Element in der Klasse verwendet die `Implements` -Schlüsselwort als Teil der Element-Deklaration, um anzugeben, dass er diesen Schnittstellenmember implementiert.  
  
## <a name="example"></a>Beispiel  
 Zwei Nachfolgend wird erläutert, wie Sie die im vorherigen Beispiel implementierte Schnittstelle verwenden können. Um die Implementierung zu testen, fügen Sie diese Verfahren auf Ihr Projekt, und rufen die `testImplements` Prozedur.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
