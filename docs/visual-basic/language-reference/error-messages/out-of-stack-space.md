---
title: Nicht genügend Stapelspeicher (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 25905e65e74b11d167d3ce2ad258599fb958eb88
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814600"
---
# <a name="out-of-stack-space-visual-basic"></a>Nicht genügend Stapelspeicher (Visual Basic)
Der Stapel ist ein Arbeitsbereich des Arbeitsspeichers, der wächst oder schrumpft dynamisch mit den Anforderungen des ausgeführten Programms an. Seine Grenzen wurden überschritten.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie, dass die Prozeduren nicht zu tief geschachtelt sind.  
  
2.  Stellen Sie sicher, dass rekursive Prozeduren ordnungsgemäß zu beenden.  
  
3.  Wenn lokale Variablen mehr Speicherplatz als verfügbar ist erforderlich, versuchen Sie es deklarieren einige Variablen auf Modulebene. Sie können alle Variablen in der Prozedur auch statische deklarieren, abgrenzen, indem Sie die `Property`, `Sub`, oder `Function` Schlüsselwort mit `Static`. Sie können auch die `Static` Anweisung, um einzelne statische Variablen innerhalb von Prozeduren deklarieren.  
  
4.  Definieren Sie einige Ihrer Zeichenfolgen fester Länge, als Zeichenfolgen variabler Länge aus, wie Zeichenfolgen mit fester Länge mehr Stapelspeicher als Zeichenfolgen variabler Länge verwenden. Sie können auch die Zeichenfolge auf Modulebene definieren, in denen es keine Stapelspeicher erfordert.  
  
5.  Überprüfen Sie die Anzahl der geschachtelten `DoEvents` Funktionsaufrufe, mit der `Calls` Dialogfeld anzeigen, welche Prozeduren auf dem Stapel aktiv sind.  
  
6.  Stellen Sie sicher, dass Sie nicht "Ereignisfolge" dazu führte, durch Auslösen eines Ereignisses, das eine Ereignisprozedur bereits auf dem Stapel aufruft. Eine Ereigniskette ist vergleichbar mit einer nicht abgeschlossenen rekursiven Prozeduraufruf, aber es ist weniger offensichtlich, da der Aufruf von Visual Basic, anstatt einen expliziten Aufruf im Code ausgeführt wird. Verwenden der `Calls` Dialogfeld anzeigen, welche Prozeduren auf dem Stapel aktiv sind.  
  
## <a name="see-also"></a>Siehe auch

- [Fenster "Arbeitsspeicher"](/visualstudio/debugger/memory-windows)
