---
title: Verarbeiten der XML-Datei (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: aa31f0f618990d4e57520a1098ec80b722e1cbe3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543668"
---
# <a name="processing-the-xml-file-visual-basic"></a>Verarbeiten der XML-Datei (Visual Basic)
Für jedes Konstrukt, das zum Generieren von Dokumentation gekennzeichnet ist, wird vom Compiler eine ID-Zeichenfolge generiert. (Informationen dazu, wie Code mit Tags versehen werden, finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md).) Das Konstrukt wird über die ID-Zeichenfolge eindeutig identifiziert. Programme, die die XML-Datei verarbeiten können die ID-Zeichenfolge zum Identifizieren der entsprechenden [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Metadaten-/ Reflektionselement.  
  
 Die XML-Datei ist nicht über eine hierarchische Darstellung des Codes; Es ist eine flache Liste mit einer generierten ID für jedes Element.  
  
 Der Compiler beachtet beim Generieren der ID-Zeichenfolgen die folgenden Regeln:  
  
-   In der Zeichenfolge wird kein Leerraum platziert.  
  
-   Der erste Teil der ID-Zeichenfolge kennzeichnet die Art des zu identifizierenden Members durch ein einzelnes Zeichen, gefolgt von einem Doppelpunkt. Die folgenden Membertypen werden verwendet.  
  
|Zeichen|Beschreibung|  
|---|---|  
|N|namespace<br /><br /> Ein Namespace können keine Dokumentationskommentare hinzugefügt, Sie können jedoch CREF-Verweise hinzugefügt, wenn dies unterstützt wird.|  
|T|Typ: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|Feld: `Dim`|  
|P|Eigenschaft: `Property` (einschließlich Eigenschaften)|  
|M|Methode: `Sub`, `Function`, `Declare`, `Operator`|  
|E|Ereignis: `Event`|  
|!|Fehlerzeichenfolge<br /><br /> Der verbleibende Teil der Zeichenfolge enthält Fehlerinformationen. Visual Basic-Compiler generiert die Fehlerinformationen für Links, die nicht aufgelöst werden kann.|  
  
-   Der zweite Teil der `String` ist der vollqualifizierte Name des Elements im Stammverzeichnis des Namespace ab. Der Name des Elements, seiner einschließenden Typen und den Namespace sind durch Punkte getrennt. Wenn der Name des Elements selbst Punkte enthält, werden sie ersetzt durch ein Nummernzeichen (#). Es wird vorausgesetzt, dass kein Element mit einem Nummernzeichen direkt im Namen hat. Z. B. den vollqualifizierten Namen des der `String` Konstruktor wäre `System.String.#ctor`.  
  
-   Wenn es sich bei Eigenschaften und Methoden um Argumente der Methode handelt, folgt die in Klammern eingeschlossene Argumentliste. Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet. Die Argumente werden durch Kommas voneinander getrennt. Die Codierung jedes Arguments erfolgt genauso wie es in codiert wird eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Signatur.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie die ID für eine Klasse Zeichenfolgen und ihre Member generiert werden.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [Vorgehensweise: Erstellen von XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
