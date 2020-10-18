---
title: Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: c5e8b8de3477147fc3174cdbee401c89753004ad
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159949"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.

Sie haben versucht, eine `WithEvents` Variable mit einer Komponente zu verwenden, die nicht als Ereignis Quelle für den angegebenen Satz von Ereignissen verwendet werden kann. Sie möchten z. b. die Ereignisse eines Objekts senken und dann ein weiteres Objekt erstellen, das `Implements` das erste Objekt ist. Obwohl Sie vielleicht denken, dass Sie die Ereignisse aus dem implementierten Objekt absenken könnten, ist dies nicht immer der Fall. `Implements` implementiert nur eine Schnittstelle für Methoden und Eigenschaften. `WithEvents` wird für private nicht unterstützt `UserControls` , da die Typinformationen, die erforderlich sind, um den zu erhöhen, zur `ObjectEvent` Laufzeit nicht verfügbar sind.

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Ereignisse für eine Komponente, die keine Ereignisse enthält, können nicht als Senke verwendet werden.

## <a name="see-also"></a>Siehe auch

- [WithEvents](../modifiers/withevents.md)
- [Implements-Anweisung](../statements/implements-statement.md)
