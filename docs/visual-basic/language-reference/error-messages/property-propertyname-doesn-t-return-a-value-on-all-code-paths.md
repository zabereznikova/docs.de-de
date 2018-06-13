---
title: Eigenschaft &#39; &lt;Propertyname&gt; &#39; ist nicht&#39;t für alle Codepfade einen Wert zurück
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 72bc7e45cadd2528f29c88bf6e80ee5f381052dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594213"
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Eigenschaft &#39; &lt;Propertyname&gt; &#39; ist nicht&#39;t für alle Codepfade einen Wert zurück
Eigenschaft '\<Propertyname >' ist nicht für alle Codepfade einen Wert zurück. Wenn das Ergebnis verwendet wird, kann während der Laufzeit eine NULL-Verweisausnahme auftreten.  
  
 Eine Eigenschaft `Get` Prozedur hat mindestens einen möglichen Pfad durch ihren Code, die keinen Wert zurückgibt.  
  
 Sie können einen Wert aus einer Eigenschaft zurückgeben `Get` Prozedur in einem der folgenden Methoden:  
  
-   Weisen Sie den Wert des Eigenschaftennamens und führen Sie dann eine `Exit Property` Anweisung.  
  
-   Weisen Sie den Wert des Eigenschaftennamens und führen Sie dann die `End Get` Anweisung.  
  
-   Schließen Sie den Wert in einer [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Wenn die Steuerung an übergibt `Exit Property` oder `End Get` und des Eigenschaftennamens nicht ausnahmslos zugewiesene der `Get` Prozedur gibt den Standardwert des Datentyps für die Eigenschaft zurück. Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42107  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, die bewirkt, eine Rückgabe dass.  
  
     Es ist einfacher, um sicherzustellen, dass jede Rückgabe aus der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung. Wenn Sie die letzte Anweisung vor dazu `End Get` sollte eine `Return` Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
