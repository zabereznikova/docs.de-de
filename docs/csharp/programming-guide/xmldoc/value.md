---
title: '&lt;value&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: e3b77af312abcc99945a22abf2b73ebd47556026
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53234525"
---
# <a name="ltvaluegt-c-programming-guide"></a>&lt;value&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>Parameter  
 `property-description`  
 Eine Beschreibung der Eigenschaft  
  
## <a name="remarks"></a>Hinweise  
 Mit dem \<value>-Tag können Sie den Wert beschreiben, den eine Eigenschaft darstellt. Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Entwicklungsumgebung von Visual Studio .NET der neuen Eigenschaft ein [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md)-Tag hinzugefügt wird. Sie sollten dann manuell ein \<value>-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
