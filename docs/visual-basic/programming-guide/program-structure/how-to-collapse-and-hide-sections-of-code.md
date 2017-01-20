---
title: "How to: Collapse and Hide Sections of Code (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic, code collapsing"
  - "Visual Basic, code hiding"
  - "Visual Basic code, collapsing and hiding"
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Collapse and Hide Sections of Code (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit der `#Region`\-Direktive können Sie Codeabschnitte aus [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Dateien reduzieren und ausblenden.  Mit der `#Region`\-Direktive können Sie einen Codeblock angeben, den Sie erweitern oder reduzieren können, wenn Sie den Code\-Editor von [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] verwenden.  Durch die Möglichkeit, ausgewählte Codeabschnitte auszublenden, werden Dateien leichter lesbar und sind besser zu verwalten.  Weitere Informationen finden Sie unter [Gliedern](/visual-studio/ide/outlining).  
  
 `#Region`\-Direktiven unterstützen Codeblocksemantik, z. B. `#If...#End If`.  Dies bedeutet, dass sie nicht in einem Block beginnen und in einem anderen Block enden können. Beginn und Ende müssen im gleichen Block liegen.  `#Region`\-Direktiven werden in Funktionen nicht unterstützt.  
  
### So werden Codeabschnitte reduziert und ausgeblendet  
  
-   Fügen Sie den Codeabschnitt zwischen die `#Region`\-Anweisung und die `#End Region`\-Anweisung ein \(siehe folgendes Beispiel\):  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-se_1.vb)]  
  
     Der `#Region`\-Block kann in einer Codedatei mehrfach verwendet werden, d. h. Benutzer können eigene Prozeduren\- und Klassenblöcke definieren, die wiederum reduziert werden können.  `#Region`\-Blöcke können auch in anderen `#Region`\-Blöcken geschachtelt werden.  
  
    > [!NOTE]
    >  Durch das Ausblenden wird der betreffende Code nicht von der Kompilierung ausgeschlossen, und das Ausblenden hat keinen Einfluss auf `#If...#End If`\-Anweisungen.  
  
## Siehe auch  
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md)   
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Gliedern](/visual-studio/ide/outlining)