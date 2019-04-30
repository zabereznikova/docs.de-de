---
title: Die Verwendung der Standardinstanz einer Klasse im Klassenkonstruktor kann zu einem unendlichen rekursiven Aufruf führen.
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 14c498bf3067415f8de2afaeaaa57cf3f28ae857
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022453"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>Die Verwendung der Standardinstanz einer Klasse im Klassenkonstruktor kann zu einem unendlichen rekursiven Aufruf führen.
Eine Standardinstanz einer Klasse wurde im Konstruktor der Klasse verwendet. Dies kann zu einem unendlichen rekursiven Aufruf, auch bekannt als Endlosschleife, führen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie die Standardinstanz aus dem Klassenkonstruktor.  
  
## <a name="see-also"></a>Siehe auch

- [Konstruktoren](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
