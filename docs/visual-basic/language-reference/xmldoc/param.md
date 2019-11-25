---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4405fdf2defbb27aa2146d20083fd406d1f07236
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352296"
---
# <a name="param-visual-basic"></a>\<param> (Visual Basic)
Defines a parameter name and description.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a>Parameter  
 `name`  
 Der Name eines Methodenparameters. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").  
  
 `description`  
 Eine Beschreibung für den Parameter  
  
## <a name="remarks"></a>Hinweise  
 The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.  
  
 The text for the `<param>` tag will appear in the following locations:  
  
- Parameter Info of IntelliSense. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).  
  
- Object Browser. Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 This example uses the `<param>` tag to describe the `id` parameter.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
