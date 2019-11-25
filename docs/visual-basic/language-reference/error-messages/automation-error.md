---
title: Automatisierungsfehler
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: df153167bc8c73a2d3760c8d7db30dccfa468e35
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976149"
---
# <a name="automation-error"></a>Automatisierungsfehler

Beim Ausführen einer Methode oder Abrufen oder Festlegen einer Eigenschaft einer Objektvariable ist ein Fehler aufgetreten. Der Fehler wurde von der Anwendung gemeldet, mit der das Objekt erstellt wurde.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die Eigenschaften des `Err`-Objekts, um die Ursache und die Art des Fehlers zu ermitteln.  
  
2. Verwenden Sie die Anweisung `On Error Resume Next` unmittelbar vor der Zugriffsanweisung, und prüfen Sie dann unmittelbar nach der Zugriffsanweisung auf Fehler hin.  
  
## <a name="see-also"></a>Siehe auch

- [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Sprechen Sie mit uns](/visualstudio/ide/feedback-options)
