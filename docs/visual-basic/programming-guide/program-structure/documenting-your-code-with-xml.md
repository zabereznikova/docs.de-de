---
title: Dokumentieren von Code mit XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: f391fb909cfe4de8f27afb24d6db389e2c8cdfae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590928"
---
# <a name="document-your-code-with-xml-visual-basic"></a>Dokumentieren Sie Ihren Code mit XML (Visual Basic)

In Visual Basic können Sie Ihren Code mit XML dokumentieren.

## <a name="xml-documentation-comments"></a>XML-Dokumentationskommentare

Visual Basic bietet eine einfache Möglichkeit, automatisch eine XML-Dokumentation für-Projekte zu erstellen. Sie können automatisch ein XML-Gerüst für Ihre Typen und Member generieren und dann Zusammenfassungen, eine beschreibende Dokumentation für jeden Parameter und andere Hinweise bereitstellen. Beim entsprechenden Setup wird die XML-Dokumentation automatisch in eine XML-Datei mit dem gleichen Stamm Dateinamen wie das Projekt ausgegeben. Weitere Informationen finden Sie unter [-doc](../../reference/command-line-compiler/doc.md).

Die XML-Datei kann als XML-Datei verwendet oder anderweitig manipuliert werden. Diese Datei befindet sich im gleichen Verzeichnis wie die EXE-Ausgabedatei oder die DLL-Datei Ihres Projekts.

Die XML-Dokumentation beginnt mit `'''` . Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:

- Die Dokumentation muss wohlgeformtes XML sein. Wenn die XML-Datei nicht wohl geformt ist, wird eine Warnung generiert, und die Dokumentations Datei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.

- Entwickler können ihren eigenen Satz von Tags erstellen. Es gibt einen empfohlenen Satz von Tags (siehe [XML-Kommentar Tags](../../language-reference/xmldoc/index.md)). Einige der empfohlenen Tags haben eine besondere Bedeutung:

  - Das- \<param> Tag wird verwendet, um Parameter zu beschreiben. Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.

  - Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen. Der Compiler überprüft, ob dieses Codeelement vorhanden ist. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus. Der Compiler respektiert auch alle-Anweisungen, wenn er nach `Imports` einem Typ sucht, der im-Attribut beschrieben wird `cref` .

  - Das- \<summary> Tag wird von IntelliSense in Visual Studio verwendet, um zusätzliche Informationen zu einem Typ oder Member anzuzeigen.

## <a name="related-sections"></a>Verwandte Abschnitte

Ausführliche Informationen zum Erstellen einer XML-Datei mit Dokumentations Kommentaren finden Sie in den folgenden Themen:

- [-doc](../../reference/command-line-compiler/doc.md)

- [XML-Kommentartags](../../language-reference/xmldoc/index.md)

- [Verarbeiten der XML-Datei](processing-the-xml-file.md)

- [Vorgehensweise: Erstellen einer XML-Dokumentation](how-to-create-xml-documentation.md)

- [XML-Tools in Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>Weitere Informationen

- [Entwickeln von Anwendungen mit Visual Basic](../../developing-apps/index.md)
- [Visual Basic-Programmierhandbuch](../index.md)
