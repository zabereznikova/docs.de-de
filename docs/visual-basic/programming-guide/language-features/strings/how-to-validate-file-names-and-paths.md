---
title: 'Vorgehensweise: Überprüfen von Dateinamen und Pfaden'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: 3b4695dfbcaf05c73bd53af5be7a49d081eb8e47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410579"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Gewusst wie: Überprüfen von Dateinamen und Pfaden in Visual Basic
In diesem Beispiel wird ein Wert zurückgegeben `Boolean` , der angibt, ob eine Zeichenfolge einen Dateinamen oder einen Pfad darstellt. Die Validierung prüft, ob der Name Zeichen enthält, die vom Dateisystem nicht zugelassen werden.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 In diesem Beispiel wird nicht überprüft, ob der Name falsch platzierte Doppelpunkte oder Verzeichnisse ohne Namen enthält oder ob die Länge des Namens die vom System definierte maximale Länge überschreitet. Außerdem wird nicht überprüft, ob die Anwendung über die Berechtigung zum Zugreifen auf die Dateisystem Ressource mit dem angegebenen Namen verfügt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Überprüfen von Zeichenfolgen in Visual Basic](validating-strings.md)
