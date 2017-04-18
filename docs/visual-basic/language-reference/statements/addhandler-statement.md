---
title: AddHandler-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
dev_langs:
- VB
helpviewer_keywords:
- AddHandler statement
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
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
ms.openlocfilehash: 728d8393c44d777f9cc016d9cf66030036582ae4
ms.lasthandoff: 03/13/2017

---
# <a name="addhandler-statement"></a>AddHandler-Anweisung
Ordnet ein Ereignis zur Laufzeit einen Ereignishandler.  
  
## <a name="syntax"></a>Syntax  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Teile  
 `event`  
 Der Name des zu behandelnden Ereignisses.  
  
 `eventhandler`  
 Der Name einer Prozedur, die das Ereignis behandelt.  
  
## <a name="remarks"></a>Hinweise  
 Die `AddHandler` und `RemoveHandler` -Anweisungen ermöglichen Ihnen das Starten und Beenden der Ereignisbehandlung zu einem beliebigen Zeitpunkt während der Ausführung des Programms.  
  
 Die Signatur der `eventhandler` Verfahren muss der Signatur des Ereignisses entsprechen `event`.  
  
 Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede. Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen. Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet.  Weitere Informationen finden Sie unter [behandelt](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
>  Für benutzerdefinierte Ereignisse die `AddHandler` -Anweisung ruft des Ereignis `AddHandler` Accessor. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrEvents&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
