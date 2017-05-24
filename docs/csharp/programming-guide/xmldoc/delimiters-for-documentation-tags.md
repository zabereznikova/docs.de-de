---
title: "Trennzeichen für Dokumentationstags (C#-Programmierhandbuch) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
caps.latest.revision: 21
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ba3b38a8bce9f5b49ef863acfae04bc2a39c052a
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a>Trennzeichen für Dokumentationstags (C#-Programmierhandbuch)
Die Verwendung von XML-Dokumentkommentaren erfordert Trennzeichen, die dem Compiler angeben, wo ein Dokumentationskommentar beginnt und endet. Sie können die folgenden Arten von Trennzeichen mit den XML-Dokumentationstags verwenden:  
  
 `///`  
 Einzeiliges Trennzeichen Dies ist die Form, die in den Dokumentationsbeispielen dargestellt und von den Visual C#-Projektvorlagen verwendet wird. Wenn ein Leerzeichen hinter einem Trennzeichen steht, ist dieses Zeichen nicht in der XML-Ausgabe enthalten.  
  
> [!NOTE]
>  Visual Studio-IDE bietet eine Funktion namens Smart Comment Editing, die automatisch die Tags \<summary> und \</summary > einfügt und Ihren Cursor innerhalb dieser Tags verschiebt, nachdem Sie das `///`-Trennzeichen im Code-Editor eingeben. Greifen Sie auf Ihren Eigenschaftenseiten des Projekts über [Formatierung, C#, Text-Editor, Dialogfeld „Optionen“](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-csharp-formatting) auf die Funktion zu.  
  
 `/** */`  
 Mehrzeilige Trennzeichen.  
  
 Es gibt einige Formatierungsregeln zu beachten, wenn Sie die `/** */`-Trennzeichen verwenden.  
  
-   In der Zeile mit dem `/**`-Trennzeichen, wenn der Rest der Zeile Leerraum ist, wird die Zeile für Kommentare nicht verarbeitet. Wenn das erste Zeichen nach dem `/**`-Trennzeichen ein Leerzeichen ist, wird dieses Leerzeichen ignoriert und der Rest der Zeile verarbeitet. Andernfalls wird de gesamte Text der Zeile nach dem `/**`-Trennzeichen als Teil des Kommentars verarbeitet.  
  
-   In der Zeile mit dem `*/`-Trennzeichen, wenn sie nur aus Leerzeichen bis zum `*/`-Trennzeichen besteht, wird diese Zeile ignoriert. Andernfalls wird der Text in der Zeile bis zum `*/`-Trennzeichen als Teil des Kommentars verarbeitet, gemäß den Mustervergleichsregeln, die im folgenden Aufzählungszeichen beschriebenen werden.  
  
-   Für die Zeilen nach der, die mit dem `/**`-Trennzeichen beginnt, sucht der Compiler ein gemeinsames Muster am Anfang jeder Zeile. Das Muster kann aus optionalen Leerzeichen und einem Sternchen bestehen (`*`), gefolgt von weiteren optionalen Leerzeichen. Wenn der Compiler am Anfang jeder Zeile ein gemeinsames Muster findet, die nicht mit dem `/**`- oder `*/`-Trennzeichen beginnt, ignoriert er dieses Muster für jede Zeile.  
  
 In den folgenden Beispielen werden diese Regeln veranschaulicht.  
  
-   Der einzige Teil des folgenden Kommentars, der verarbeitet wird, ist die Zeile, die mit `<summary>` beginnt. Die drei Tag-Formate ergeben identische Kommentare.  
  
    ```  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
    ```  
  
-   Der Compiler identifiziert ein gemeinsames Muster von „*“ am Anfang der zweiten und dritten Zeile. Das Muster ist nicht in der Ausgabe enthalten.  
  
    ```  
    /**   
     * <summary>   
     * text </summary>*/   
    ```  
  
-   Der Compiler findet kein gemeinsames Muster im folgenden Kommentar, da das zweite Zeichen in der dritten Zeile kein Sternchen ist. Daher wird der gesamte Text in der zweiten und dritten Zeile als Teil des Kommentars verarbeitet.  
  
    ```  
    /**   
     * <summary>   
       text </summary>  
    */   
    ```  
  
-   Der Compiler findet aus zwei Gründen kein Muster im folgenden Kommentar. Erstens ist die Anzahl von Leerzeichen vor dem Sternchen nicht konsistent. Zweitens beginnt die fünfte Zeile mit einem Tab, der mit Leerzeichen nicht übereinstimmt. Daher wird aller Text von Zeile zwei bis fünf als Teil des Kommentars verarbeitet.  
  
    ```  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [XML-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)   
 [-doc (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

