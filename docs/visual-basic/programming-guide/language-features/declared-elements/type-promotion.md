---
title: Geben Sie Promotion (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, scope
- visibility, declared elements
- Partial keyword, unexpected results with type promotion
- scope, declared elements
- scope, Visual Basic
- type promotion
- declared elements, visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: d732e765fc28eaedc0deab477dbf9955a40e97c9
ms.lasthandoff: 03/13/2017

---
# <a name="type-promotion-visual-basic"></a>Typerweiterung (Visual Basic)
Wenn Sie in einem Modul ein Programmierelement deklarieren [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] stuft den Gültigkeitsbereich auf den Namespace, der das Modul enthält. Dies wird als bezeichnet *geben Promotion*.  
  
 Das folgende Beispiel zeigt eine Skelett Definition eines Moduls und zwei Member dieses Moduls.  
  
 [!code-vb[VbVbalrDeclaredElements&#1;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 In `projModule`Programmierelemente auf Modulebene deklarierte Elemente zu hochgestuft werden `projNamespace`. Im vorangehenden Beispiel `basicEnum` und `innerClass` höher gestuft werden, aber `numberSub` dagegen nicht, da es auf Modulebene nicht deklariert ist.  
  
## <a name="effect-of-type-promotion"></a>Auswirkung der Heraufstufen von Typen  
 Heraufstufen von Typen wird ein Qualifizierungspfad müssen nicht den Namen des Moduls enthalten. Das folgende Beispiel enthält zwei Aufrufe an die Prozedur im vorhergehenden Beispiel.  
  
 [!code-vb[VbVbalrDeclaredElements&#2;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 Im vorherigen Beispiel verwendet der erste Aufruf vollständige Qualifizierung Zeichenfolgen. Dies ist jedoch nicht notwendig aufgrund heraufstufen. Die zweite Aufruf erfolgt ebenfalls die Member des Moduls, ohne `projModule` in die Qualifikation-Zeichenfolgen.  
  
## <a name="defeat-of-type-promotion"></a>Entschärfen von Heraufstufen von Typen  
 Wenn der Namespace bereits einen Member mit dem gleichen Namen wie einen Modulmember verfügt, erfolgt Heraufstufen von Typen für dieses Modul-Element. Das folgende Beispiel zeigt eine Skelette Definition für eine Enumeration und ein Modul innerhalb desselben Namespaces.  
  
 [!code-vb[VbVbalrDeclaredElements&3;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 Im vorangehenden Beispiel [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kann nicht höher gestuft Klasse `abc` zu `thisNameSpace` da bereits eine Enumeration mit dem gleichen Namen auf Namespaceebene vorhanden ist. Für den Zugriff auf `abcSub`, müssen Sie den vollständigen Qualifizierungspfad verwenden `thisNamespace.thisModule.abc.abcSub`. -Klasse `xyz` wird jedoch erweitert, und Sie können den `xyzSub` mit den kürzeren Qualifizierungspfad `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Entschärfen von Heraufstufen von Typen für partielle Typen  
 Wenn eine Klasse oder Struktur innerhalb eines Moduls verwendet die [teilweise](../../../../visual-basic/language-reference/modifiers/partial.md) -Schlüsselwort, Heraufstufen von Typen ist automatisch für diese Klasse oder Struktur, außer Kraft gesetzt, und zwar unabhängig davon, ob der Namespace einen Member mit dem gleichen Namen hat. Andere Elemente im Modul kommen noch für heraufstufen.  
  
 **Folgen.** Entschärfen von Heraufstufen einer partiellen Definition kann unerwartete Ergebnisse und sogar zu Compilerfehlern führen. Im folgenden Beispiel wird das Skelett partielle Definitionen einer Klasse, von denen innerhalb eines Moduls ist.  
  
 [!code-vb[VbVbalrDeclaredElements&4;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 Im vorangehenden Beispiel erwarten Entwickler den Compiler die beiden partiellen Definitionen von merge `sampleClass`. Der Compiler berücksichtigt jedoch keine Erweiterung der partiellen Definition in `sampleModule`. Daher versucht er, zwei separate Klassen zu kompilieren, mit dem Namen `sampleClass` jedoch mit verschiedenen Qualifizierung Pfade.  
  
 Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.  
  
## <a name="recommendations"></a>Empfehlungen  
 Die folgenden Aspekte stellen guten Programmierpraxis dar.  
  
-   **Eindeutige Namen.** Wenn Sie vollständige Kontrolle über die Benennung von Programmierelementen verfügen, ist es immer eine gute Idee, eindeutige Namen verwenden. Identische Namen können erfordern zusätzliche Qualifizierung und Ihren Code schwieriger zu lesen. Sie können auch Fehler auftreten und unerwarteten Ergebnissen führen.  
  
-   **Vollständige Qualifizierung.** Wenn Sie mit Modulen und anderen Elementen im gleichen Namespace arbeiten, ist am sichersten immer vollständige Qualifizierung für alle Programmierelemente verwenden. Wenn Heraufstufen von Typen für einen Modulmember erfolgt und Sie diesen Member nicht vollständig qualifizieren, konnten Sie versehentlich einen anderen Programmierelement zugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [Module-Anweisung](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Teilweise](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)   
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
