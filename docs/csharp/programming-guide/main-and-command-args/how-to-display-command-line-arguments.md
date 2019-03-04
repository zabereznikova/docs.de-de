---
title: 'Vorgehensweise: Anzeigen von Befehlszeilenargumenten – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: b7018afa1272f4ae092863de6b7f9ef783001244
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965591"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="dd964-102">Vorgehensweise: Anzeigen von Befehlszeilenargumenten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="dd964-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="dd964-103">Auf die Argumente, die für eine ausführbare Datei in der Befehlszeile bereitgestellt wurden, können Sie über einen optionalen Parameter für `Main` zugreifen.</span><span class="sxs-lookup"><span data-stu-id="dd964-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="dd964-104">Die Argumente werden in Form eines Arrays von Zeichenfolgen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dd964-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="dd964-105">Jedes Element des Arrays enthält ein Argument.</span><span class="sxs-lookup"><span data-stu-id="dd964-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="dd964-106">Leerzeichen zwischen Argumenten wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="dd964-106">White-space between arguments is removed.</span></span> <span data-ttu-id="dd964-107">Beachten Sie z.B. diese Befehlszeilenaufrufe einer fiktiven ausführbaren Datei:</span><span class="sxs-lookup"><span data-stu-id="dd964-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="dd964-108">Eingabe in der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="dd964-108">Input on Command-line</span></span>|<span data-ttu-id="dd964-109">An Main übergebenes Array von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="dd964-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="dd964-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="dd964-110">**executable.exe a b c**</span></span>|<span data-ttu-id="dd964-111">"a"</span><span class="sxs-lookup"><span data-stu-id="dd964-111">"a"</span></span><br /><br /> <span data-ttu-id="dd964-112">"b"</span><span class="sxs-lookup"><span data-stu-id="dd964-112">"b"</span></span><br /><br /> <span data-ttu-id="dd964-113">"c"</span><span class="sxs-lookup"><span data-stu-id="dd964-113">"c"</span></span>|  
|<span data-ttu-id="dd964-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="dd964-114">**executable.exe one two**</span></span>|<span data-ttu-id="dd964-115">"one"</span><span class="sxs-lookup"><span data-stu-id="dd964-115">"one"</span></span><br /><br /> <span data-ttu-id="dd964-116">"two"</span><span class="sxs-lookup"><span data-stu-id="dd964-116">"two"</span></span>|  
|<span data-ttu-id="dd964-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="dd964-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="dd964-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="dd964-118">"one two"</span></span><br /><br /> <span data-ttu-id="dd964-119">"three"</span><span class="sxs-lookup"><span data-stu-id="dd964-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="dd964-120">Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.</span><span class="sxs-lookup"><span data-stu-id="dd964-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd964-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd964-121">Example</span></span>  
 <span data-ttu-id="dd964-122">In diesem Beispiel werden die Befehlszeilenargumente gezeigt, die an eine Befehlszeilenanwendung übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="dd964-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="dd964-123">Die Ausgabe wird für den ersten Eintrag in der obigen Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dd964-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="dd964-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd964-124">See also</span></span>

- [<span data-ttu-id="dd964-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dd964-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dd964-126">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="dd964-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="dd964-127">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="dd964-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="dd964-128">Vorgehensweise: Zugreifen auf Befehlszeilenargumente mithilfe von „foreach“</span><span class="sxs-lookup"><span data-stu-id="dd964-128">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
- [<span data-ttu-id="dd964-129">Main()-Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="dd964-129">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
