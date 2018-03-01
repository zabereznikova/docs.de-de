---
title: "&lt;Typ1&gt;&#39;&lt; TypeName&gt;&#39; muss implementieren &#39;&lt; Methodenname&gt;&#39; für Schnittstelle &#39;&lt; Schnittstellenname&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e803ec7d0054f2fa1b9ed2a731fd30c9c3060468
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;Typ1&gt;&#39;&lt; TypeName&gt;&#39; muss implementieren &#39;&lt; Methodenname&gt;&#39; für Schnittstelle &#39;&lt; Schnittstellenname&gt;&#39;
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
