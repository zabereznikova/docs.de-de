---
title: '#ExternalSource-Anweisung (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: dcde8507eb033d0a47d5c5d3fa36176cd63b0856
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556317"
---
# <a name="externalsource-directive"></a>#ExternalSource-Anweisung
Gibt eine Zuordnung zwischen bestimmten Codezeilen an Quelle und dem Text für die Quelle extern an.  
  
## <a name="syntax"></a>Syntax  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Teile  
 `StringLiteral`  
 Der Pfad zu der externen Datenquelle.  
  
 `IntLiteral`  
 Die Nummer der Zeile der ersten Zeile der externen Quelle.  
  
 `LogicalLine`  
 Die Zeile, in dem sich der Fehler in der externen Datenquelle auf.  
  
 `#End ExternalSource`  
 Beendet den `#ExternalSource`-Block.  
  
## <a name="remarks"></a>Hinweise  
 Diese Richtlinie wird nur durch den Compiler und der Debugger verwendet werden.  
  
 Eine Quelldatei kann Direktiven für externe Quellen enthalten, die eine Zuordnung zwischen bestimmten Codezeilen in der Quelldatei zu externem Text an der Quelle, z. B. eine ASPX-Datei angeben. Wenn Fehler in den angegebenen Quellcode während der Kompilierung auftreten, werden sie identifiziert, da Sie von der externen Quelle stammen.  
  
 Externe quelldirektiven haben keine Auswirkungen auf die Kompilierung und können nicht geschachtelt werden. Sie sind von der Anwendung nur für die interne Verwendung vorgesehen.  
  
## <a name="see-also"></a>Siehe auch  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
