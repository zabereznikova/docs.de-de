---
title: "&lt;include&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "include"
  - "<include>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<include> (C#-XML-Tag)"
  - "include (C#-XML-Tag)"
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &lt;include&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### Parameter  
 `filename`  
 Der Name der XML\-Datei, die die Dokumentation enthält  Der Dateiname kann mit einem Pfad gekennzeichnet sein.  `filename` muss in einfache Anführungszeichen \(' '\) eingeschlossen werden.  
  
 `tagpath`  
 Der Pfad der Tags in `filename`, der zum `name`\-Tag führt.  Der Pfad muss in einfache Anführungszeichen \(**' '**\) eingeschlossen werden.  
  
 `name`  
 Der Namensbezeichner in dem Tag, das sich vor den Kommentaren befindet. `name` weist eine `id` auf.  
  
 `id`  
 die ID für das Tag, das sich vor den Kommentaren befindet.  Die ID muss in doppelte Anführungszeichen \(" "\) eingeschlossen werden.  
  
## Hinweise  
 Mit dem \<include\>\-Tag kann auf Kommentare in anderen Dateien verwiesen werden, die die Typen und Member im Quellcode beschreiben.  Dies stellt eine Alternative zum direkten Positionieren der Dokumentationskommentare in Quellcodedateien dar.  Durch das Ablegen der Dokumentation in einer separaten Datei können Sie die Quellcodeverwaltung getrennt vom Quellcode auf die Dokumentation anwenden.  Eine Person kann die Quellcodedatei auschecken lassen, und jemand anderes kann die Dokumentationsdatei auschecken lassen.  
  
 Das \<include\>\-Tag verwendet die XPath\-Syntax von XML.  Weitere Informationen zu Anpassungsmöglichkeiten der Verwendung von \<include\> finden Sie in der XPath\-Dokumentation.  
  
## Beispiel  
 Hierbei handelt es sich um ein Beispiel mit mehreren Dateien.  Es folgt die Auflistung des Inhalts der ersten Datei, in der \<include\> verwendet wird:  
  
 [!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
 Die zweite Datei, **xml\_include\_tag.doc**, enthält die folgenden Dokumentationskommentare:  
  
```  
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
  
## Programmausgabe  
 Die folgende Ausgabe wird generiert, wenn Sie die Test\-Klasse und die Test2\-Klasse mit der folgenden Befehlszeile kompilieren: `/doc:DocFileName.xml.`. In Visual Studio geben Sie die XML\-Dokumentkommentaroption im Bereich "Build" des Projekt\-Designers an.  Wenn der C\#\-Compiler das \<include\>\-Tag sieht, sucht er in xml\_include\_tag.doc statt der aktuellen Quelldatei nach Dokumentationskommentaren.  Der Compiler generiert dann DocFileName.xml, und dies ist die Datei, die von Dokumentationstools wie z. B. [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061) verwendet wird, um die abschließende Dokumentation zu erzeugen.  
  
```  
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
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)