---
title: "Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc42105"
  - "vbc42105"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42105"
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Die \<Prozedurname\>\-Funktion gibt nicht für alle Codepfade einen Wert zurück.Fehlt eine Return\-Anweisung?  
  
 Eine `Function`\-Prozedur weist mindestens einen möglichen Codepfad auf, der keinen Wert zurückgibt.  
  
 Mit einem der folgenden Verfahren kann ein Wert von einer `Function`\-Prozedur zurückgegeben werden:  
  
-   Fügen Sie den Wert in eine [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) ein.  
  
-   Weisen Sie dem Namen der `Function`\-Prozedur den Wert zu, und führen Sie dann eine `Exit Function`\-Anweisung aus.  
  
-   Weisen Sie dem Namen der `Function`\-Prozedur den Wert zu, und führen Sie dann die `End Function`\-Anweisung aus.  
  
 Wenn die Steuerung an `Exit Function` oder an `End Function` übergeben wird und Sie dem Prozedurnamen keinen Wert zugewiesen haben, gibt die Prozedur den Standardwert des Rückgabedatentyps zurück.  Weitere Informationen finden Sie in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) unter "Verhalten".  
  
 Standardmäßig ist diese Meldung eine Warnung.  Weitere Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42105  
  
### So beheben Sie diesen Fehler  
  
-   Überprüfen Sie die Ablaufsteuerungslogik, und weisen Sie vor jeder Anweisung, die eine Rückgabe verursacht, einen Wert zu.  
  
     Wenn Sie immer die `Return`\-Anweisung verwenden, lässt sich einfacher sicherstellen, dass bei jeder Beendigung der Prozedur ein Wert zurückgegeben wird.  Bei dieser Vorgehensweise muss die letzte Anweisung vor `End Function` eine `Return`\-Anweisung sein.  
  
## Siehe auch  
 [Function\-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)