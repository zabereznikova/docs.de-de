---
title: 'Vorgehensweise: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 08ad2f1c9455853e92533a7f00726c73b6adb87e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071156"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten (Visual Basic)

In diesem Beispiel wird die Zeichenfolge "abcd" aus einzelnen Zeichen erstellt.  
  
## <a name="example"></a>Beispiel  

 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  

 Diese Methode hat keine besonderen Anforderungen.  
  
 Die Syntax `"a"c` , bei der ein einzelnes `c` einem einzelnen Zeichen in Anführungszeichen folgt, wird zum Erstellen eines Zeichenliterals verwendet.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 NULL-Zeichen (äquivalent zu `Chr(0)` ) in der Zeichenfolge führen zu unerwarteten Ergebnissen, wenn die Zeichenfolge verwendet wird. Das NULL-Zeichen wird in die Zeichenfolge eingeschlossen, jedoch werden Zeichen, die auf das NULL-Zeichen folgen, in einigen Situationen nicht angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.String>
- [Char-Datentyp](../../../language-reference/data-types/char-data-type.md)
- [Datentypen](../data-types/index.md)
