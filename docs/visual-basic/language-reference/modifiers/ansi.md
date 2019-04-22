---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 98dafab3e524ea371bba228eb231e28d46cc3b4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819454"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Gibt an, dass es sich bei Visual Basic alle Zeichenfolgen in Werte American National Standards Institute (ANSI), unabhängig vom Namen des die deklarierte externe Prozedur marshallen soll.  
  
 Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die die Prozedur richtig aufrufen muss. Diese Informationen umfassen, in dem die Prozedur befindet, wie dieses ermittelt wird, die Aufrufsequenz und Rückgabetyp und die Zeichenfolge festgelegt wird. Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Die `charsetmodifier` -Teil in die `Declare` -Anweisung gibt die Informationen für das Marshalling von Zeichenfolgen bei einem Aufruf der externen Prozedur Zeichen. Es wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht. Die `Ansi` %(Dateiname) gibt an, dass Visual Basic alle Zeichenfolgen in ANSI-Werte marshallen und die Prozedur suchen soll, ohne seinen Namen bei der Suche zu ändern.  
  
 Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.  
  
## <a name="remarks"></a>Hinweise  
 Die `Ansi` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Hinweise für Entwickler intelligente Geräte  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
