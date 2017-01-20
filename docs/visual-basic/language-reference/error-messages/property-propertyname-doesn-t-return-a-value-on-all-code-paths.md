---
title: "Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc42107"
  - "vbc42107"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42107"
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die \<Eigenschaftenname\>\-Eigenschaft gibt nicht für alle Codepfade einen Wert zurück.Wenn das Ergebnis verwendet wird, kann zur Laufzeit eine NULL\-Verweisausnahme auftreten  
  
 Eine `Get`\-Eigenschaftenprozedur weist mindestens einen möglichen Codepfad auf, der keinen Wert zurückgibt.  
  
 Mit einem der folgenden Verfahren kann ein Wert von einer `Get`\-Eigenschaftenprozedur zurückgegeben werden:  
  
-   Weisen Sie dem Eigenschaftennamen den Wert zu, und führen Sie dann eine `Exit Property`\-Anweisung aus.  
  
-   Weisen Sie dem Eigenschaftennamen den Wert zu, und führen Sie dann die `End Get`\-Anweisung aus.  
  
-   Fügen Sie den Wert in eine [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) ein.  
  
 Wenn die Steuerung an `Exit Property` oder an `End Get` übergeben wird und Sie dem Eigenschaftennamen keinen Wert zugewiesen haben, gibt die `Get`\-Prozedur den Standardwert für den Datentyp der Eigenschaft zurück.  Weitere Informationen finden Sie in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) unter "Verhalten".  
  
 Standardmäßig ist diese Meldung eine Warnung.  Weitere Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42107  
  
### So beheben Sie diesen Fehler  
  
-   Überprüfen Sie die Ablaufsteuerungslogik, und weisen Sie vor jeder Anweisung, die eine Rückgabe verursacht, einen Wert zu.  
  
     Wenn Sie immer die `Return`\-Anweisung verwenden, lässt sich einfacher sicherstellen, dass bei jeder Beendigung der Prozedur ein Wert zurückgegeben wird.  Bei dieser Vorgehensweise muss die letzte Anweisung vor `End Get` eine `Return`\-Anweisung sein.  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)