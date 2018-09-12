---
title: '&lt;Para&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: fa11c713a5ed5793b50865753f8bcdeaabf56e83
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44699711"
---
# <a name="ltparagt-visual-basic"></a>&lt;Para&gt; (Visual Basic)
Gibt an, dass der Inhalt als ein Absatz formatiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a>Parameter  
 `content`  
 Der Text des Absatzes  
  
## <a name="remarks"></a>Hinweise  
 Die `<para>` Tag ist für die Verwendung innerhalb eines Tags wie z. B. [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<"Hinweise" >](../../../visual-basic/language-reference/xmldoc/remarks.md), oder [ \<gibt >](../../../visual-basic/language-reference/xmldoc/returns.md), und können Sie die Struktur auf den Text hinzufügen.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<para>` Tag, teilen den Abschnitt "Hinweise" der `UpdateRecord` Methode in beiden Absätze tauschen.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
