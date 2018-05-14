---
title: add (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: c1fa8c130475a67ac175205fe3491a32654ea475
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="add-c-reference"></a>add (C#-Referenz)
Das kontextabhängige Schlüsselwort `add` definiert einen benutzerdefinierten Ereignisaccessor, der aufgerufen wird, wenn der Clientcode ihr [Ereignis](../../../csharp/language-reference/keywords/event.md) abonniert. Wenn Sie einen benutzerdefinierten `add`-Accessor bereitstellen, müssen Sie auch einen [remove](../../../csharp/language-reference/keywords/remove.md)-Accessor angeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Ereignis gezeigt, dass über benutzerdefinierte `add`- und [remove](../../../csharp/language-reference/keywords/remove.md)-Accessoren verfügt. Das vollständige Beispiel finden Sie unter [Vorgehensweise: Implementieren von Schnittstellenereignissen](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/add_1.cs)]  
  
 Sie müssen normalerweise keine eigenen benutzerdefinierten Ereignisaccessoren bereitstellen. Die Accessoren, die automatisch vom Compiler generiert werden, wenn Sie ein Ereignis deklarieren, sind in den meisten Szenarios ausreichend.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)
