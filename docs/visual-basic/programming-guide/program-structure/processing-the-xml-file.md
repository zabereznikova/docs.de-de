---
title: Verarbeiten der XML-Datei
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 81d2c8d305e828b2963a0af9d97ec35b1745197a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398330"
---
# <a name="processing-the-xml-file-visual-basic"></a>Verarbeiten der XML-Datei (Visual Basic)
Für jedes Konstrukt, das zum Generieren von Dokumentation gekennzeichnet ist, wird vom Compiler eine ID-Zeichenfolge generiert. (Informationen zum Markieren Ihres Codes finden Sie unter XML- [Kommentar Tags](../../language-reference/xmldoc/index.md).) Mit der ID-Zeichenfolge wird das Konstrukt eindeutig identifiziert. Programme, die die XML-Datei verarbeiten, können die ID-Zeichenfolge verwenden, um die entsprechenden .NET Framework Metadata/Reflection-Element zu identifizieren.  
  
 Die XML-Datei ist keine hierarchische Darstellung des Codes. Es handelt sich um eine flache Liste mit einer generierten ID für jedes Element.  
  
 Der Compiler beachtet beim Generieren der ID-Zeichenfolgen die folgenden Regeln:  
  
- In der Zeichenfolge wird kein Leerraum platziert.  
  
- Der erste Teil der ID-Zeichenfolge kennzeichnet die Art des zu identifizierenden Members durch ein einzelnes Zeichen, gefolgt von einem Doppelpunkt. Die folgenden Elementtypen werden verwendet.  
  
|Zeichen|Beschreibung|  
|---|---|  
|N|namespace<br /><br /> Sie können einem Namespace keine Dokumentations Kommentare hinzufügen. Sie können jedoch auch Verweise auf diese erstellen, sofern dies unterstützt wird.|  
|T|Geben Sie Folgendes ein: `Class` , `Module` ,, `Interface` `Structure` , `Enum` ,`Delegate`|  
|F|Flächen`Dim`|  
|P|Property: `Property` (einschließlich der Standardeigenschaften)|  
|M|Methode: `Sub` , `Function` , `Declare` ,`Operator`|  
|E|Veranstalter`Event`|  
|!|Fehlerzeichenfolge<br /><br /> Der verbleibende Teil der Zeichenfolge enthält Fehlerinformationen. Der Visual Basic-Compiler generiert Fehlerinformationen für Links, die nicht aufgelöst werden können.|  
  
- Der zweite Teil des `String` ist der voll qualifizierte Name des Elements, beginnend mit dem Stamm des Namespace. Der Name des Elements, der einschließende Typ (en) und der Namespace werden durch Punkte getrennt. Wenn der Name des Elements selbst Zeiträume enthält, werden diese durch das Nummern Zeichen (#) ersetzt. Es wird davon ausgegangen, dass kein Element direkt in seinem Namen über ein Nummern Zeichen verfügt. Beispielsweise wäre der voll qualifizierte Name des `String` Konstruktors `System.String.#ctor` .  
  
- Wenn es sich bei Eigenschaften und Methoden um Argumente der Methode handelt, folgt die in Klammern eingeschlossene Argumentliste. Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet. Die Argumente werden durch Kommas voneinander getrennt. Die Codierung der einzelnen Argumente erfolgt direkt nach dem Codieren in einer .NET Framework Signatur.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie die ID-Zeichen folgen für eine Klasse und ihre Member generiert werden.  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>Weitere Informationen

- [-doc](../../reference/command-line-compiler/doc.md)
- [Vorgehensweise: Erstellen einer XML-Dokumentation](how-to-create-xml-documentation.md)
