---
title: Der Membername eines anonymen Typs kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: f657048a8aa9748104e40503e727a5e6d90a87ad
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646855"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Der Membername eines anonymen Typs kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
Einen anonymer Typmembernamen aus einem komplexen Ausdruck kann nicht abgeleitet werden.  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Weitere Informationen zu Quellen, von dem anonyme Typen können, und können nicht abgeleitet, Membernamen und-Typen, finden Sie unter [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
 **Fehler-ID:** BC36556  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Weisen Sie den Ausdruck zu einem Elementnamen, wie im folgenden Code gezeigt:  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
