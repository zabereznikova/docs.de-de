---
title: "&lt;summary&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<summary>"
  - "summary"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<summary> (C#-XML-Tag)"
  - "summary (C#-XML-Tag)"
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# &lt;summary&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<summary>description</summary>  
```  
  
#### Parameter  
 `description`  
 eine Zusammenfassung des Objekts.  
  
## Hinweise  
 Das \<summary\>\-Tag sollte verwendet werden, um einen Typ oder einen Typmember zu beschreiben.  Mit [\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md) können Sie zusätzliche Informationen zu einer Typbeschreibung angeben.  Aktivieren Sie Dokumentationstools wie [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061) mit dem [cref\-Attribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.  
  
 Der Text für das \<summary\>\-Tag ist die einzige Informationsquelle über den Typ in IntelliSense und wird auch im [Object Browser Window](http://msdn.microsoft.com/de-de/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) angezeigt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061) verwenden.  
  
## Beispiel  
 [!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/summary_1.cs)]  
  
 Im vorherige Beispiel erzeugt die folgende XML\-Datei.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein `cref`\-Verweis auf einen generischen Typ erstellt wird.  
  
 [!code-cs[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/summary_2.cs)]  
  
 Im vorherige Beispiel erzeugt die folgende XML\-Datei.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
  
```  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)