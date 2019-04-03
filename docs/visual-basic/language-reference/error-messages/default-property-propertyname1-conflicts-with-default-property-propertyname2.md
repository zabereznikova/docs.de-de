---
title: Die "<propertyname1>"-Standardeigenschaft verursacht einen Konflikt mit der "<propertyname2>"-Standardeigenschaft in "<classname>" und sollte daher als "Shadows" deklariert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: ab45278b2e1199282e3066c34828b9bda716e162
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813170"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>Default-Eigenschaft "\<eigenschaftsname1 >" verursacht einen Konflikt mit Default-Eigenschaft "\<propertyname2 >' in '\<Klassenname >' und daher als"Shadows"deklariert werden soll
Eine Eigenschaft wird mit dem gleichen Namen wie eine Eigenschaft in der Basisklasse deklariert. In diesem Fall muss die Eigenschaft in dieser Klasse als Eigenschaft der Basisklasse überschatten.  
  
 Diese Meldung ist eine Warnung. `Shadows` wird standardmäßig angenommen. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40007  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Hinzufügen der `Shadows` Schlüsselwort, um die Deklaration, oder ändern, die der Namen der Eigenschaft deklariert wird.  
  
## <a name="see-also"></a>Siehe auch

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
