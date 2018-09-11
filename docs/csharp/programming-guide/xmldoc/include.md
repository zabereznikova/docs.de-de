---
title: '&lt;include&gt; (C#-Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 854c8b61fa8164bccfc9451f2f163dab4a56388f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44214757"
---
# <a name="ltincludegt-c-programming-guide"></a>&lt;include&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Der Name der XML-Datei, die die Dokumentation enthält. Der Dateiname kann mit einem Pfad relativ zur Quellcodedatei qualifiziert werden. `filename` muss in einfache Anführungszeichen (‚‘) eingeschlossen werden.  
  
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
  
 [!code-csharp[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
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
 Die folgende Ausgabe wird generiert, wenn Sie die Klassen „Test“ und „Test2“ mit der folgenden Befehlszeile kompilieren: `/doc:DocFileName.xml.`. Geben Sie in Visual Studio im Bereich „Build“ des Projekt-Designers die Option XML-Dokumentkommentare an. Erkennt der C#-Compiler das \<include>-Tag, sucht er statt in der aktuellen Quelldatei in „xml_include_tag.doc“ nach Dokumentationskommentaren. Der Compiler generiert dann DocFileName.xml. Dies ist die Datei, die von Dokumentationstools wie z.B. [Sandcastle](https://github.com/EWSoftware/SHFB) genutzt wird, um die endgültige Dokumentation zu erzeugen.  
  
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

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
