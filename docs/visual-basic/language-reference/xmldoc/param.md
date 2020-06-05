---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: d325d5f9fbfd132630cf280653be214a267a7a80
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400059"
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
 Das- `<param>` Tag sollte im Kommentar für eine Methoden Deklaration verwendet werden, um einen der Parameter für die-Methode zu beschreiben.  
  
 Der Text für das `<param>` Tag wird an den folgenden Speicherorten angezeigt:  
  
- Parameter Informationen von IntelliSense. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).  
  
- Objektkatalog. Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das- `<param>` Tag zum Beschreiben des- `id` Parameters verwendet.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
