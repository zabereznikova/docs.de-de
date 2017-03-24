---
title: "Nicht genügend Stapelspeicher (Visual Basic) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
dev_langs:
- VB
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6343767da28ea4e02f9443006b222640755f7882
ms.lasthandoff: 03/13/2017

---
# <a name="out-of-stack-space-visual-basic"></a>Nicht genügend Stapelspeicher (Visual Basic)
Der Stapel ist ein Arbeitsbereich des Arbeitsspeichers, der vergrößert bzw. verkleinert dynamisch mit der Auslastung des ausgeführten Programms an. Die Grenzen wurden überschritten.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie, dass Prozeduren nicht zu tief geschachtelt sind.  
  
2.  Stellen Sie sicher, dass rekursive Prozeduren ordnungsgemäß zu beenden.  
  
3.  Wenn lokale Variablen mehr Speicherplatz als erforderlich ist, versuchen Sie, einige Variablen auf Modulebene zu deklarieren. Sie können alle Variablen in der Prozedur auch statische deklarieren, indem Sie vor der `Property`, `Sub`, oder `Function` Schlüsselwort mit `Static`. Sie können auch die `Static` Anweisung, um einzelne statische Variablen innerhalb von Prozeduren zu deklarieren.  
  
4.  Definieren Sie einige Zeichenfolgen fester Länge als Zeichenfolgen variabler Länge, wie Zeichenfolgen mit fester Länge als Zeichenfolgen variabler Länge mehr Stapelspeicher verwenden. Sie können auch die Zeichenfolge auf Modulebene definieren, in denen es keine Stapelspeicher erfordert.  
  
5.  Überprüfen Sie die Anzahl der geschachtelten `DoEvents` Funktionsaufrufe, mithilfe der `Calls` Dialogfeld, welche Prozeduren aktiv auf dem Stapel.  
  
6.  Stellen Sie sicher, dass Sie nicht "Ereignisfolge" durch das Auslösen eines Ereignisses, das eine Ereignisprozedur bereits auf dem Stapel aufgerufen wird. Eine Ereigniskette ist mit einem nicht abgeschlossenen rekursiven Prozeduraufruf, aber es ist weniger offensichtlich, da der Aufruf erfolgt [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] anstatt explizit im Code. Verwenden der `Calls`Dialogfeld, welche Prozeduren aktiv auf dem Stapel.  
  
## <a name="see-also"></a>Siehe auch  
 [Fenster "Arbeitsspeicher"](https://docs.microsoft.com/visualstudio/debugger/memory-windows)
