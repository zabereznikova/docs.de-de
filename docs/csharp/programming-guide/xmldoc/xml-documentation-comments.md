---
title: "XML-Dokumentationskommentare (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.xml"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, XML-Codekommentare"
  - "C#-Quellcodedateien"
  - "Kommentare [C#], XML"
  - "Dokumentationskommentare [C#]"
  - "XML [C#], Codekommentare"
  - "XML-Dokumentationskommentare [C#]"
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# XML-Dokumentationskommentare (C#-Programmierhandbuch)
In Visual C\# lässt sich eine Dokumentation des Codes erstellen. Dazu werden XML\-Elemente in spezielle Kommentarfelder \(angegeben durch drei Schrägstriche\) des Quellcodes unmittelbar vor dem Codeblock eingefügt, auf den sie sich beziehen, z. B.:  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass{}  
```  
  
 Wenn Sie mit der Option [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompilieren, sucht der Compiler alle XML\-Tags im Quellcode und erstellt eine XML\-Dokumentationsdatei.  Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061) verwenden.  
  
 Zum Verweisen auf XML\-Elemente \(beispielsweise verarbeitet eine Funktion bestimmte XML\-Elemente, die Sie in einem XML\-Dokumentationskommentar beschreiben möchten\) können Sie die Standardnotierungsart verwenden \(`<` und `>`\).  Zum Verweisen auf generische Bezeichner in Codeverweiselementen \(`cref`\-Elementen\) können Sie entweder die Escapezeichen \(z. B. `cref=”List<T>”`\) oder geschweifte Klammern \(`cref=”List{T}”`\) verwenden.  Als Sonderfall analysiert der Compiler die geschweiften Klammern als spitze Klammern, um das Erstellen des Dokumentationskommentars beim Verweisen auf generische Bezeichner weniger schwerfällig zu gestalten.  
  
> [!NOTE]
>  XML\-Dokumentationskommentare sind keine Metadaten und sind nicht in der kompilierten Assembly enthalten. Folglich ist der Zugriff auf sie über Reflektion nicht möglich.  
  
## In diesem Abschnitt  
  
-   [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [Verarbeiten der XML\-Datei](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [Trennzeichen für Dokumentationstags](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [Gewusst wie: Verwenden der XML\-Dokumentationsfunktionen](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:  
  
-   [\/doc \(Verarbeiten von Dokumentationskommentaren\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)