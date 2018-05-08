---
title: '&lt;Typ1&gt;&#39;&lt;Typename&gt; &#39; implementieren müssen &#39; &lt;Methodname&gt; &#39; für Schnittstelle &#39; &lt;Schnittstellenname&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: daeeab853f6a7f582542fa15ffc09ce749731d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;Typ1&gt;&#39;&lt;Typename&gt; &#39; implementieren müssen &#39; &lt;Methodname&gt; &#39; für Schnittstelle &#39; &lt;Schnittstellenname&gt;&#39;
Eine Klasse oder Struktur Ansprüche an, um eine Schnittstelle zu implementieren, implementiert jedoch keine Prozedur, die von der Schnittstelle definiert. Jeder Member der Schnittstelle muss implementiert werden.  
  
 **Fehler-ID:** BC30149  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie eine Prozedur mit demselben Namen und derselben Signatur wie in der Schnittstelle definiert. Schließen Sie unbedingt mit mindestens der `End Function` oder `End Sub` Anweisung.  
  
2.  Hinzufügen einer `Implements` -Klausel, um das Ende der `Function` oder `Sub` Anweisung. Zum Beispiel:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
