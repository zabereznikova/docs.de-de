---
title: remove (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: 245ef0a16fd2cec2f36c86dd0ac3b8838a76b02e
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999770"
---
# <a name="remove-c-reference"></a>remove (C#-Referenz)
Das kontextabhängige Schlüsselwort `remove` definiert einen benutzerdefinierten Ereignisaccessor, der aufgerufen wird, wenn der Clientcode das Abonnement Ihres Ereignisses ([event](../../../csharp/language-reference/keywords/event.md)) aufhebt. Wenn Sie einen benutzerdefinierten `remove`-Accessor bereitstellen, müssen Sie auch einen [add](../../../csharp/language-reference/keywords/add.md)-Accessor angeben.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird ein Ereignis mit den benutzerdefinierten Accessoren [add](../../../csharp/language-reference/keywords/add.md) und `remove` gezeigt. Das vollständige Beispiel finden Sie unter [Vorgehensweise: Implementieren von Schnittstellenereignissen](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 Sie müssen normalerweise keine eigenen benutzerdefinierten Ereignisaccessoren bereitstellen. Die Accessoren, die automatisch vom Compiler generiert werden, wenn Sie ein Ereignis deklarieren, sind in den meisten Szenarios ausreichend.  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse](../../../csharp/programming-guide/events/index.md)
