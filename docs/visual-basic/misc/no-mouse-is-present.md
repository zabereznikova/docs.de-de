---
title: Keine Maus vorhanden
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: ceb850d98d29c232da304fbdfaddf5611714ef1a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078852"
---
# <a name="no-mouse-is-present"></a>Keine Maus vorhanden

Eine der Eigenschaften des `My.Computer.Mouse` -Objekts wurde aufgerufen, aber der Computer verfügt über keine Maus, oder es ist kein Port für die Maus installiert.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Fügen Sie rund um den Aufruf der Eigenschaft des `Try...Catch` -Objekts einen `My.Computer.Mouse` -Block hinzu.  
  
     \- oder -  
  
- Installieren Sie auf dem Computer eine Maus.  
  
## <a name="see-also"></a>Siehe auch

- [My.Computer.Mouse](xref:Microsoft.VisualBasic.Devices.Mouse)
- [Behandeln und Auslösen von Ausnahmen in .NET](../../standard/exceptions/index.md)
- [Try... Catch... Abschließend-Anweisung](../language-reference/statements/try-catch-finally-statement.md)
