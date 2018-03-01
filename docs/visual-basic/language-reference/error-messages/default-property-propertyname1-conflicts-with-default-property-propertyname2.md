---
title: Standardeigenschaft &#39; &lt;eigenschaftsname1&gt;&#39; steht in Konflikt mit der Standardeigenschaft &#39;&lt; propertyName2&gt;&#39; in &#39;&lt; Klassenname&gt;&#39; und sollte daher deklariert werden &#39; Shadows &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af92c06f6d07b6ea64a05b9043547a46e3679111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>Standardeigenschaft &#39; &lt;eigenschaftsname1&gt;&#39; steht in Konflikt mit der Standardeigenschaft &#39;&lt; propertyName2&gt;&#39; in &#39;&lt; Klassenname&gt;&#39; und sollte daher deklariert werden &#39; Shadows &#39;
Mit dem gleichen Namen wie eine in der Basisklasse definierte Eigenschaft ist eine Eigenschaft deklariert. In diesem Fall muss die Eigenschaft in dieser Klasse die Eigenschaft der Basisklasse überschatten.  
  
 Diese Meldung ist eine Warnung. `Shadows` wird standardmäßig angenommen. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40007  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Hinzufügen der `Shadows` Schlüsselwort, um die Deklaration, oder ändern Sie der Namen der Eigenschaft deklariert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
