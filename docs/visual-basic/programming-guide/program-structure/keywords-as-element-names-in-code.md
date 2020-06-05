---
title: Schlüsselwörter als Elementnamen in Code
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: a98f0b027700717b414d58e1284ddec655eb25f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403225"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Schlüsselwörter als Elementnamen in Code (Visual Basic)
Jedes Programmelement – z. b. eine Variable, eine Klasse oder ein Member – kann denselben Namen wie ein eingeschränktes Schlüsselwort haben. Beispielsweise können Sie eine Variable mit dem Namen erstellen `Loop` . Um jedoch auf Ihre Version des IT-– mit dem gleichen Namen wie das Schlüsselwort "Restricted" zu verweisen `Loop` – müssen Sie entweder eine vollständige Qualifikations Zeichenfolge voranstellen oder Sie in eckige Klammern ( `[ ]` ) einschließen, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 Wenn Sie keine dieser Aktionen ausführen, wird Visual Basic die Verwendung des systeminternen `Loop` Schlüssel Worts annimmt und einen Fehler erzeugt, wie im folgenden Beispiel gezeigt:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Sie können eckige Klammern verwenden, wenn Sie auf Formulare und Steuerelemente verweisen, und wenn Sie eine Variable deklarieren oder eine Prozedur mit demselben Namen wie ein eingeschränktes Schlüsselwort definieren. Es kann leicht vergessen werden, Namen zu qualifizieren oder eckige Klammern einzuschließen. auf diese Weise können Sie Fehler in Ihren Code einbringen und das Lesen erschweren. Aus diesem Grund wird empfohlen, dass Sie keine eingeschränkten Schlüsselwörter als Namen von Programmelementen verwenden. Wenn eine zukünftige Version von Visual Basic jedoch ein neues Schlüsselwort definiert, das mit einem vorhandenen Formular-oder Steuerelement Namen in Konflikt steht, können Sie dieses Verfahren verwenden, wenn Sie Ihren Code aktualisieren, um mit der neuen Version zu arbeiten.  
  
> [!NOTE]
> Ihr Programm kann auch Elementnamen enthalten, die von anderen referenzierten Assemblys bereitgestellt werden Wenn diese Namen mit eingeschränkten Schlüsselwörtern in Konflikt stehen, bewirkt das Platzieren von eckigen Klammern, Visual Basic Sie als die definierten Elemente interpretiert werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Benennungskonventionen in Visual Basic](naming-conventions.md)
- [Programmstruktur und Codekonventionen](program-structure-and-code-conventions.md)
- [Schlüsselwörter](../../language-reference/keywords/index.md)
