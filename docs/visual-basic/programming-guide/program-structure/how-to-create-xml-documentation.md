---
title: 'Vorgehensweise: Erstellen einer XML-Dokumentation in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: ff93a7bb2d8fdef68fc956d4c569ca5ad37afb2c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054102"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Vorgehensweise: Erstellen einer XML-Dokumentation in Visual Basic

Dieses Beispiel zeigt, wie Sie Ihrem Code XML-Dokumentations Kommentare hinzufügen.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a>So erstellen Sie eine XML-Dokumentation für einen Typ oder Member

1. Positionieren Sie den Cursor im **Code-Editor**in der Zeile oberhalb des Typs oder Members, für den Sie eine Dokumentation erstellen möchten.

2. Type `'''` (drei einfache Anführungszeichen).

    Ein XML-Gerüst für den Typ oder Member wird im **Code-Editor**hinzugefügt.

3. Fügen Sie beschreibende Informationen zwischen den entsprechenden Tags hinzu.

    > [!NOTE]
    > Wenn Sie im XML-Dokumentationsblock weitere Zeilen hinzufügen, muss jede Zeile mit `'''`beginnen.

4. Fügen Sie zusätzlichen Code hinzu, der den Typ oder Member mit den neuen XML-Dokumentations Kommentaren verwendet.

    IntelliSense zeigt den Text aus dem \<Zusammenfassungs >-Tag für den Typ oder Member an.

5. Kompilieren Sie den Code, um eine XML-Datei zu generieren, die die Dokumentations Kommentare enthält. Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).

## <a name="see-also"></a>Siehe auch

- [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
