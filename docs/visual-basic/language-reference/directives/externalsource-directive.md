---
title: '#ExternalSource-Anweisung'
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
ms.openlocfilehash: fa0a40827c1b3865b90c7d796ea4dd364774e1c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343832"
---
# <a name="externalsource-directive"></a>#ExternalSource-Anweisung

Gibt eine Zuordnung zwischen bestimmten Quell Codezeilen und Text außerhalb der Quelle an.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>-Komponenten  

 `StringLiteral`  
 Der Pfad zur externen Quelle.  
  
 `IntLiteral`  
 Die Zeilennummer der ersten Zeile der externen Quelle.  
  
 `LogicalLine`  
 Die Zeile, in der der Fehler in der externen Quelle auftritt.  
  
 `#End ExternalSource`  
 Beendet den `#ExternalSource`-Block.  
  
## <a name="remarks"></a>Hinweise  

 Diese Direktive wird nur vom Compiler und vom Debugger verwendet.  
  
 Eine Quelldatei kann externe Quell Direktiven enthalten, die eine Zuordnung zwischen bestimmten Codezeilen in der Quelldatei und Text außerhalb der Quelle, z. b. einer ASPX-Datei, angeben. Wenn während der Kompilierung Fehler im vorgesehenen Quellcode auftreten, werden Sie als aus der externen Quelle stammende identifiziert.  
  
 Externe Quell Direktiven haben keine Auswirkung auf die Kompilierung und können nicht eingebettet werden. Sie sind nur für die interne Verwendung durch die Anwendung vorgesehen.  
  
## <a name="see-also"></a>Siehe auch

- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
