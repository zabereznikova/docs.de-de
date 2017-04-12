---
title: Default-Eigenschaft &quot;&lt;propertyname1&gt;&quot;steht in Konflikt mit der Standardeigenschaft&quot;&lt;propertyname2&gt;&quot;in&quot;&lt;Classname&gt;&quot;und sollte daher als&quot;Shadows&quot;deklariert werden | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
dev_langs:
- VB
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 803b42b7659c16fd97251635e4b6ba49362e0a02
ms.lasthandoff: 03/13/2017

---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>Default-Eigenschaft '&lt;propertyname1&gt;"steht in Konflikt mit der Standardeigenschaft"&lt;propertyname2&gt;"in"&lt;Classname&gt;"und sollte daher als"Shadows"deklariert werden
Eine Eigenschaft wird mit den gleichen Namen wie eine Eigenschaft in der Basisklasse deklariert. In diesem Fall muss die Eigenschaft in dieser Klasse die Eigenschaft der Basisklasse überschatten.  
  
 Diese Meldung ist eine Warnung. `Shadows`wird standardmäßig angenommen. Weitere Informationen zum Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40007  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Hinzufügen der `Shadows` Schlüsselwort auf die Deklaration, oder ändern Sie der Namen der Eigenschaft deklariert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
