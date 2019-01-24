---
title: Ungültiger Ordinalwert.
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 351b7ee7f1cfc5199d878c33965770693227ccc4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618960"
---
# <a name="ordinal-is-not-valid"></a>Ungültiger Ordinalwert.
Beim Aufruf einer Dynamic Link Library (DLL) wurde angegeben, eine Anzahl anstelle einer Prozedur verwendet mit dem `#num` Syntax. Dieser Fehler hat die folgenden möglichen Ursachen:  
  
-   Ein Versuch, konvertieren die `#num` Ausdruck, der eine Ordnungszahl ist fehlgeschlagen.  
  
-   Die `#num` angegebenen gibt keine Funktion in der DLL.  
  
-   Eine Typbibliothek weist eine ungültige Deklaration, die interne Verwendung des eine ungültige Ordinalzahl zu.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Ausdruck eine gültige Zahl darstellt, oder rufen Sie die Prozedur nach Namen.  
  
2.  Stellen Sie sicher, dass `#num` identifiziert eine gültige Funktion in der DLL.  
  
3.  Isolieren Sie den Aufruf der Prozedur das Problem verursachen, durch den Code auskommentieren. Schreiben einer `Declare` -Anweisung für die Prozedur, und klicken Sie auf Bericht des Problems an den Hersteller der Bibliothek weiter.  
  
## <a name="see-also"></a>Siehe auch
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
