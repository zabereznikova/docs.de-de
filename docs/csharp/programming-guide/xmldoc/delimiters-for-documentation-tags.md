---
title: "Trennzeichen f&#252;r Dokumentationstags (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/** */-Trennzeichen für C#-Dokumentationstags"
  - "///-Trennzeichen für C#-Dokumentation"
  - "XML [C#], Trennzeichen"
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Trennzeichen f&#252;r Dokumentationstags (C#-Programmierhandbuch)
Die Verwendung von XML\-Dokumentkommentaren erfordert Trennzeichen, anhand derer der Compiler erkennt, wo ein Dokumentationskommentar anfängt und wo er aufhört.  In Verbindung mit den XML\-Dokumentationstags können die folgenden Trennzeichen verwendet werden:  
  
 `///`  
 Einzeiliges Trennzeichen.  Diese Art Trennzeichen kommt in Dokumentationsbeispielen vor und wird in den Visual C\#\-Projektvorlagen verwendet.  Wenn ein Leerzeichen dem Trennzeichen folgt, ist dieses Zeichen nicht in der XML\-Ausgabe enthalten.  
  
> [!NOTE]
>  Die Visual Studio IDE verfügt über ein Feature mit der Bezeichnung Smart\-Kommentar bearbeiten, durch das ein \<summary\>\/\<\/summary\>\-Tagpaar automatisch eingefügt und der Cursor innerhalb dieser Tags positioniert wird, nachdem Sie das `///`\-Trennzeichen im Code\-Editor eingegeben haben.  Greifen Sie auf dieses Feature in den Projekteigenschaftenseiten über [Optionen, Text\-Editor, C\#, Formatierung](/visual-studio/ide/reference/options-text-editor-csharp-formatting) zu.  
  
 `/** */`  
 Mehrzeilige Trennzeichen.  
  
 Bei Verwendung der `/** */`\-Trennzeichen sind einige Formatierungsregeln zu beachten:  
  
-   Wenn der verbleibende Teil der Zeile mit dem `/**` \-Trennzeichen Leerraum ist, wird die Zeile für Kommentare nicht verarbeitet.  Wenn das erste Zeichen nach dem Trennzeichen `/**` ein Leerzeichen ist, wird das entsprechende Zeichen ignoriert und der Rest der Zeile verarbeitet.  Andernfalls wird der gesamte Zeilentext hinter dem `/**`\-Trennzeichen als Teil des Kommentars verarbeitet.  
  
-   Wenn auf der Zeile mit dem `*/` \-Trennzeichen bis zum `*/`\-Trennzeichen nur Leerraum vorhanden ist, wird diese Zeile ignoriert.  Andernfalls wird der Text in der Zeile bis zum `*/`\-Trennzeichen als Teil des Kommentars verarbeitet, wobei die im folgenden Punkt beschriebenen Mustervergleichsregeln gelten.  
  
-   Hinter der Zeile, die mit dem `/**`\-Trennzeichen beginnt, überprüft der Compiler den Anfang der einzelnen Zeilen auf ein gemeinsames Muster.  Das Muster kann aus optionalen Leerstellen und einem Sternchen \(`*`\) bestehen, auf das weitere optionale Leerstellen folgen.  Wenn der Compiler am Anfang jeder Zeile, die nicht mit dem Trennzeichen `/**` oder `*/` beginnt, ein gemeinsames Muster findet, ignoriert er dieses Muster für alle Zeilen.  
  
 Das folgende Beispiel veranschaulicht diese Regeln.  
  
-   Vom folgenden Kommentar wird nur die Zeile verarbeitet, die mit `<summary>` beginnt.  Die folgenden drei Tagformate ergeben identische Kommentare.  
  
    ```  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
  
    ```  
  
-   Der Compiler identifiziert ein gemeinsames Muster " \* " am Anfang der zweiten und dritten Zeile.  Das Muster ist nicht in der Ausgabe enthalten.  
  
    ```  
    /**   
     * <summary>   
     * text </summary>*/   
    ```  
  
-   Der Compiler findet kein gemeinsames Muster im folgenden Kommentar, da das zweite Zeichen auf der dritten Zeile kein Sternchen ist.  Folglich wird der gesamte Text in der zweiten und dritten Zeile als Teil des Kommentars verarbeitet.  
  
    ```  
    /**   
     * <summary>   
       text </summary>  
    */   
    ```  
  
-   Der Compiler findet aus zwei Gründen kein Muster im folgenden Kommentar.  Zunächst ist die Anzahl von Leerzeichen vor dem Sternchen nicht konsistent.  Zweitens beginnt die fünfte Zeile mit einem Tabulatorzeichen, das sich von Leerzeichen unterscheidet.  Folglich wird der gesamte Text von Zeile zwei bis fünf als Teil des Kommentars verarbeitet.  
  
    ```  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [XML\-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML\-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)