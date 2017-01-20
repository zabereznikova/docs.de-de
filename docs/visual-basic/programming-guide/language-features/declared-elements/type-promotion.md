---
title: "Type Promotion (Visual Basic) | Microsoft Docs"
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
  - "declared elements, scope"
  - "visibility, declared elements"
  - "Partial keyword, unexpected results with type promotion"
  - "scope, declared elements"
  - "scope, Visual Basic"
  - "type promotion"
  - "declared elements, visibility"
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type Promotion (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn Sie in einem Modul ein Programmierelement deklarieren, wird dessen Gültigkeitsbereich von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] auf den Namespace erweitert, der das Modul enthält.  Dies wird als *Typerweiterung* bezeichnet.  
  
 Am folgenden Beispiel wird gezeigt, wie die Gerüstdefinition für ein Modul und zwei Member dieses Moduls erfolgt.  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 Innerhalb von `projModule` werden auf Modulebene deklarierte Programmierelemente auf `projNamespace` erweitert.  Im vorhergehenden Beispiel werden `basicEnum` und `innerClass` erweitert, `numberSub` dagegen nicht, da es auf Modulebene nicht deklariert ist.  
  
## Folgen der Typerweiterung  
 Aufgrund der Typerweiterung müssen Qualifikationspfade nicht den Modulnamen enthalten.  Im folgenden Beispiel wird die Prozedur aus dem obigen Beispiel zwei Mal aufgerufen.  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 Im vorhergehenden Beispiel werden im ersten Aufruf vollständige Qualifizierungspfade verwendet.  Dank der Typerweiterung ist dies jedoch nicht notwendig.  Im zweiten Aufruf erfolgt ebenfalls ein Zugriff auf die Member des Moduls, ohne dass `projModule` in die Qualifizierungspfade einbezogen wird.  
  
## Fehlschlagen der Typerweiterung  
 Wenn der Namespace bereits einen Member mit dem gleichen Namen als Modulmember enthält, ist eine Typerweiterung für den betreffenden Modulmember nicht möglich.  Im folgenden Beispiel wird gezeigt, wie die Gerüstdefinition für eine Enumeration und ein Modul innerhalb desselben Namespaces durchgeführt wird.  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 Im vorhergehenden Beispiel kann [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] die `abc`\-Klasse nicht auf `thisNameSpace` erweitern, da dort bereits eine Enumeration mit dem gleichen Namen auf Namespaceebene vorhanden ist.  Wenn Sie auf `abcSub` zugreifen möchten, müssen Sie den vollständigen Qualifizierungspfad `thisNamespace.thisModule.abc.abcSub` verwenden.  Die `xyz`\-Klasse wird jedoch erweitert, und Sie können über den kürzeren Qualifizierungspfad `thisNamespace.xyz.xyzSub` auf `xyzSub` zugreifen.  
  
### Fehlschlagen der Typerweiterung für partielle Typen  
 Wenn in einer Klasse oder in einer Struktur innerhalb eines Moduls das [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)\-Schlüsselwort verwendet wird, ist die Typerweiterung für die betreffende Klasse oder Struktur automatisch nicht mehr möglich. Dies gilt unabhängig davon, ob es im Namespace einen Member mit dem gleichen Namen gibt.  Andere Elemente im Modul sind dennoch weiterhin für die Typerweiterung geeignet.  
  
 **Folgen.** Das Fehlschlagen der Typerweiterung einer partiellen Definition kann unerwartete Ergebnisse und sogar Compilerfehler verursachen.  Im folgenden Beispiel werden partielle Gerüstdefinitionen einer Klasse dargestellt; eine dieser Definitionen befindet sich innerhalb eines Moduls.  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 Im vorhergehenden Beispiel erwartet der Entwickler möglicherweise, dass der Compiler die beiden partiellen Definitionen von `sampleClass` zusammenführt.  Der Compiler zieht jedoch keine Erweiterung der partiellen Definition in `sampleModule` in Betracht.  Daher versucht er, zwei separate Klassen zu kompilieren. Diese heißen zwar beide `sampleClass`, zeichnen sich aber durch unterschiedliche Qualifizierungspfade aus.  
  
 Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.  
  
## Empfehlungen  
 Die folgenden Empfehlungen erleichtern Ihnen Ihre Programmierarbeit.  
  
-   **Eindeutige Namen.** Wenn ausschließlich Sie die Benennung von Programmierelementen vornehmen, sollten Sie eindeutige Namen verwenden.  Identische Namen erfordern zusätzliche Qualifizierung und können das Lesen des Codes erschweren.  Darüber hinaus können sie zu schwierig zu entdeckenden Fehlern und unerwarteten Ergebnissen führen.  
  
-   **Volle Qualifizierung.** Wenn Sie mit Modulen und anderen Elementen im gleichen Namespace arbeiten, ist es am sichersten, alle Programmierelemente stets voll zu qualifizieren.  Wenn die Typerweiterung für einen Modulmember nicht möglich ist und Sie den betreffenden Member nicht voll qualifizieren, greifen Sie unter Umständen versehentlich auf ein anderes Programmierelement zu.  
  
## Siehe auch  
 [Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)