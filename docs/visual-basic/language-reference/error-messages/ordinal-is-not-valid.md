---
title: "Ungültiger Ordinalwert."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d31d0fba19cc16004c0b56786af30603d0c509ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ordinal-is-not-valid"></a>Ungültiger Ordinalwert.
Rufen Sie eine Dynamic Link Library (DLL) angegeben wird, eine Zahl statt einem Prozedurnamen verwenden mithilfe der `#num` Syntax. Dieser Fehler hat die folgenden möglichen Ursachen:  
  
-   Ein Versuch, konvertieren die `#num` Ausdruck, der eine Ordinalzahl ist fehlgeschlagen.  
  
-   Die `#num` angegebenen gibt keine Funktion in der DLL.  
  
-   Eine Typbibliothek weist eine ungültige Deklaration in die interne Verwendung des eine ungültige Ordinalzahl.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Ausdruck eine gültige Zahl darstellt, oder rufen Sie die Prozedur nach Namen.  
  
2.  Stellen Sie sicher, dass `#num` identifiziert eine gültige Funktion in der DLL.  
  
3.  Isolieren Sie den Aufruf der Prozedur das Problem verursacht, indem Sie den Code auskommentieren. Schreiben einer `Declare` -Anweisung für die Prozedur, und klicken Sie auf Bericht des Problems an den Hersteller der Typbibliothek weiter.  
  
## <a name="see-also"></a>Siehe auch  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
