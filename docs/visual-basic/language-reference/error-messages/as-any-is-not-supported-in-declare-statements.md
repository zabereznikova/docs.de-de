---
title: As Any wird in Declare-Anweisungen nicht unterstützt.
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: c6c792e02bb655dc8a9544c4b5b46a64210556f6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839924"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a>As Any wird in Declare-Anweisungen nicht unterstützt.
Die `Any` Datentyp wurde verwendet, mit `Declare` Anweisungen in Visual Basic 6.0 und früheren Versionen, um die Verwendung von Argumenten zu ermöglichen, die beliebige Datentypen enthalten könnte. Überladen zulässt, jedoch von Visual Basic unterstützt und löst so die `Any` -Datentyp ab.  
  
 **Fehler-ID:** BC30828  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie die Parameter des angegebenen Typs, die Sie verwenden möchten; Zum Beispiel.  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2.  Verwenden der <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut an `As Any` beim `Void*` wird von der aufgerufenen Prozedur erwartet.  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](../../../framework/interop/creating-prototypes-in-managed-code.md)
