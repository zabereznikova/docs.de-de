---
title: '&lt;Param&gt; (Visual Basic) | Microsoft-Dokumentation'
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
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
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
ms.openlocfilehash: 41852a7fc41595050940d87f9e741df5cb23361c
ms.lasthandoff: 03/13/2017

---
# <a name="ltparamgt-visual-basic"></a>&lt;Param&gt; (Visual Basic)
Definiert einen Parametername und Beschreibung.  
  
## <a name="syntax"></a>Syntax  
  
```  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 Der Name des Methodenparameters. Der Name muss in doppelte Anführungszeichen ("").  
  
 `description`  
 Eine Beschreibung für den Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Der `<param>` -Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Parameter der Methode zu beschreiben.  
  
 Der Text für die `<param>` Tag wird in den folgenden Speicherorten angezeigt:  
  
-   ParameterInfo von IntelliSense. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense).  
  
-   Objektkatalog. Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)..  
  
 Kompilieren Sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) Dokumentationskommentare zu einer Datei.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<param>` Tag beschreiben die `id` Parameter.  
  
 [!code-vb[VbVbcnXmlDocComments&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
