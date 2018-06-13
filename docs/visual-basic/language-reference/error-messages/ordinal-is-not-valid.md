---
title: Ungültiger Ordinalwert.
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 12d73b33e3c025b40c98d84e3507af7be1e1e91a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593602"
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
