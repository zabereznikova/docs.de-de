---
title: Kann nicht auf verweisen &#39; &lt;Namen&gt; &#39; , da es sich um ein Mitglied der Werttypen basierenden Felds ist &#39; &lt;Namen&gt; &#39; Klasse &#39; &lt;Classname&gt; &#39;IValidator.h &#39;System.MarshalByRefObject&#39; als Basisklasse
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: a6298c3e0f5102397d5cc3f237a186598c6b5ecc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739296"
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>Kann nicht auf verweisen &#39; &lt;Namen&gt; &#39; , da es sich um ein Mitglied der Werttypen basierenden Felds ist &#39; &lt;Namen&gt; &#39; Klasse &#39; &lt;Classname&gt; &#39;IValidator.h &#39;System.MarshalByRefObject&#39; als Basisklasse
Die `System.MarshalByRefObject` -Klasse ermöglicht es Anwendungen, die remote-Zugriff auf Objekte über Anwendungsdomänen hinweg zu unterstützen. Typen müssen erben von der `MarshalByRejectObject` Klasse, wenn der Typ über Anwendungsdomänengrenzen hinweg verwendet wird. Der Zustand des Objekts muss nicht kopiert werden, da die Member des Objekts nicht außerhalb der Anwendungsdomäne verwendet werden, in denen sie erstellt wurden.  
  
 **Fehler-ID:** BC30310  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie den Verweis auf die Stellen Sie sicher, dass das Element verwiesen wird, gültig ist.  
  
2.  Qualifizieren Sie explizit das Element mit dem `Me` Schlüsselwort.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.MarshalByRefObject>
- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
