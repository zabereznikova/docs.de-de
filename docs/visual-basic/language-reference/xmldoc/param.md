---
title: '&lt;Param&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4cb3de06d574f8b9abb3e3e11641a6ada750b56a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856490"
---
# <a name="ltparamgt-visual-basic"></a>&lt;Param&gt; (Visual Basic)
Definiert einen Namen und eine Beschreibung an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 Der Name eines Methodenparameters. Setzen Sie den Namen in doppelte Anführungszeichen (" ").  
  
 `description`  
 Eine Beschreibung für den Parameter  
  
## <a name="remarks"></a>Hinweise  
 Die `<param>` -Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Parameter für die Methode zu beschreiben.  
  
 Der Text für die `<param>` Tag wird in den folgenden Speicherorten angezeigt:  
  
-   ParameterInfo von IntelliSense. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).  
  
-   Objekt-Browser. Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<param>` Tag zum Beschreiben der `id` Parameter.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
