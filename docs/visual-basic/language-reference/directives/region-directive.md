---
title: '#<a name="region-directive"></a>Region-Direktive'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb308da6ad0ca6243f14e0d825ed7eb005d622bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="region-directive"></a>#Region-Anweisung
Reduziert Codeabschnitte in Visual Basic-Dateien und blendet sie aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`identifier_string`|Erforderlich. Eine Zeichenfolge, die als Bereichtitel fungiert, wenn sie reduziert ist. Bereiche werden standardmäßig reduziert.|  
|`#End Region`|Beendet den `#Region`-Block.|  
  
## <a name="remarks"></a>Hinweise  
 Mit der `#Region`-Direktive können Sie einen Codeblock festlegen, der bei Verwendung der Gliederungsfunktion des Code-Editors von Visual Studio erweitert oder reduziert werden soll. Sie können platzieren, oder *schachteln*, innerhalb von anderen Bereichen, damit ähnliche Bereiche zusammen gruppiert.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `#Region`-Direktive.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Gliedern](/visualstudio/ide/outlining)  
 [Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
