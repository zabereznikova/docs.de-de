---
title: 'Gewusst wie: Erstellen einer XML-Dokumentation'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 41b7ef1f435fd0a4f20c4ca2936e2d91e155f7c5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347424"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic

Dieses Beispiel zeigt, wie Sie Ihrem Code XML-Dokumentations Kommentare hinzufügen.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a>So erstellen Sie eine XML-Dokumentation für einen Typ oder Member

1. Positionieren Sie den Cursor im **Code-Editor**in der Zeile oberhalb des Typs oder Members, für den Sie eine Dokumentation erstellen möchten.

2. Geben Sie `'''` (drei einfache Anführungszeichen) ein.

    Ein XML-Gerüst für den Typ oder Member wird im **Code-Editor**hinzugefügt.

3. Fügen Sie beschreibende Informationen zwischen den entsprechenden Tags hinzu.

    > [!NOTE]
    > Wenn Sie im XML-Dokumentationsblock weitere Zeilen hinzufügen, muss jede Zeile mit `'''`beginnen.

4. Fügen Sie zusätzlichen Code hinzu, der den Typ oder Member mit den neuen XML-Dokumentations Kommentaren verwendet.

    IntelliSense zeigt den Text aus der \<Zusammenfassungs >-Tags für den Typ oder Member an.

5. Kompilieren Sie den Code, um eine XML-Datei zu generieren, die die Dokumentations Kommentare enthält. Weitere Informationen finden Sie unter [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).

## <a name="see-also"></a>Siehe auch

- [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)
