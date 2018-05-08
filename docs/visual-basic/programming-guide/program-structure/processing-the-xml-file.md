---
title: Verarbeiten der XML-Datei (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 6be7597f1c03d8aa044eba70ef6287cfc07d9b84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="processing-the-xml-file-visual-basic"></a>Verarbeiten der XML-Datei (Visual Basic)
Für jedes Konstrukt, das zum Generieren von Dokumentation gekennzeichnet ist, wird vom Compiler eine ID-Zeichenfolge generiert. (Informationen zum Kennzeichnen von Code finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) Das Konstrukt wird über die ID-Zeichenfolge eindeutig identifiziert. Programme, die die XML-Datei verarbeiten können die ID-Zeichenfolge zum Identifizieren der entsprechenden [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Metadaten/Reflektion-Element.  
  
 Die XML-Datei ist nicht über eine hierarchische Darstellung des Codes; Es ist eine flache Liste mit einer generierten ID für jedes Element.  
  
 Der Compiler beachtet beim Generieren der ID-Zeichenfolgen die folgenden Regeln:  
  
-   In der Zeichenfolge wird kein Leerzeichen eingefügt.  
  
-   Der erste Teil der ID-Zeichenfolge identifiziert die Art des Elements identifiziert wird, mit einem einzelnen Zeichen, gefolgt von einem Doppelpunkt. Die folgenden Elementtypen werden verwendet.  
  
|Zeichen|Beschreibung|  
|---|---|  
|N|namespace<br /><br /> Ein Namespace können keine Dokumentationskommentare hinzugefügt, Sie können jedoch CREF-Verweise, sofern diese unterstützt wird.|  
|T|Typ: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|Feld: `Dim`|  
|P|Eigenschaft: `Property` (einschließlich Standardeigenschaften)|  
|M|Methode: `Sub`, `Function`, `Declare`, `Operator`|  
|E|Ereignis: `Event`|  
|!|Fehlerzeichenfolge<br /><br /> Der verbleibende Teil der Zeichenfolge enthält Fehlerinformationen. Visual Basic-Compiler generiert Fehlerinformationen für Links, die nicht aufgelöst werden kann.|  
  
-   Der zweite Teil der `String` ist der vollqualifizierte Name des Elements, angefangen beim Stamm des Namespaces. Der Name des Elements, dessen einschließenden Typs und den Namespace werden durch Punkte getrennt. Wenn der Name des Elements selbst Punkte enthält, werden sie ersetzt, durch das Nummernzeichen (#). Es wird vorausgesetzt, dass kein Element mit einem Nummernzeichen direkt im Namen aufweist. Z. B. den vollqualifizierten Namen des der `String` Konstruktor wäre `System.String.#ctor`.  
  
-   Wenn es sich bei Eigenschaften und Methoden um Argumente der Methode handelt, folgt die in Klammern eingeschlossene Argumentliste. Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet. Die Argumente werden durch Kommas voneinander getrennt. Die Codierung des jedes Argument folgt direkt Codieren in eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Signatur.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie die ID-Zeichenfolgen für eine Klasse und ihre Member generiert.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
