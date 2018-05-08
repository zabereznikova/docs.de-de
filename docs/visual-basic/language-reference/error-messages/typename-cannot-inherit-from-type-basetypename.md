---
title: '&#39;&lt;TypeName&gt; &#39; kann nicht Vererben &lt;Typ&gt; &#39; &lt;Basistypname&gt; &#39; erweitert den Zugriff von Basis-und &lt;Typ&gt; außerhalb der Assembly'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: f747b2b24f5fecc22b9e1fbc6ba26b634e9ead2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;TypeName&gt; &#39; kann nicht Vererben &lt;Typ&gt; &#39; &lt;Basistypname&gt; &#39; erweitert den Zugriff von Basis-und &lt;Typ&gt; außerhalb der Assembly
Eine Klasse oder Schnittstelle erbt von einer Basisklasse oder Schnittstelle enthält jedoch eine weniger restriktive Zugriffsebene.  
  
 Z. B. eine `Public` Schnittstelle erbt von einer `Friend` -Schnittstelle, oder eine `Protected` Klasse erbt von einer `Private` Klasse. Dies stellt die Basisklasse oder-Schnittstelle außerhalb der vorgesehenen Ebene den Zugriff auf.  
  
 **Fehler-ID:** BC30910  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ändern Sie die Zugriffsebene der abgeleiteten Klasse oder Schnittstelle, die mindestens so restriktiv wie, die von der Basisklasse oder Schnittstelle sein.  
  
     - oder -   
  
-   Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die `Inherits` Anweisung. Sie können nicht von einem eingeschränkteren Basisklasse oder Schnittstelle erben.  
  
## <a name="see-also"></a>Siehe auch  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
