---
title: "Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be4b9140222ef969bfb836fd74f45b8f662360b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.
Sie haben versucht, mit einem `WithEvents` Variable mit einer Komponente, die als Ereignisquelle für den angegebenen Satz von Ereignissen nicht funktionieren. Sie möchten z. B. die Ereignisse eines Objekts aufzufangen und anschließend ein anderes Objekt zu erstellen, die `Implements` das erste Objekt. Obwohl Sie denken, dass Sie die Ereignisse aus dem Objekt implementiert sink konnte vielleicht, ist dies nicht immer der Fall. `Implements`nur eine Schnittstelle für Methoden und Eigenschaften implementiert wird. `WithEvents`wird nicht unterstützt für Private `UserControls`, da die Typinformationen zum Auslösen der `ObjectEvent` zur Laufzeit nicht verfügbar ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Sie können nicht für eine Komponente Auffangen von Ereignissen, die nicht im Quellmodell Ereignisse.  
  
## <a name="see-also"></a>Siehe auch  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)
