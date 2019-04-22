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
ms.openlocfilehash: eaaf0f8279ec905767be3f364a88357f0d393bba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818871"
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
 Mit der `#Region`-Anweisung können Sie einen Codeblock festlegen, der bei Verwendung der Gliederungsfunktion des Code-Editors von Visual Studio erweitert oder reduziert werden soll. Sie können platzieren, oder *schachteln*, innerhalb von anderen Bereichen, die ähnliche Bereiche zusammen gruppiert.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `#Region`-Anweisung.  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Gliedern](/visualstudio/ide/outlining)
- [Vorgehensweise: Reduzieren und Ausblenden von Codeabschnitten](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
