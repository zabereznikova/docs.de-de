---
title: "Eigenschaft der &#39; &lt;Propertyname&gt;&#39; ist nicht &#39; t für alle Codepfade einen Wert zurück"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c9ef5b2ac62412f5684cbc78ab6bebf6bc7b6752
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Eigenschaft der &#39; &lt;Propertyname&gt;&#39; ist nicht &#39; t für alle Codepfade einen Wert zurück
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
