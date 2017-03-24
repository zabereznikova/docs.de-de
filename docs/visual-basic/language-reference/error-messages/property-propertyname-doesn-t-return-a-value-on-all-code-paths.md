---
title: "Eigenschaft &quot;&lt;Propertyname&gt;&quot; nicht für alle Codepfade einen Wert zurück | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
dev_langs:
- VB
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
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
ms.openlocfilehash: e7c94d827761ad26d517b44a06734c5db4480a62
ms.lasthandoff: 03/13/2017

---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Eigenschaft '&lt;Propertyname&gt;' nicht für alle Codepfade einen Wert zurück
Eigenschaft '\<Propertyname >' nicht für alle Codepfade einen Wert zurück. Wenn das Ergebnis verwendet wird, kann während der Laufzeit eine NULL-Verweisausnahme auftreten.  
  
 Eine Eigenschaft `Get` Prozedur verfügt über mindestens einen möglichen Codepfad auf, die keinen Wert zurückgibt.  
  
 Sie können einen Wert zurückgeben, von einer Eigenschaft `Get` Verfahren in den folgenden Methoden:  
  
-   Weisen Sie den Wert auf den Eigenschaftennamen, und führen Sie dann eine `Exit Property` Anweisung.  
  
-   Weisen Sie den Wert auf den Eigenschaftennamen, und führen Sie dann die `End Get` Anweisung.  
  
-   Fügen Sie den Wert in einem [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Wenn die Steuerung an `Exit Property` oder `End Get` und Sie den Namen der Eigenschaft einen Wert zugewiesen haben die `Get` Prozedur gibt den Standardwert des Datentyps der Eigenschaft zurück. Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zu Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42107  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie die Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, der eine Rückgabe verursacht.  
  
     Es ist einfacher sicherstellen, dass bei jeder Beendigung der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung. Wenn Sie die letzte Anweisung vor dazu `End Get` sollte eine `Return` Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 [Property-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
