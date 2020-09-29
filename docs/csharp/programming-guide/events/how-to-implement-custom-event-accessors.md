---
title: 'Vorgehensweise: Implementieren benutzerdefinierter Ereignisaccessoren (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie benutzerdefinierte Ereignisaccessoren implementieren. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 41c9bd255bf66cd914982b6044c4acaef66b8fcf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167560"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Vorgehensweise: Implementieren benutzerdefinierter Ereignisaccessoren (C#-Programmierleitfaden)

Ein Ereignis ist eine besondere Art eines Multitaskdelegaten, der nur aus der Klasse , in der er deklariert ist, aufgerufen werden kann. Der Client abonniert das Ereignis durch Bereitstellen eines Verweises auf eine Methode, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird. Diese Methoden werden der Aufrufliste des Delegaten über Ereignisaccessoren hinzugefügt, die Eigenschaftenaccessoren ähneln, mit der Ausnahme, dass Ereignisaccessoren mit `add` und `remove` bezeichnet werden. In den meisten Fällen müssen Sie keine benutzerdefinierten Ereignisaccessoren angeben. Wenn keine benutzerdefinierten Ereignisaccessoren im Code angegeben werden, werden sie durch den Compiler automatisch hinzugefügt. In einigen Fällen müssen Sie möglicherweise jedoch benutzerdefiniertes Verhalten bereitstellen. Einen solchen Fall enthält das Thema [Vorgehensweise: Implementieren von Schnittstellenereignissen](./how-to-implement-interface-events.md).
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel veranschaulicht das Implementieren von Ereignisaccessoren zum Hinzufügen und Entfernen. Obwohl Sie Code innerhalb der Accessoren ersetzen können, wird empfohlen, dass Sie das Ereignis sperren, bevor Sie eine neue Ereignishandlermethode hinzufügen oder entfernen.  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse](./index.md)
- [event](../../language-reference/keywords/event.md)
