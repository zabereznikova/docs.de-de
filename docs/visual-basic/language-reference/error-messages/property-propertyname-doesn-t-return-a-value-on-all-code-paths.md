---
title: Eigenschaft &#39; &lt;Propertyname&gt; &#39; &#39;t für alle Codepfade einen Wert zurück
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: b8059ebc9b6c1de685f2f04c3ee362ab8cf6d05e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611253"
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Eigenschaft &#39; &lt;Propertyname&gt; &#39; &#39;t für alle Codepfade einen Wert zurück
Eigenschaft '\<Propertyname >' nicht für alle Codepfade einen Wert zurück. Wenn das Ergebnis verwendet wird, kann während der Laufzeit eine NULL-Verweisausnahme auftreten.  
  
 Eine Eigenschaft `Get` Prozedur verfügt über mindestens einen möglichen Pfad durch den Code, die keinen Wert zurückgibt.  
  
 Sie können einen Wert zurückgeben, aus einer Eigenschaft `Get` Prozedur in einer der folgenden Methoden:  
  
-   Weisen Sie den Wert an den Eigenschaftennamen an, und führen Sie dann eine `Exit Property` Anweisung.  
  
-   Weisen Sie den Wert an den Eigenschaftennamen an, und führen Sie dann die `End Get` Anweisung.  
  
-   Fügen Sie den Wert in eine [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Wenn die Steuerung an übergibt `Exit Property` oder `End Get` und einen beliebigen Wert an den Eigenschaftennamen nicht zugewiesene der `Get` Prozedur gibt den Standardwert des Datentyps der Eigenschaft zurück. Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42107  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, die bewirkt, eine Rückgabe dass.  
  
     Es ist einfacher, um sicherzustellen, dass es sich bei jeder Beendigung der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung. Wenn Sie die letzte Anweisung vor so vorgehen `End Get` muss eine `Return` Anweisung.  
  
## <a name="see-also"></a>Siehe auch
- [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
