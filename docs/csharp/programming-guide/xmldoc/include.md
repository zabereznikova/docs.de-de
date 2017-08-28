---
title: '&lt;include&gt; (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- include
- <include>
dev_langs:
- CSharp
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1788a51d1bc61ba5e69774d65c14001851924472
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ltincludegt-c-programming-guide"></a>&lt;include&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Der Name der XML-Datei, die die Dokumentation enthält. Der Dateiname kann mit einem Pfad qualifiziert werden. `filename` muss in einfache Anführungszeichen (‚‘) eingeschlossen werden.  
  
 `tagpath`  
 Der Pfad der Tags in `filename`, der zum Tag `name` führt. Der Pfad muss in einfache Anführungszeichen (‚‘) eingeschlossen werden.  
  
 `name`  
 Der Namensbezeichner in dem Tag, das sich vor den Kommentaren befindet. `name` besitzt eine `id`.  
  
 `id`  
 Die ID für das Tag, das sich vor den Kommentaren befindet. Die ID muss in doppelte Anführungszeichen („“) eingeschlossen werden.  
  
## <a name="remarks"></a>Hinweise  
 Mit dem \<include>-Tag können Sie auf Kommentare in einer anderen Datei verweisen, die die Typen und Member in Ihrem Quellcode beschreiben. Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei. Durch das Ablegen der Dokumentation in einer separaten Datei können Sie die Quellcodeverwaltung unabhängig vom Quellcode auf die Dokumentation anwenden. Eine Person kann die Quellcodedatei auschecken, eine andere die Dokumentationsdatei.  
  
 Das \<include>-Tag verwendet die XPath-Syntax von XML. Weitere Anpassungsmöglichkeiten der Verwendung von \<include> finden Sie in der XPath-Dokumentation.  
  
## <a name="example"></a>Beispiel  
 Dies ist ein Beispiel einer Mehrfachdatei. Die erste Datei, die \<include> verwendet, wird unten aufgeführt:  
  
 [!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
 Die zweite Datei, xml_include_tag.doc, enthält die folgenden Dokumentationskommentare:  
  
```xml  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## <a name="program-output"></a>Programmausgabe  
 Die folgende Ausgabe wird generiert, wenn Sie die Klassen „Test“ und „Test2“ mit der folgenden Befehlszeile kompilieren: `/doc:DocFileName.xml.`. Geben Sie in Visual Studio im Bereich „Build“ des Projekt-Designers die Option XML-Dokumentkommentare an. Erkennt der C#-Compiler das \<include>-Tag, sucht er anstatt in der aktuellen Quelldatei in xml_include_tag.doc nach Dokumentationskommentaren. Der Compiler generiert dann DocFileName.xml. Dies ist die Datei, die von Dokumentationstools wie z.B. [Sandcastle](https://github.com/EWSoftware/SHFB) genutzt wird, um die endgültige Dokumentation zu erzeugen.  
  
```xml  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

