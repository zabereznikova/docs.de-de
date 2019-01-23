---
title: '&#39;&lt;TypeName&gt; &#39; kann nicht von erben &lt;Typ&gt; &#39; &lt;Basistypname&gt; &#39; erweitert den Zugriff der Basis &lt;Typ&gt; außerhalb der Assembly'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 108025132bdd0fa86df5ed142aaa39c7b7e18062
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556482"
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;TypeName&gt; &#39; kann nicht von erben &lt;Typ&gt; &#39; &lt;Basistypname&gt; &#39; erweitert den Zugriff der Basis &lt;Typ&gt; außerhalb der Assembly
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
