---
title: Trennzeichen für Dokumentationstags – C#-Programmierhandbuch
description: Erfahren Sie mehr über Trennzeichen für Dokumentationstags. Trennzeichen informieren den Compiler darüber, wo ein Dokumentationskommentar beginnt und endet.
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: 3191e32b0ff2dbde004abaab0b699cd61fcbb150
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381982"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="a7d4a-104">Trennzeichen für Dokumentationstags (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a7d4a-104">Delimiters for documentation tags (C# programming guide)</span></span>

<span data-ttu-id="a7d4a-105">Die Verwendung von XML-Dokumentkommentaren erfordert Trennzeichen, die dem Compiler angeben, wo ein Dokumentationskommentar beginnt und endet.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-105">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="a7d4a-106">Sie können die folgenden Arten von Trennzeichen mit den XML-Dokumentationstags verwenden:</span><span class="sxs-lookup"><span data-stu-id="a7d4a-106">You can use the following kinds of delimiters with the XML documentation tags:</span></span>

- `///`

  <span data-ttu-id="a7d4a-107">Einzeiliges Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="a7d4a-107">Single-line delimiter.</span></span> <span data-ttu-id="a7d4a-108">Dies ist die Form, die in den Dokumentationsbeispielen und von den C#-Projektvorlagen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-108">This is the form that is shown in documentation examples and used by the C# project templates.</span></span> <span data-ttu-id="a7d4a-109">Wenn ein Leerzeichen hinter einem Trennzeichen steht, ist dieses Zeichen nicht in der XML-Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-109">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a7d4a-110">Die integrierte Entwicklungsumgebung (IDE) von Visual Studio fügt die Tags `<summary>` und `</summary>` automatisch ein und verschiebt Ihren Cursor innerhalb dieser Tags, nachdem Sie das Trennzeichen `///` in den Code-Editor eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-110">The Visual Studio integrated development environment (IDE) automatically inserts the `<summary>` and `</summary>` tags and moves your cursor within these tags after you type the `///` delimiter in the code editor.</span></span> <span data-ttu-id="a7d4a-111">Sie können diese Funktion im [Dialogfeld „Optionen“](/visualstudio/ide/reference/options-text-editor-csharp-advanced) aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-111">You can turn this feature on or off in the [Options dialog box](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span></span>
  
- `/** */`

  <span data-ttu-id="a7d4a-112">Mehrzeilige Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-112">Multiline delimiters.</span></span>

  <span data-ttu-id="a7d4a-113">Es gibt einige Formatierungsregeln zu beachten, wenn Sie die `/** */`-Trennzeichen verwenden:</span><span class="sxs-lookup"><span data-stu-id="a7d4a-113">There are some formatting rules to follow when you use the `/** */` delimiters:</span></span>
  
  - <span data-ttu-id="a7d4a-114">In der Zeile mit dem `/**`-Trennzeichen, wenn der Rest der Zeile Leerraum ist, wird die Zeile für Kommentare nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-114">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="a7d4a-115">Wenn das erste Zeichen nach dem `/**`-Trennzeichen ein Leerzeichen ist, wird dieses Leerzeichen ignoriert und der Rest der Zeile verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-115">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="a7d4a-116">Andernfalls wird de gesamte Text der Zeile nach dem `/**`-Trennzeichen als Teil des Kommentars verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-116">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>

  - <span data-ttu-id="a7d4a-117">In der Zeile mit dem `*/`-Trennzeichen, wenn sie nur aus Leerzeichen bis zum `*/`-Trennzeichen besteht, wird diese Zeile ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-117">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="a7d4a-118">Andernfalls wird der Text der Zeile bis zum `*/`-Trennzeichen als Teil des Kommentars verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-118">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment.</span></span>
  
  - <span data-ttu-id="a7d4a-119">Für die Zeilen nach der, die mit dem `/**`-Trennzeichen beginnt, sucht der Compiler ein gemeinsames Muster am Anfang jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-119">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="a7d4a-120">Das Muster kann aus optionalen Leerzeichen und einem Sternchen bestehen (`*`), gefolgt von weiteren optionalen Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-120">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="a7d4a-121">Wenn der Compiler am Anfang jeder Zeile ein gemeinsames Muster findet, die nicht mit dem `/**`- oder `*/`-Trennzeichen beginnt, ignoriert er dieses Muster für jede Zeile.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-121">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>

  <span data-ttu-id="a7d4a-122">In den folgenden Beispielen werden diese Regeln veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-122">The following examples illustrate these rules.</span></span>

  - <span data-ttu-id="a7d4a-123">Der einzige Teil des folgenden Kommentars, der verarbeitet wird, ist die Zeile, die mit `<summary>` beginnt.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-123">The only part of the following comment that's processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="a7d4a-124">Die drei Tag-Formate ergeben identische Kommentare.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-124">The three tag formats produce the same comments.</span></span>

    ```csharp
    /** <summary>text</summary> */

    /**
    <summary>text</summary>
    */

    /**
     * <summary>text</summary>
    */
    ```

  - <span data-ttu-id="a7d4a-125">Der Compiler identifiziert ein gemeinsames Muster von „\*“ am Anfang der zweiten und dritten Zeile.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-125">The compiler identifies a common pattern of " \* " at the beginning of the second and third lines.</span></span> <span data-ttu-id="a7d4a-126">Das Muster ist nicht in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-126">The pattern is not included in the output.</span></span>

    ```csharp
    /**
     * <summary>
     * text </summary>*/
    ```

  - <span data-ttu-id="a7d4a-127">Der Compiler findet kein gemeinsames Muster im folgenden Kommentar, da das zweite Zeichen in der dritten Zeile kein Sternchen ist.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-127">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="a7d4a-128">Daher wird der gesamte Text in der zweiten und dritten Zeile als Teil des Kommentars verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-128">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>

    ```csharp
    /**
     * <summary>
       text </summary>
    */
    ```

  - <span data-ttu-id="a7d4a-129">Der Compiler findet aus zwei Gründen kein Muster im folgenden Kommentar.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-129">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="a7d4a-130">Erstens ist die Anzahl von Leerzeichen vor dem Sternchen nicht konsistent.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-130">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="a7d4a-131">Zweitens beginnt die fünfte Zeile mit einem Tab, der mit Leerzeichen nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-131">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="a7d4a-132">Daher wird aller Text von Zeile zwei bis fünf als Teil des Kommentars verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a7d4a-132">Therefore, all text from lines two through five is processed as part of the comment.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a7d4a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7d4a-133">See also</span></span>

- [<span data-ttu-id="a7d4a-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a7d4a-134">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="a7d4a-135">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="a7d4a-135">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="a7d4a-136">-doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a7d4a-136">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
