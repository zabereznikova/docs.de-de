---
title: '&lt;typeparam&gt; (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e1b8800e39b1ee5eeac8c5d3e4390ed3226b33a3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
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
  
 Der Text für die `<typeparam>` Tag wird in IntelliSense angezeigt werden, dem [Objekt Browserfenster](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) Webbericht für Codekommentare.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
