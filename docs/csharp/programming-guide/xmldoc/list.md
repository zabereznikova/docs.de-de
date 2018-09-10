---
title: '&lt;list&gt; (C# -Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 3f9d1e2b08b672ca58e96767aedaa71a8826c0ab
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512431"
---
# <a name="ltlistgt-c-programming-guide"></a>&lt;list&gt; (C# -Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a>Parameter  
 `term`  
 Ein zu definierender Begriff, der in `description` definiert wird.  
  
 `description`  
 Entweder ein Element einer Aufzählung oder nummerierten Liste oder die Definition eines `term`.  
  
## <a name="remarks"></a>Hinweise  
 Der \<listheader>-Block wird verwendet, um die Überschriftenzeile einer Tabelle oder einer Definitionsliste zu definieren. Bei der Definition einer Tabelle müssen Sie nur einen Eintrag für „term“ in der Überschrift angeben.  
  
 Jedes Element der Liste wird mit einem \<item>-Block angegeben. Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben. Für eine Tabelle, eine Auflistung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.  
  
 Eine Liste oder Tabelle kann so viele \<item>-Blöcke besitzen wie nötig.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
