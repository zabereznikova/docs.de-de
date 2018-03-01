---
title: "&lt;Typ1&gt;&#39;&lt; TypeName&gt;&#39; muss implementieren &#39;&lt; Membername&gt;&#39; für Schnittstelle &#39;&lt; Schnittstellenname&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05e0229d0259c519d4db265c017a5040b425c79a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;Typ1&gt;&#39;&lt; TypeName&gt;&#39; muss implementieren &#39;&lt; Membername&gt;&#39; für Schnittstelle &#39;&lt; Schnittstellenname&gt;&#39;
"\<Typename >" implementieren müssen "\<Membername >' für die Schnittstelle"\<Schnittstellenname >'. Implementieren die Eigenschaft müssen übereinstimmen "ReadOnly" / "WriteOnly" Spezifizierer.  
  
 Eine Klasse oder Struktur Ansprüche an, um eine Schnittstelle zu implementieren, aber eine Prozedur, Eigenschaft oder Ereignis definiert, durch die Schnittstelle nicht implementiert. Jeder Member der Schnittstelle muss implementiert werden.  
  
 **Fehler-ID:** BC30154  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie einen Member mit demselben Namen und derselben Signatur wie in der Schnittstelle definiert. Schließen Sie unbedingt mit mindestens der `End Function`, `End Sub`, oder `End Property` Anweisung.  
  
2.  Hinzufügen einer `Implements` -Klausel, um das Ende der `Function`, `Sub`, `Property`, oder `Event` Anweisung. Zum Beispiel:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  Wenn Sie eine Eigenschaft zu implementieren, stellen sicher, dass `ReadOnly` oder `WriteOnly` auf die gleiche Weise wie in der Schnittstellendefinition verwendet wird.  
  
4.  Beim Implementieren einer Eigenschaft deklarieren `Get` und `Set` Prozeduren nach Bedarf.  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
