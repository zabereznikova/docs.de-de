---
title: Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: e55a5515d88bd2782e31fdea7c07e16c595d43b5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873654"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.

Sie haben versucht, eine `WithEvents` Variable mit einer Komponente zu verwenden, die nicht als Ereignis Quelle für den angegebenen Satz von Ereignissen verwendet werden kann. Sie möchten z. b. die Ereignisse eines Objekts senken und dann ein weiteres Objekt erstellen, das `Implements` das erste Objekt ist. Obwohl Sie vielleicht denken, dass Sie die Ereignisse aus dem implementierten Objekt absenken könnten, ist dies nicht immer der Fall. `Implements` implementiert nur eine Schnittstelle für Methoden und Eigenschaften. `WithEvents` wird für private nicht unterstützt `UserControls` , da die Typinformationen, die erforderlich sind, um den zu erhöhen, zur `ObjectEvent` Laufzeit nicht verfügbar sind.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Ereignisse für eine Komponente, die keine Ereignisse enthält, können nicht als Senke verwendet werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [WithEvents](../modifiers/withevents.md)
- [Implements-Anweisung](../statements/implements-statement.md)
