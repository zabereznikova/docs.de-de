---
title: "Die Verwendung der Standardinstanz einer Klasse im Klassenkonstruktor kann zu einem unendlichen rekursiven Aufruf führen."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6a0c54c6e62f9bdc7fe510500a486461d26636d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>Die Verwendung der Standardinstanz einer Klasse im Klassenkonstruktor kann zu einem unendlichen rekursiven Aufruf führen.
Eine Standardinstanz einer Klasse wurde im Konstruktor der Klasse verwendet. Dies kann zu einem unendlichen rekursiven Aufruf, auch bekannt als Endlosschleife, führen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Standardinstanz aus dem Klassenkonstruktor.  
  
## <a name="see-also"></a>Siehe auch  
 [Konstruktoren](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
