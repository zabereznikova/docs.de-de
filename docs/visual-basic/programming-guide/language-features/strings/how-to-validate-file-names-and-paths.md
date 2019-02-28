---
title: 'Vorgehensweise: Überprüfen Sie Dateinamen und Pfaden in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: d29553071d68319d754406b3104da6e096f908fd
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975523"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Vorgehensweise: Überprüfen Sie Dateinamen und Pfaden in Visual Basic
In diesem Beispiel gibt eine `Boolean` Wert, der angibt, ob eine Zeichenfolge einen Dateinamen oder den Pfad darstellt. Die Validierung wird überprüft, ob der Name Zeichen enthält, die vom Dateisystem nicht zulässig sind.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 In diesem Beispiel überprüft nicht, wenn Sie der Namen Doppelpunkte oder Verzeichnisse ohne Namen falsch platziert wurden oder die Länge des Namens vom System definierte maximale Länge überschreitet. Es wird auch nicht überprüft, wenn die Anwendung die Berechtigung zum Zugriff auf die Ressource für das Dateisystem mit dem angegebenen Namen verfügt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
