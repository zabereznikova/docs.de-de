---
title: "Kann nicht auf verweisen &#39; &lt;Namen&gt;&#39; da es Mitglied der typisierte Wert Feld &#39; ist&lt; Namen&gt;&#39; Klasse &#39;&lt; Klassenname&gt;&#39; verfügt über &#39; System.MarshalByRefObject &#39; als Basisklasse"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a84811b9f0e706cf3ebede09e07c03bd7e4cea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>Kann nicht auf verweisen &#39; &lt;Namen&gt;&#39; da es Mitglied der typisierte Wert Feld &#39; ist&lt; Namen&gt;&#39; Klasse &#39;&lt; Klassenname&gt;&#39; verfügt über &#39; System.MarshalByRefObject &#39; als Basisklasse
Die `System.MarshalByRefObject` -Klasse ermöglicht es Anwendungen, die remote-Zugriff auf Objekte über Anwendungsdomänengrenzen hinweg zu unterstützen. Typen müssen von erben die `MarshalByRejectObject` Klasse, wenn der Typ über Anwendungsdomänengrenzen hinweg verwendet wird. Der Zustand des Objekts muss nicht kopiert werden, da die Member des Objekts nicht außerhalb der Anwendungsdomäne verwendet werden, in denen sie erstellt wurden.  
  
 **Fehler-ID:** BC30310  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie den Verweis, um sicherzustellen, dass das Element, auf die verwiesen wird, gültig ist.  
  
2.  Explizit zu qualifizieren das Element mit dem `Me` Schlüsselwort.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.MarshalByRefObject>  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
