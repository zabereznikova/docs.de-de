---
title: <typename> erweitert den Zugriff der Basis-<type> außerhalb der Assembly und kann daher nicht von <basetypename> '<type>' erben.
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 226c85f887ecc706a5cb554c2163742f10896141
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269821"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>'\<Typname >' kann nicht von erben \<Typ > '\<Basistypname >' erweitert den Zugriff der Basis \<Typ > außerhalb der Assembly
Eine Klasse oder Schnittstelle erbt von einer Basisklasse oder Schnittstelle weist jedoch eine weniger restriktive Zugriffsebene.  
  
 Z. B. eine `Public` Schnittstelle erbt von einer `Friend` -Schnittstelle, oder ein `Protected` Klasse erbt von einer `Private` Klasse. Dies stellt die Basisklasse oder Schnittstelle, um nach den gewünschten zugreifen.  
  
 **Fehler-ID:** BC30910  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ändern Sie die Zugriffsebene der abgeleiteten Klasse oder Schnittstelle, die mindestens so restriktiv wie der Basisklasse oder Schnittstelle sein.  
  
     - oder -   
  
-   Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die `Inherits` Anweisung. Sie können nicht von einem eingeschränkteren Basisklasse oder Schnittstelle erben.  
  
## <a name="see-also"></a>Siehe auch
- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
