---
title: 'Gewusst wie: Überprüfen von Dateinamen und Pfaden in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: ab3df335bc5bba21d386bb69b12d840990e629fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647803"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Gewusst wie: Überprüfen von Dateinamen und Pfaden in Visual Basic
In diesem Beispiel gibt eine `Boolean` -Wert, der angibt, ob eine Zeichenfolge einen Dateinamen oder den Pfad darstellt. Die Überprüfung wird überprüft, ob der Name Zeichen enthält, die vom Dateisystem zugelassen sind.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 In diesem Beispiel überprüft nicht, wenn der Name falsch Doppelpunkte bzw. Verzeichnisse ohne Namen gesetzt hat oder wenn die Länge des Namens vom System definierte maximale Länge überschreitet. Er überprüft auch nicht, wenn die Anwendung über die Berechtigung zum Zugriff auf die Ressource für das Dateisystem mit dem angegebenen Namen verfügt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.Path.GetInvalidPathChars%2A>  
 [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
