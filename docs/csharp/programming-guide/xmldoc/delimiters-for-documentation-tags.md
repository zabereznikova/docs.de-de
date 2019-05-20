---
title: Trennzeichen für Dokumentationstags – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: d08dd0c68a11ddf73c19a1e09bc8c59937708553
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634766"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="d159a-102">Trennzeichen für Dokumentationstags (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d159a-102">Delimiters for Documentation Tags (C# Programming Guide)</span></span>
<span data-ttu-id="d159a-103">Die Verwendung von XML-Dokumentkommentaren erfordert Trennzeichen, die dem Compiler angeben, wo ein Dokumentationskommentar beginnt und endet.</span><span class="sxs-lookup"><span data-stu-id="d159a-103">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="d159a-104">Sie können die folgenden Arten von Trennzeichen mit den XML-Dokumentationstags verwenden:</span><span class="sxs-lookup"><span data-stu-id="d159a-104">You can use the following kinds of delimiters with the XML documentation tags:</span></span>  
  
 `///`  
 <span data-ttu-id="d159a-105">Einzeiliges Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d159a-105">Single-line delimiter.</span></span> <span data-ttu-id="d159a-106">Dies ist die Form, die in den Dokumentationsbeispielen dargestellt und von den Visual C#-Projektvorlagen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d159a-106">This is the form that is shown in documentation examples and used by the Visual C# project templates.</span></span> <span data-ttu-id="d159a-107">Wenn ein Leerzeichen hinter einem Trennzeichen steht, ist dieses Zeichen nicht in der XML-Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="d159a-107">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d159a-108">Visual Studio-IDE bietet eine Funktion namens Smart Comment Editing, die automatisch die Tags \<summary> und \</summary > einfügt und Ihren Cursor innerhalb dieser Tags verschiebt, nachdem Sie das `///`-Trennzeichen im Code-Editor eingeben.</span><span class="sxs-lookup"><span data-stu-id="d159a-108">The Visual Studio IDE has a feature called Smart Comment Editing that automatically inserts the \<summary> and \</summary> tags and moves your cursor within these tags after you type the `///` delimiter in the Code Editor.</span></span> <span data-ttu-id="d159a-109">Sie können diese Funktion im [Dialogfeld „Optionen“](/visualstudio/ide/reference/options-text-editor-csharp-advanced) aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d159a-109">You can turn this feature on or off in the [Options dialog box](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span></span>  
  
 `/** */`  
 <span data-ttu-id="d159a-110">Mehrzeilige Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="d159a-110">Multiline delimiters.</span></span>  
  
 <span data-ttu-id="d159a-111">Es gibt einige Formatierungsregeln zu beachten, wenn Sie die `/** */`-Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d159a-111">There are some formatting rules to follow when you use the `/** */` delimiters.</span></span>  
  
- <span data-ttu-id="d159a-112">In der Zeile mit dem `/**`-Trennzeichen, wenn der Rest der Zeile Leerraum ist, wird die Zeile für Kommentare nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d159a-112">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="d159a-113">Wenn das erste Zeichen nach dem `/**`-Trennzeichen ein Leerzeichen ist, wird dieses Leerzeichen ignoriert und der Rest der Zeile verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d159a-113">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="d159a-114">Andernfalls wird de gesamte Text der Zeile nach dem `/**`-Trennzeichen als Teil des Kommentars verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d159a-114">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>  
  
- <span data-ttu-id="d159a-115">In der Zeile mit dem `*/`-Trennzeichen, wenn sie nur aus Leerzeichen bis zum `*/`-Trennzeichen besteht, wird diese Zeile ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d159a-115">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="d159a-116">Andernfalls wird der Text in der Zeile bis zum `*/`-Trennzeichen als Teil des Kommentars verarbeitet, gemäß den Mustervergleichsregeln, die im folgenden Aufzählungszeichen beschriebenen werden.</span><span class="sxs-lookup"><span data-stu-id="d159a-116">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment, subject to the pattern-matching rules described in the following bullet.</span></span>  
  
- <span data-ttu-id="d159a-117">Für die Zeilen nach der, die mit dem `/**`-Trennzeichen beginnt, sucht der Compiler ein gemeinsames Muster am Anfang jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="d159a-117">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="d159a-118">Das Muster kann aus optionalen Leerzeichen und einem Sternchen bestehen (`*`), gefolgt von weiteren optionalen Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="d159a-118">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="d159a-119">Wenn der Compiler am Anfang jeder Zeile ein gemeinsames Muster findet, die nicht mit dem `/**`- oder `*/`-Trennzeichen beginnt, ignoriert er dieses Muster für jede Zeile.</span><span class="sxs-lookup"><span data-stu-id="d159a-119">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>  
  
 <span data-ttu-id="d159a-120">In den folgenden Beispielen werden diese Regeln veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d159a-120">The following examples illustrate these rules.</span></span>  
  
- <span data-ttu-id="d159a-121">Der einzige Teil des folgenden Kommentars, der verarbeitet wird, ist die Zeile, die mit `<summary>` beginnt.</span><span class="sxs-lookup"><span data-stu-id="d159a-121">The only part of the following comment that will be processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="d159a-122">Die drei Tag-Formate ergeben identische Kommentare.</span><span class="sxs-lookup"><span data-stu-id="d159a-122">The three tag formats produce the same comments.</span></span>  
  
    ```csharp  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
    ```  
  
- <span data-ttu-id="d159a-123">Der Compiler identifiziert ein gemeinsames Muster von „\*“ am Anfang der zweiten und dritten Zeile.</span><span class="sxs-lookup"><span data-stu-id="d159a-123">The compiler identifies a common pattern of " \* " at the beginning of the second and third lines.</span></span> <span data-ttu-id="d159a-124">Das Muster ist nicht in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="d159a-124">The pattern is not included in the output.</span></span>  
  
    ```csharp  
    /**   
     * <summary>   
     * text </summary>*/   
    ```  
  
- <span data-ttu-id="d159a-125">Der Compiler findet kein gemeinsames Muster im folgenden Kommentar, da das zweite Zeichen in der dritten Zeile kein Sternchen ist.</span><span class="sxs-lookup"><span data-stu-id="d159a-125">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="d159a-126">Daher wird der gesamte Text in der zweiten und dritten Zeile als Teil des Kommentars verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d159a-126">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>  
  
    ```csharp  
    /**   
     * <summary>   
       text </summary>  
    */   
    ```  
  
- <span data-ttu-id="d159a-127">Der Compiler findet aus zwei Gründen kein Muster im folgenden Kommentar.</span><span class="sxs-lookup"><span data-stu-id="d159a-127">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="d159a-128">Erstens ist die Anzahl von Leerzeichen vor dem Sternchen nicht konsistent.</span><span class="sxs-lookup"><span data-stu-id="d159a-128">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="d159a-129">Zweitens beginnt die fünfte Zeile mit einem Tab, der mit Leerzeichen nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="d159a-129">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="d159a-130">Daher wird aller Text von Zeile zwei bis fünf als Teil des Kommentars verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d159a-130">Therefore, all text from lines two through five is processed as part of the comment.</span></span>  
  
    ```csharp  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d159a-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d159a-131">See also</span></span>

- [<span data-ttu-id="d159a-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d159a-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d159a-133">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="d159a-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/index.md)
- [<span data-ttu-id="d159a-134">/doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="d159a-134">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="d159a-135">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="d159a-135">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/index.md)
