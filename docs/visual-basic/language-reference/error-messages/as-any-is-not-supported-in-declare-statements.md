---
title: '&#39;Wie ein anderer&#39; wird nicht unterstützt &#39;Declare&#39; Anweisungen'
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 560ddc8674718f98f3e1a2f6d4facdb198f5e506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709858"
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39;Wie ein anderer&#39; wird nicht unterstützt &#39;Declare&#39; Anweisungen
Die `Any` Datentyp wurde verwendet, mit `Declare` Anweisungen in Visual Basic 6.0 und früheren Versionen, um die Verwendung von Argumenten zu ermöglichen, die beliebige Datentypen enthalten könnte. Überladen zulässt, jedoch von Visual Basic unterstützt und löst so die `Any` -Datentyp ab.  
  
 **Fehler-ID:** BC30828  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie die Parameter des angegebenen Typs, die Sie verwenden möchten; Zum Beispiel.  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Verwenden der <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut an `As Any` beim `Void*` wird von der aufgerufenen Prozedur erwartet.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](../../../framework/interop/creating-prototypes-in-managed-code.md)
