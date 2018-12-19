---
title: '&lt;typeparam&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 87629346238e92cf95141e72d79be37f8b11e48f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241813"
---
# <a name="lttypeparamgt-c-programming-guide"></a>&lt;typeparam&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 Der Name des Typparameters. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").  
  
 `description`  
 Eine Beschreibung für den Typparameter.  
  
## <a name="remarks"></a>Hinweise  
 Die `<typeparam>` -Tag sollte im Kommentar für einen generischen Typ oder eine Methodendeklaration verwendet werden, um einen Typparameter zu beschreiben. Fügen Sie ein Tag für jeden Typparameter des generischen Typs oder der Methode hinzu.  
  
 Weitere Informationen finden Sie unter [Generika](../../../csharp/programming-guide/generics/index.md).  
  
 Der Text für die `<typeparam>` Tag wird in IntelliSense angezeigt werden, dem [Objekt Browserfenster](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) Webbericht für Codekommentare.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
