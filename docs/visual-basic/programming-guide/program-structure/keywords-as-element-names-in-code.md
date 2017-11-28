---
title: "Schlüsselwörter als Elementnamen in Code (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f410a0eaac0dcc034d406a89ed1d01a8f228a583
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Schlüsselwörter als Elementnamen in Code (Visual Basic)
Jedem Programmelement, z. B. eine Variable, eine Klasse oder ein Member – kann den gleichen Namen wie ein eingeschränktes Schlüsselwort haben. Sie können z. B. erstellen eine Variablen namens `Loop`. Allerdings zum Verweisen auf die Version zu – die hat des gleichen Namens wie die eingeschränkte `Loop` Schlüsselwort – müssen Sie ein vollständiger Qualifizierungspfad voran oder schließen Sie ihn in eckige Klammern (`[ ]`), wie das folgende Beispiel zeigt.  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 Wenn Sie nicht eine dieser Optionen, und klicken Sie dann Visual Basic davon aus, die systeminterne Funktion dass `Loop` Schlüsselwort und erzeugt einen Fehler, wie im folgenden Beispiel gezeigt:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Eckige Klammern können beim Verweisen auf Formularen und Steuerelementen und beim Deklarieren einer Variablen oder eine Prozedur mit dem gleichen Namen wie ein eingeschränktes Schlüsselwort definieren. Es kann leicht vergessen, qualifizieren Namen oder eckige Klammern einschließen und somit einführen von Fehlern in Ihren Code und schwieriger zu lesen sein. Aus diesem Grund wird empfohlen, dass Sie eingeschränkte Schlüsselwörter nicht als den Namen der Anwendung Elemente verwenden. Jedoch wenn eine zukünftige Version von Visual Basic einem neuen Schlüsselwort, steht in Konflikt mit vorhandenen Steuerelementnamen eines Formulars oder definiert, können klicken Sie dann diese Technik Sie beim Aktualisieren von Code mit der neuen Version funktioniert.  
  
> [!NOTE]
>  Das Programm kann auch Elementnamen, die von anderen Assemblys verwiesen wird bereitgestellt enthalten. Wenn diese Namen mit eingeschränkte Schlüsselwörter in Konflikt stehen, führt dazu, dass Platzieren von eckigen Klammern darum Visual Basic, um sie als Ihre definierten Elemente interpretiert werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
