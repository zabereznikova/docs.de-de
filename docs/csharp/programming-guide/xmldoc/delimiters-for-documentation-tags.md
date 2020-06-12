---
title: Trennzeichen für Dokumentationstags – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: 7e62c75fd393c4009c987830cca41e512cdb6250
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287389"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a>Trennzeichen für Dokumentationstags (C#-Programmierhandbuch)

Die Verwendung von XML-Dokumentkommentaren erfordert Trennzeichen, die dem Compiler angeben, wo ein Dokumentationskommentar beginnt und endet. Sie können die folgenden Arten von Trennzeichen mit den XML-Dokumentationstags verwenden:

- `///`

  Einzeiliges Trennzeichen Dies ist die Form, die in den Dokumentationsbeispielen und von den C#-Projektvorlagen verwendet wird. Wenn ein Leerzeichen hinter einem Trennzeichen steht, ist dieses Zeichen nicht in der XML-Ausgabe enthalten.

  > [!NOTE]
  > Die integrierte Entwicklungsumgebung (IDE) von Visual Studio fügt die Tags `<summary>` und `</summary>` automatisch ein und verschiebt Ihren Cursor innerhalb dieser Tags, nachdem Sie das Trennzeichen `///` in den Code-Editor eingegeben haben. Sie können diese Funktion im [Dialogfeld „Optionen“](/visualstudio/ide/reference/options-text-editor-csharp-advanced) aktivieren oder deaktivieren.
  
- `/** */`

  Mehrzeilige Trennzeichen.

  Es gibt einige Formatierungsregeln zu beachten, wenn Sie die `/** */`-Trennzeichen verwenden:
  
  - In der Zeile mit dem `/**`-Trennzeichen, wenn der Rest der Zeile Leerraum ist, wird die Zeile für Kommentare nicht verarbeitet. Wenn das erste Zeichen nach dem `/**`-Trennzeichen ein Leerzeichen ist, wird dieses Leerzeichen ignoriert und der Rest der Zeile verarbeitet. Andernfalls wird de gesamte Text der Zeile nach dem `/**`-Trennzeichen als Teil des Kommentars verarbeitet.

  - In der Zeile mit dem `*/`-Trennzeichen, wenn sie nur aus Leerzeichen bis zum `*/`-Trennzeichen besteht, wird diese Zeile ignoriert. Andernfalls wird der Text der Zeile bis zum `*/`-Trennzeichen als Teil des Kommentars verarbeitet.
  
  - Für die Zeilen nach der, die mit dem `/**`-Trennzeichen beginnt, sucht der Compiler ein gemeinsames Muster am Anfang jeder Zeile. Das Muster kann aus optionalen Leerzeichen und einem Sternchen bestehen (`*`), gefolgt von weiteren optionalen Leerzeichen. Wenn der Compiler am Anfang jeder Zeile ein gemeinsames Muster findet, die nicht mit dem `/**`- oder `*/`-Trennzeichen beginnt, ignoriert er dieses Muster für jede Zeile.

  In den folgenden Beispielen werden diese Regeln veranschaulicht.

  - Der einzige Teil des folgenden Kommentars, der verarbeitet wird, ist die Zeile, die mit `<summary>` beginnt. Die drei Tag-Formate ergeben identische Kommentare.

    ```csharp
    /** <summary>text</summary> */

    /**
    <summary>text</summary>
    */

    /**
     * <summary>text</summary>
    */
    ```

  - Der Compiler identifiziert ein gemeinsames Muster von „\*“ am Anfang der zweiten und dritten Zeile. Das Muster ist nicht in der Ausgabe enthalten.

    ```csharp
    /**
     * <summary>
     * text </summary>*/
    ```

  - Der Compiler findet kein gemeinsames Muster im folgenden Kommentar, da das zweite Zeichen in der dritten Zeile kein Sternchen ist. Daher wird der gesamte Text in der zweiten und dritten Zeile als Teil des Kommentars verarbeitet.

    ```csharp
    /**
     * <summary>
       text </summary>
    */
    ```

  - Der Compiler findet aus zwei Gründen kein Muster im folgenden Kommentar. Erstens ist die Anzahl von Leerzeichen vor dem Sternchen nicht konsistent. Zweitens beginnt die fünfte Zeile mit einem Tab, der mit Leerzeichen nicht übereinstimmt. Daher wird aller Text von Zeile zwei bis fünf als Teil des Kommentars verarbeitet.

    <!-- markdownlint-disable MD010 -->
    ```csharp
    /**
      * <summary>
      * text
     *  text2
        *  </summary>
    */
    ```
    <!-- markdownlint-enable MD010 -->

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [XML-Dokumentationskommentare](./index.md)
- [-doc (C#-Compileroptionen)](../../language-reference/compiler-options/doc-compiler-option.md)
