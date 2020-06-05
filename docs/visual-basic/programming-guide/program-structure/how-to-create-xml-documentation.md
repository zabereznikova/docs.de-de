---
title: 'Vorgehensweise: Erstellen einer XML-Dokumentation'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 1421cc85beba42b3cf3656c34b1d02347fbaf164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403238"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic

Dieses Beispiel zeigt, wie Sie Ihrem Code XML-Dokumentations Kommentare hinzufügen.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a>So erstellen Sie eine XML-Dokumentation für einen Typ oder Member

1. Positionieren Sie den Cursor im **Code-Editor**in der Zeile oberhalb des Typs oder Members, für den Sie eine Dokumentation erstellen möchten.

2. Type `'''` (drei einfache Anführungszeichen).

    Ein XML-Gerüst für den Typ oder Member wird im **Code-Editor**hinzugefügt.

3. Fügen Sie beschreibende Informationen zwischen den entsprechenden Tags hinzu.

    > [!NOTE]
    > Wenn Sie im XML-Dokumentationsblock weitere Zeilen hinzufügen, muss jede Zeile mit beginnen `'''` .

4. Fügen Sie zusätzlichen Code hinzu, der den Typ oder Member mit den neuen XML-Dokumentations Kommentaren verwendet.

    IntelliSense zeigt den Text aus dem- \<summary> Tag für den Typ oder Member an.

5. Kompilieren Sie den Code, um eine XML-Datei zu generieren, die die Dokumentations Kommentare enthält. Weitere Informationen finden Sie unter [-doc](../../reference/command-line-compiler/doc.md).

## <a name="see-also"></a>Siehe auch

- [Dokumentieren von Code mit XML](documenting-your-code-with-xml.md)
- [XML-Kommentartags](../../language-reference/xmldoc/index.md)
- [-doc](../../reference/command-line-compiler/doc.md)
