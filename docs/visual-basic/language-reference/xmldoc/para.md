---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 8f28ecc33eea99150509bb4bade047489b4b826b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352307"
---
# <a name="para-visual-basic"></a>\<para > (Visual Basic)
Gibt an, dass der Inhalt als Absatz formatiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Parameter  
 `content`  
 Der Text des Absatzes  
  
## <a name="remarks"></a>Hinweise  
 Das `<para>`-Tag dient zur Verwendung innerhalb eines Tags, z. b. [\<Zusammenfassungs >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<Anmerkungen >](../../../visual-basic/language-reference/xmldoc/remarks.md), oder [\<gibt > zurück](../../../visual-basic/language-reference/xmldoc/returns.md), und Sie können dem Text Struktur hinzufügen.  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das `<para>`-Tag verwendet, um den Abschnitt "Hinweise" für die `UpdateRecord`-Methode in zwei Absätze aufzuteilen.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
