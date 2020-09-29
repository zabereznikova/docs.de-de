---
description: Hier erfahren Sie, wie Sie mithilfe des Schlüsselworts „add“ in C# benutzerdefinierte Ereignisaccessoren erstellen.
title: add – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: 9daf635206ff9727a4bf333c123f68be812723cd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168763"
---
# <a name="add-c-reference"></a>add (C#-Referenz)

Das kontextabhängige Schlüsselwort `add` definiert einen benutzerdefinierten Ereignisaccessor, der aufgerufen wird, wenn der Clientcode ihr [Ereignis](./event.md) abonniert. Wenn Sie einen benutzerdefinierten `add`-Accessor bereitstellen, müssen Sie auch einen [remove](./remove.md)-Accessor angeben.  
  
## <a name="example"></a>Beispiel  

Im folgenden Beispiel wird ein Ereignis gezeigt, dass über benutzerdefinierte `add`- und [remove](./remove.md)-Accessoren verfügt. Das vollständige Beispiel finden Sie unter [Vorgehensweise: Implementieren von Schnittstellenereignissen](../../programming-guide/events/how-to-implement-interface-events.md).
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 Sie müssen normalerweise keine eigenen benutzerdefinierten Ereignisaccessoren bereitstellen. Die Accessoren, die automatisch vom Compiler generiert werden, wenn Sie ein Ereignis deklarieren, sind in den meisten Szenarios ausreichend.  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse](../../programming-guide/events/index.md)
