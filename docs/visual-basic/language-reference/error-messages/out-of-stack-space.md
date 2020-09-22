---
title: Nicht genügend Stapelspeicher
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: afb6a42372bdbd2e49ac15fbbf2b9e254f8db431
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871315"
---
# <a name="out-of-stack-space-visual-basic"></a>Nicht genügend Stapelspeicher (Visual Basic)

Der Stapel ist ein Arbeitsbereich des Arbeitsspeichers, der dynamisch mit den Anforderungen Ihres ausführenden Programms vergrößert und verkleinert wird. Die Grenzen wurden überschritten.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie, ob Prozeduren zu tief geschachtelt sind.  
  
2. Stellen Sie sicher, dass rekursive Prozeduren richtig  
  
3. Wenn lokale Variablen mehr lokalen Variablen Speicher benötigen, als verfügbar ist, versuchen Sie, einige Variablen auf Modulebene zu deklarieren. Sie können auch alle Variablen in der Prozedur static deklarieren, indem Sie das `Property` `Sub` Schlüsselwort, oder mit vorangestellt haben `Function` `Static` . Oder Sie können die- `Static` Anweisung verwenden, um einzelne statische Variablen in Prozeduren zu deklarieren.  
  
4. Definieren Sie einige der Zeichen folgen fester Länge als Zeichen folgen variabler Länge neu, da Zeichen folgen fester Länge mehr Stapel Speicher als Zeichen folgen variabler Länge verwenden. Sie können auch die Zeichenfolge auf Modulebene definieren, an der kein Stapel Speicherplatz erforderlich ist.  
  
5. Überprüfen Sie die Anzahl der aufgerufenen `DoEvents` Funktionsaufrufe, indem Sie im `Calls` Dialogfeld anzeigen, welche Prozeduren auf dem Stapel aktiv sind.  
  
6. Stellen Sie sicher, dass Sie keine "Ereignis Cascade" verursacht haben, indem Sie ein Ereignis auslösen, das eine bereits auf dem Stapel bereits aufgerufenen Ereignis Prozedur aufruft. Eine Ereignis Kaskadierung ähnelt einem nicht abgeschlossenen rekursiven Prozedur Aufruf, aber Sie ist weniger offensichtlich, da der-Befehl durch Visual Basic statt eines expliziten Aufrufes im Code erfolgt. Verwenden `Calls` Sie das Dialogfeld, um anzuzeigen, welche Prozeduren auf dem Stapel aktiv sind.  
  
## <a name="see-also"></a>Siehe auch

- [Fenster "Arbeitsspeicher"](/visualstudio/debugger/memory-windows)
