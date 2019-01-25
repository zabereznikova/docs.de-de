---
title: '#Region-Anweisung (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: db8063cf06ad0735bb4d9290c60548f7ff9af217
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611942"
---
# <a name="region-directive"></a>#Region-Anweisung
Reduziert Codeabschnitte in Visual Basic-Dateien und blendet sie aus.  
  
## <a name="syntax"></a>Syntax  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`identifier_string`|Erforderlich. Eine Zeichenfolge, die als Bereichtitel fungiert, wenn sie reduziert ist. Bereiche werden standardmäßig reduziert.|  
|`#End Region`|Beendet den `#Region`-Block.|  
  
## <a name="remarks"></a>Hinweise  
 Mit der `#Region`-Direktive können Sie einen Codeblock festlegen, der bei Verwendung der Gliederungsfunktion des Code-Editors von Visual Studio erweitert oder reduziert werden soll. Sie können platzieren, oder *schachteln*, innerhalb von anderen Bereichen, die ähnliche Bereiche zusammen gruppiert.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `#Region`-Anweisung.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Gliedern](/visualstudio/ide/outlining)
- [Vorgehensweise: Reduzieren und Ausblenden von Codeabschnitten](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
