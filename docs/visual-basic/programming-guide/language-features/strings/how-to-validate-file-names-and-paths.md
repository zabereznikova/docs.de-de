---
title: 'Vorgehensweise: Überprüfen Sie Dateinamen und Pfaden in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c8e01a0f5a3f99fdbc424d6cd7d224367c7bad08
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835803"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Vorgehensweise: Überprüfen Sie Dateinamen und Pfaden in Visual Basic
In diesem Beispiel gibt eine `Boolean` Wert, der angibt, ob eine Zeichenfolge einen Dateinamen oder den Pfad darstellt. Die Validierung wird überprüft, ob der Name Zeichen enthält, die vom Dateisystem nicht zulässig sind.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 In diesem Beispiel überprüft nicht, wenn Sie der Namen Doppelpunkte oder Verzeichnisse ohne Namen falsch platziert wurden oder die Länge des Namens vom System definierte maximale Länge überschreitet. Es wird auch nicht überprüft, wenn die Anwendung die Berechtigung zum Zugriff auf die Ressource für das Dateisystem mit dem angegebenen Namen verfügt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
