---
title: 'Gewusst wie: Schreiben in Binärdateien'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: 72d019f5f49868bd84d0507535e8ebc547b50e25
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334429"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a>Gewusst wie: Schreiben in Binärdateien in Visual Basic

Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>-Methode schreibt Daten in eine Binärdatei. Wenn der `append`-Parameter `True` ist, fügt er die Daten an die Datei an. Andernfalls werden die Daten in der Datei überschrieben.

Wenn der angegebene Pfad mit dem Dateinamen nicht zulässig ist, wird eine <xref:System.IO.DirectoryNotFoundException>-Ausnahme ausgelöst. Wenn der Pfad zulässig ist, die Datei aber nicht existiert, wird die Datei erstellt.

## <a name="to-write-to-a-binary-file"></a>Schreiben in eine Binärdatei

Verwenden Sie die `WriteAllBytes`-Methode, die den Dateipfad und -namen und die zu schreibenden Bytes bereitstellt. In diesem Beispiel wird das Datenarray `CustomerData` an die Datei `CollectedData.dat` angefügt.

[!code-vb[VbVbcnMyFileSystem#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#27)]

## <a name="robust-programming"></a>Stabile Programmierung

Die folgenden Bedingungen können einen Ausnahmefehler verursachen:

- Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0 (null), der Pfad enthält nur Leerzeichen, oder er enthält ungültige Zeichen. (<xref:System.ArgumentException>).

- Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).

- `File` verweist auf einen Pfad, der nicht vorhanden ist (<xref:System.IO.FileNotFoundException> oder<xref:System.IO.DirectoryNotFoundException>).

- Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).

- Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).

- Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).

- Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [Gewusst wie: Schreiben von Text in Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
