---
title: '&lt;Zusammenfassung&gt; (C#-Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 5415603142afaeb5df3f6c2d270a8f895196a207
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltsummarygt-c-programming-guide"></a>&lt;Zusammenfassung&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>Parameter  
 `description`  
 Eine Übersicht des Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Das \<summary>-Tag sollte verwendet werden, um einen Typ oder einen Typmember zu beschreiben. Verwenden Sie [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen. Verwenden Sie das [cref-Attribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md), um Dokumentationswerkzeuge wie [Sandcastle](https://github.com/EWSoftware/SHFB) zum Erstellen von internen Links zu Dokumentationsseiten für Codeelemente zu aktivieren.  
  
 Der Text für das \<summary>-Tag ist die einzige Informationsquelle über den Typ in IntelliSense und wird auch im Fenster des Objektkatalogs angezeigt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden. Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 Das vorherige Beispiel erzeugt folgende XML-Datei.  
  
```xml  
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
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel stellt dar, wie Sie einen `cref`-Verweis auf generische Typen erstellen.  
  
 [!code-csharp[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 Das vorherige Beispiel erzeugt folgende XML-Datei.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
