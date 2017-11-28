---
title: '&lt;exception&gt; (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bd859a09bfbe9f814bf57f0987fd49ded9ba7100
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltexceptiongt-c-programming-guide"></a>&lt;exception&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>Parameter  
 cref = " `member`"  
 Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist. Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen. `member` muss in doppelte Anführungszeichen (" ") gesetzt werden.  
  
 Weitere Informationen zum Erstellen von cref-Verweisen auf einen generischen Typ finden Sie unter [\<see](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Eine Beschreibung der Ausnahme.  
  
## <a name="remarks"></a>Hinweise  
 Mit dem Tag \<exception> können Sie angeben, welche Ausnahmen ausgelöst werden können. Dieses Tag kann für Definitionen für Methoden, Eigenschaften, Ereignisse und Indexer angewendet werden.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
 Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/index.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
