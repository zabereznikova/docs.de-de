---
title: Standardeigenschaft &#39; &lt;eigenschaftsname1&gt; &#39; steht in Konflikt mit der Standardeigenschaft &#39; &lt;propertyname2&gt; &#39; in &#39; &lt;Classname&gt; &#39;und sollte daher deklariert werden &#39;Schatten&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: b305f7a59a9865ebeb6b6f53607757b719fb4d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586623"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>Standardeigenschaft &#39; &lt;eigenschaftsname1&gt; &#39; steht in Konflikt mit der Standardeigenschaft &#39; &lt;propertyname2&gt; &#39; in &#39; &lt;Classname&gt; &#39;und sollte daher deklariert werden &#39;Schatten&#39;
Mit dem gleichen Namen wie eine in der Basisklasse definierte Eigenschaft ist eine Eigenschaft deklariert. In diesem Fall muss die Eigenschaft in dieser Klasse die Eigenschaft der Basisklasse überschatten.  
  
 Diese Meldung ist eine Warnung. `Shadows` wird standardmäßig angenommen. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40007  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Hinzufügen der `Shadows` Schlüsselwort, um die Deklaration, oder ändern Sie der Namen der Eigenschaft deklariert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
