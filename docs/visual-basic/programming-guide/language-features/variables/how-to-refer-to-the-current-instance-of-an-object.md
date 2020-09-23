---
title: 'Vorgehensweise: Verweisen auf die aktuelle Instanz eines Objekts'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 64d21fe4aaf6fd34bf880373a7ab3067fb67820e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077058"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Gewusst wie: Verweisen auf die aktuelle Instanz eines Objekts (Visual Basic)

Die *aktuelle Instanz* eines-Objekts ist die Instanz, in der der Code gerade ausgeführt wird.  
  
 Verwenden Sie das- `Me` Schlüsselwort, um auf die aktuelle-Instanz zu verweisen.  
  
### <a name="to-refer-to-the-current-instance"></a>So verweisen Sie auf die aktuelle Instanz  
  
- Verwenden `Me` Sie das Schlüsselwort, in dem Sie normalerweise den Namen einer Objektvariablen verwenden.  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Obwohl `Me` sich wie eine Objekt Variable verhält, können Sie Sie nicht deklarieren oder ihr andere zuweisen. `Me` verweist immer auf die aktuelle-Instanz.  
  
## <a name="see-also"></a>Siehe auch

- [Objektvariablen](object-variables.md)
- [Zuweisung von Objektvariablen](object-variable-assignment.md)
- [Me, My, MyBase und MyClass](../../program-structure/me-my-mybase-and-myclass.md)
