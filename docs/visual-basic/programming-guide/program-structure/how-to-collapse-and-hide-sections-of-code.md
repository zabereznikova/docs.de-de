---
title: 'Gewusst wie: reduzieren und Ausblenden von Codeabschnitten (Visual Basic) | Microsoft-Dokumentation'
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
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
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
ms.openlocfilehash: 200a90b6983277d46b6e5c7b27ee4a90ecf88c40
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)
Die `#Region` Richtlinie ermöglicht es Ihnen, reduzieren und Ausblenden von Codeabschnitten im [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien. Die `#Region` -Direktive können Sie einen Codeblock, den Sie erweitern können oder reduzieren angeben, bei Verwendung der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Code-Editor. Die Möglichkeit, ausgewählte Codeabschnitte auszublenden macht Ihre Dateien verwaltet werden und sind einfacher zu lesen. Weitere Informationen finden Sie unter [Gliederung](https://docs.microsoft.com/visualstudio/ide/outlining).  
  
 `#Region`Direktiven unterstützen Codesemantik Block, wie z. B. `#If...#End If`. Das heißt, sie können nicht in einem Block beginnen und enden in einer anderen. Anfang und Ende müssen im selben Block sein. `#Region`-Direktiven werden in Funktionen nicht unterstützt.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Reduzieren und Ausblenden eines Abschnitts des Codes  
  
-   Platzieren Sie den Codeabschnitt zwischen die `#Region` und `#End Region` -Anweisungen, wie im folgenden Beispiel:  
  
     [!code-vb[VbVbalrConditionalComp&6;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     Die `#Region` Block kann mehrmals in einer Codedatei verwendet werden, daher können Benutzer ihre eigenen Blöcke von Prozeduren und Klassen, die wiederum reduziert werden können, definieren. `#Region`Blöcke können auch geschachtelt werden, in den anderen `#Region` blockiert.  
  
    > [!NOTE]
    >  Ausblenden von Code verhindert nicht, dass er kompiliert und hat keinen Einfluss auf `#If...#End If` Anweisungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [#Region-Direktive](../../../visual-basic/language-reference/directives/region-directive.md)   
 [#If... Then... #Else-Direktive](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Gliedern](https://docs.microsoft.com/visualstudio/ide/outlining)
