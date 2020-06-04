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
ms.openlocfilehash: e4c7704c32c3a6c73e069d0b7129d5386696b438
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402991"
---
# <a name="externalsource-directive"></a>#ExternalSource-Anweisung

Gibt eine Zuordnung zwischen bestimmten Quell Codezeilen und Text außerhalb der Quelle an.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Bestandteile  

 `StringLiteral`  
 Der Pfad zur externen Quelle.  
  
 `IntLiteral`  
 Die Zeilennummer der ersten Zeile der externen Quelle.  
  
 `LogicalLine`  
 Die Zeile, in der der Fehler in der externen Quelle auftritt.  
  
 `#End ExternalSource`  
 Beendet den `#ExternalSource`-Block.  
  
## <a name="remarks"></a>Bemerkungen  

 Diese Direktive wird nur vom Compiler und vom Debugger verwendet.  
  
 Eine Quelldatei kann externe Quell Direktiven enthalten, die eine Zuordnung zwischen bestimmten Codezeilen in der Quelldatei und Text außerhalb der Quelle, z. b. einer ASPX-Datei, angeben. Wenn während der Kompilierung Fehler im vorgesehenen Quellcode auftreten, werden Sie als aus der externen Quelle stammende identifiziert.  
  
 Externe Quell Direktiven haben keine Auswirkung auf die Kompilierung und können nicht eingebettet werden. Sie sind nur für die interne Verwendung durch die Anwendung vorgesehen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Bedingte Kompilierung](../../programming-guide/program-structure/conditional-compilation.md)
