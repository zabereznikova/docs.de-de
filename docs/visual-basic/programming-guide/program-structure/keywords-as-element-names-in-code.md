---
title: Schlüsselwörter als Elementnamen in Code
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 4cdcda7c5c78481af1633bf29d75070c521ab393
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347390"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Schlüsselwörter als Elementnamen in Code (Visual Basic)
Jedes Programmelement – z. b. eine Variable, eine Klasse oder ein Member – kann denselben Namen wie ein eingeschränktes Schlüsselwort haben. Beispielsweise können Sie eine Variable mit dem Namen `Loop`erstellen. Wenn Sie jedoch auf Ihre Version des IT-– verweisen, das den gleichen Namen hat wie das Schlüsselwort restricted `Loop` – müssen Sie entweder eine vollständige Qualifikations Zeichenfolge voranstellen oder Sie in eckige Klammern (`[ ]`) einschließen, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 Wenn Sie keine dieser Aktionen ausführen, wird Visual Basic die Verwendung des intrinsischen `Loop` Schlüsselworts annimmt und einen Fehler erzeugt, wie im folgenden Beispiel gezeigt:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Sie können eckige Klammern verwenden, wenn Sie auf Formulare und Steuerelemente verweisen, und wenn Sie eine Variable deklarieren oder eine Prozedur mit demselben Namen wie ein eingeschränktes Schlüsselwort definieren. Es kann leicht vergessen werden, Namen zu qualifizieren oder eckige Klammern einzuschließen. auf diese Weise können Sie Fehler in Ihren Code einbringen und das Lesen erschweren. Aus diesem Grund wird empfohlen, dass Sie keine eingeschränkten Schlüsselwörter als Namen von Programmelementen verwenden. Wenn eine zukünftige Version von Visual Basic jedoch ein neues Schlüsselwort definiert, das mit einem vorhandenen Formular-oder Steuerelement Namen in Konflikt steht, können Sie dieses Verfahren verwenden, wenn Sie Ihren Code aktualisieren, um mit der neuen Version zu arbeiten.  
  
> [!NOTE]
> Ihr Programm kann auch Elementnamen enthalten, die von anderen referenzierten Assemblys bereitgestellt werden Wenn diese Namen mit eingeschränkten Schlüsselwörtern in Konflikt stehen, bewirkt das Platzieren von eckigen Klammern, Visual Basic Sie als die definierten Elemente interpretiert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Benennungs Konventionen für Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
