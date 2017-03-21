---
title: Verarbeiten der XML-Datei (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 72b2832d0131adf39a37ebd9297b43fb34ea49ba
ms.lasthandoff: 03/13/2017

---
# <a name="processing-the-xml-file-visual-basic"></a>Verarbeiten der XML-Datei (Visual Basic)
Der Compiler generiert eine ID-Zeichenfolge für jedes Konstrukt in Ihrem Code, der zum Generieren von Dokumentation gekennzeichnet ist. (Informationen zum Markieren von Code finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) Die ID-Zeichenfolge identifiziert eindeutig das Konstrukt. Programme, die die XML-Datei verarbeiten können die ID-Zeichenfolge zum Identifizieren der entsprechenden [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Metadaten/Reflektion-Element.  
  
 Die XML-Datei ist keine hierarchische Darstellung des Codes. Es ist eine flache Liste mit einer generierten ID für jedes Element.  
  
 Der Compiler verwendet die folgenden Regeln beim Generieren der ID-Zeichenfolgen:  
  
-   In der Zeichenfolge wird kein Leerzeichen eingefügt.  
  
-   Der erste Teil der ID-Zeichenfolge kennzeichnet die Art des Elements identifiziert werden, durch ein einzelnes Zeichen, gefolgt von einem Doppelpunkt. Die folgenden Membertypen werden verwendet.  
  
|Zeichen|Beschreibung|  
|---|---|  
|N|namespace<br /><br /> Ein Namespace können keine Dokumentationskommentare hinzugefügt, Sie können jedoch CREF-Verweise, sofern unterstützt.|  
|T|type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`|  
|F|Feld:`Dim`|  
|P|Eigenschaft: `Property` (einschließlich Standardeigenschaften)|  
|M|method: `Sub`, `Function`, `Declare`,`Operator`|  
|E|Ereignis:`Event`|  
|!|Fehlerzeichenfolge<br /><br /> Der Rest der Zeichenfolge enthält Informationen über den Fehler. Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler werden Fehlerinformationen für Links, die nicht aufgelöst werden kann.|  
  
-   Der zweite Teil der `String` ist der vollqualifizierte Name des Elements, beginnend mit dem Stamm des Namespace. Der Name des Elements, seiner einschließenden Typen und der Namespace sind durch Punkte getrennt. Wenn der Name des Elements selbst Punkte enthält, werden sie ersetzt durch ein Nummernzeichen (#). Es wird vorausgesetzt, dass kein Element ein Nummernzeichen direkt im Namen aufweist. Z. B. den vollqualifizierten Namen von der `String` Konstruktor wäre `System.String.#ctor`.  
  
-   Eigenschaften und Methoden sind die Argumente der Methode folgt die Argumentliste in Klammern eingeschlossen. Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet. Die Argumente werden durch Kommas getrennt. Die Codierung jedes Arguments erfolgt genauso wie es in ist eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Signatur.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie die ID-Zeichenfolgen für eine Klasse und ihre Member generiert.  
  
 [!code-vb[VbVbcnXmlDocComments&#10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [/ doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
