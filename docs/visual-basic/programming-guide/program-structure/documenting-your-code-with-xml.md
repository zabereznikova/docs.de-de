---
title: Dokumentieren von Code mit XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 6b9fe9994b7bdf2259dcdb1ecef906e0f9955c8f
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480624"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Dokumentieren von Code mit XML (Visual Basic)

In Visual Basic können Sie den Code mit XML dokumentieren.

## <a name="xml-documentation-comments"></a>XML-Dokumentationskommentare

Visual Basic bietet eine einfache Möglichkeit zum automatischen Erstellen von XML-Dokumentation für Projekte. Sie können eine XML-Grundgerüst für die verwendeten Typen und Member automatisch zu generieren und geben Sie dann für jeden Parameter und andere Hinweise Zusammenfassungen, aussagekräftigen-Dokumentation. Die XML-Dokumentation wird automatisch in eine XML-Datei mit dem gleichen Namen wie das Projekt und der Erweiterung .xml ausgegeben, bei der entsprechenden Einrichtung. Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).

Die XML-Datei kann verbraucht oder im XML-Format bearbeitet werden. Diese Datei befindet sich im gleichen Verzeichnis wie die Ausgabe .exe oder .dll-Datei des Projekts.

XML-Dokumentation beginnt mit `'''`. Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:

- Die Dokumentation muss wohlgeformtes XML sein. Wenn der XML-Code nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.

- Entwickler können ihren eigenen Satz von Tags erstellen. Es gibt ein Reihe empfohlener Tags (finden Sie in diesem Thema unter "Verwandte Abschnitte"). Einige der empfohlenen Tags haben eine besondere Bedeutung:

  - Das \<param>-Tag wird verwendet, um Parameter zu beschreiben. Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.

  - Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen. Der Compiler überprüft, ob dieses Codeelement vorhanden ist. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus. Der Compiler berücksichtigt außerdem alle `Imports` Anweisungen, die bei der Suche für einen Typ beschrieben, die der `cref` Attribut.

  - Die \<summary >-Tag wird von IntelliSense in Visual Studio verwendet, um weitere Informationen über einen Typ oder Member anzuzeigen.

## <a name="related-sections"></a>Verwandte Abschnitte

Ausführliche Informationen zum Erstellen einer XML-Datei mit Dokumentationskommentaren finden Sie unter den folgenden Themen:

- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)

- [Verarbeiten der XML-Datei](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [Vorgehensweise: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [XML-Tools in Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>Siehe auch

- [Entwickeln von Anwendungen mit Visual Basic](../../../visual-basic/developing-apps/index.md)
- [Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md)
