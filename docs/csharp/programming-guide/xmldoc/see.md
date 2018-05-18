---
title: '&lt;see&gt; (C# -Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 24fa317a0f89568d9aa1b53849e327ef7615cc7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltseegt-c-programming-guide"></a>&lt;see&gt; (C# -Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parameter  
 cref = " `member`"  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe. *member* muss in doppelte Anführungszeichen („“) gesetzt werden.  
  
## <a name="remarks"></a>Hinweise  
 Mit dem \<see>-Tag kann ein Link im Text angegeben werden. Verwenden Sie [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md), um anzugeben, dass Text in einen Abschnitt „Siehe auch“ eingefügt werden soll. Verwenden Sie das [cref-Attribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.  
  
 Kompilieren Sie mit [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
 Im folgenden Beispiel wird ein \<see>-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
