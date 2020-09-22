---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 19300a928a59c7259f81b282bd28d9bdd447d76b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872623"
---
# <a name="param-visual-basic"></a>\<param> (Visual Basic)

Definiert einen Parameternamen und eine Beschreibung.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a>Parameter  

 `name`  
 Der Name eines Methodenparameters. Setzen Sie den Namen in doppelte Anführungszeichen (" ").  
  
 `description`  
 Eine Beschreibung für den Parameter  
  
## <a name="remarks"></a>Hinweise  

 Das `<param>`-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.  
  
 Der Text für das `<param>` Tag wird an den folgenden Speicherorten angezeigt:  
  
- Parameter Informationen von IntelliSense. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).  
  
- Objektkatalog. Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird das- `<param>` Tag zum Beschreiben des- `id` Parameters verwendet.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
