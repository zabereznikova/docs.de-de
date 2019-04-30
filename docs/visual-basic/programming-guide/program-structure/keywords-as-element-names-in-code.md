---
title: Schlüsselwörter als Elementnamen in Code (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: c247ada67f6554362f287cf252dd49856c4995da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955583"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Schlüsselwörter als Elementnamen in Code (Visual Basic)
Jedem Programmelement, z. B. eine Variable, eine Klasse oder ein Member, haben den gleichen Namen wie ein eingeschränktes Schlüsselwort. Sie können z. B. erstellen eine Variablen namens `Loop`. Allerdings zum Verweisen auf Ihre Version des Zertifikats – das hat des gleichen Namens wie die eingeschränkte `Loop` Schlüsselwort – müssen Sie ein vollständiger Qualifizierungspfad voranstellen oder schließen Sie ihn in eckige Klammern (`[ ]`), wie im folgende Beispiel gezeigt.  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 Wenn Sie nicht tun, eines dieser, Visual Basic wird für die systeminterne Funktion `Loop` Schlüsselwort und erzeugt einen Fehler, wie im folgenden Beispiel gezeigt:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Eckige Klammern können beim Verweisen auf die Formulare und Steuerelemente, und wenn eine Variable deklarieren oder definieren eine Prozedur mit dem gleichen Namen wie ein eingeschränktes Schlüsselwort. Es kann leicht vergessen, qualifizierte Namen oder eckige Klammern einschließen und daher Fehler in Ihren Code einführen und machen es schwieriger zu lesen sein. Aus diesem Grund empfehlen wir, dass Sie eingeschränkte Schlüsselwörter nicht als die Namen der Programmelemente verwenden. Allerdings eine zukünftige Version von Visual Basic einem neuen Schlüsselwort, verursacht einen Konflikt mit vorhandenen Steuerelementnamen eines Formulars oder definiert, können klicken Sie dann dieses Verfahren Sie beim Aktualisieren von Code mit der neuen Version funktioniert.  
  
> [!NOTE]
>  Das Programm kann auch Elementnamen bereitgestellt, die von anderen referenzierten Assemblys enthalten. Diese Namen mit beschränkter Schlüsselwörter in Konflikt stehen, bewirkt, dass dann platzieren eckige Klammern sie Visual Basic, um sie als die definierte Elemente interpretiert werden soll.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
