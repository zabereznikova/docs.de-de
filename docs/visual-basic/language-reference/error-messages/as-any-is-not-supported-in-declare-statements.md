---
title: "&#39; Alle &#39; wird nicht unterstützt, &#39; Declare &#39; Anweisungen"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords: BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59120622688ee38d5b8f45c08dfc3ae40711fb8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39; Alle &#39; wird nicht unterstützt, &#39; Declare &#39; Anweisungen
Die `Any` wurde mit dem verwendet `Declare` Anweisungen in Visual Basic 6.0 und früheren Versionen gestatten die Verwendung von Argumenten, die beliebige Datentypen enthalten kann. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]unterstützt jedoch Überladen und ermöglicht die `Any` -Datentyp ab.  
  
 **Fehler-ID:** BC30828  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie die Parameter des angegebenen Typs, die Sie verwenden möchten. Zum Beispiel.  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Verwenden der <xref:System.Runtime.InteropServices.MarshalAsAttribute> -Attribut angeben, `As Any` Wenn `Void*` wird von der aufgerufenen Prozedur erwartet.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](../../../framework/interop/creating-prototypes-in-managed-code.md)
