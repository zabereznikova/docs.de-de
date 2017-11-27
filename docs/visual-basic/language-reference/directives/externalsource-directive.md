---
title: '#<a name="externalsource-directive"></a>ExternalSource-Direktive'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "160"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f90b838e50b65b8652cd9cf6f6ee084e9552f025
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="externalsource-directive"></a>#ExternalSource-Anweisung
Gibt eine Zuordnung zwischen bestimmten Quellcodezeilen und Text für die Quelle extern an.  
  
## <a name="syntax"></a>Syntax  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Teile  
 `StringLiteral`  
 Der Pfad mit der externen Datenquelle.  
  
 `IntLiteral`  
 Die Zeilennummer der ersten Zeile der externen Quelle.  
  
 `LogicalLine`  
 Die Zeile, in dem der Fehler in der externen Quelle auf.  
  
 `#End ExternalSource`  
 Beendet den `#ExternalSource`-Block.  
  
## <a name="remarks"></a>Hinweise  
 Diese Richtlinie wird nur durch den Compiler und der Debugger verwendet.  
  
 Eine Quelldatei eventuell Direktiven für den externen Code, die was darauf hindeuten, eine Zuordnung zwischen bestimmten Codezeilen in der Quelldatei und Text außerhalb der Quelle, z. B. eine ASPX-Datei dass. Wenn Fehler in den angegebenen Quellcode während der Kompilierung festgestellt werden, werden sie identifiziert als aus der externen Quelle stammen.  
  
 Die externe Quelle Direktiven haben keine Auswirkungen auf die Kompilierung und können nicht geschachtelt werden. Sie werden von der Anwendung nur für die interne Verwendung gedacht.  
  
## <a name="see-also"></a>Siehe auch  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
