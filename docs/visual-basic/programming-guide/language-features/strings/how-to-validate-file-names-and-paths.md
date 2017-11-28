---
title: "Gewusst wie: Überprüfen von Dateinamen und Pfaden in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9c50d09dd7160992ffd95ececeff623a8aa93d2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Gewusst wie: Überprüfen von Dateinamen und Pfaden in Visual Basic
In diesem Beispiel gibt eine `Boolean` -Wert, der angibt, ob eine Zeichenfolge einen Dateinamen oder den Pfad darstellt. Die Überprüfung wird überprüft, ob der Name Zeichen enthält, die vom Dateisystem zugelassen sind.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 In diesem Beispiel überprüft nicht, wenn der Name falsch Doppelpunkte bzw. Verzeichnisse ohne Namen gesetzt hat oder wenn die Länge des Namens vom System definierte maximale Länge überschreitet. Er überprüft auch nicht, wenn die Anwendung über die Berechtigung zum Zugriff auf die Ressource für das Dateisystem mit dem angegebenen Namen verfügt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.Path.GetInvalidPathChars%2A>  
 [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
