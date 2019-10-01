---
title: Der Membername eines anonymen Typs kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: 38f669fe183ac79ebed6e5a122bc70aedc9bb753
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701225"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Der Membername eines anonymen Typs kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
Sie können den Namen eines anonymen Typmembers nicht aus einem komplexen Ausdruck ableiten.  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Weitere Informationen zu Quellen, aus denen anonyme Typen Elementnamen und-Typen ableiten können und nicht ableiten können, finden Sie unter [gewusst wie: Eigenschaften Namen und Typen in Deklarationen anonymer Typen @ no__t-0 ableiten.  
  
 **Fehler-ID:** BC36556  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Weisen Sie den Ausdruck einem Elementnamen zu, wie im folgenden Code gezeigt:  
  
    ```vb  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Vorgehensweise: Eigenschaften Namen und Typen in Deklarationen anonymer Typen eingeben @ no__t-0
