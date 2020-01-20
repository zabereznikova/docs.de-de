---
title: 'Vorgehensweise: Anzeigen von Befehlszeilenargumenten (C#-Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 210dad71220572535a0325fac925b0453b0d4e03
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712025"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="d4635-102">Vorgehensweise: Anzeigen von Befehlszeilenargumenten (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="d4635-102">How to display command line arguments (C# Programming Guide)</span></span>
<span data-ttu-id="d4635-103">Auf die Argumente, die für eine ausführbare Datei in der Befehlszeile bereitgestellt wurden, können Sie über einen optionalen Parameter für `Main` zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d4635-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="d4635-104">Die Argumente werden in Form eines Arrays von Zeichenfolgen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d4635-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="d4635-105">Jedes Element des Arrays enthält ein Argument.</span><span class="sxs-lookup"><span data-stu-id="d4635-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="d4635-106">Leerzeichen zwischen Argumenten wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="d4635-106">White-space between arguments is removed.</span></span> <span data-ttu-id="d4635-107">Beachten Sie z.B. diese Befehlszeilenaufrufe einer fiktiven ausführbaren Datei:</span><span class="sxs-lookup"><span data-stu-id="d4635-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="d4635-108">Eingabe in der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="d4635-108">Input on Command-line</span></span>|<span data-ttu-id="d4635-109">An Main übergebenes Array von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="d4635-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="d4635-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="d4635-110">**executable.exe a b c**</span></span>|<span data-ttu-id="d4635-111">"a"</span><span class="sxs-lookup"><span data-stu-id="d4635-111">"a"</span></span><br /><br /> <span data-ttu-id="d4635-112">"b"</span><span class="sxs-lookup"><span data-stu-id="d4635-112">"b"</span></span><br /><br /> <span data-ttu-id="d4635-113">"c"</span><span class="sxs-lookup"><span data-stu-id="d4635-113">"c"</span></span>|  
|<span data-ttu-id="d4635-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="d4635-114">**executable.exe one two**</span></span>|<span data-ttu-id="d4635-115">"one"</span><span class="sxs-lookup"><span data-stu-id="d4635-115">"one"</span></span><br /><br /> <span data-ttu-id="d4635-116">"two"</span><span class="sxs-lookup"><span data-stu-id="d4635-116">"two"</span></span>|  
|<span data-ttu-id="d4635-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="d4635-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="d4635-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="d4635-118">"one two"</span></span><br /><br /> <span data-ttu-id="d4635-119">"three"</span><span class="sxs-lookup"><span data-stu-id="d4635-119">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d4635-120">Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.</span><span class="sxs-lookup"><span data-stu-id="d4635-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4635-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4635-121">Example</span></span>  
 <span data-ttu-id="d4635-122">In diesem Beispiel werden die Befehlszeilenargumente gezeigt, die an eine Befehlszeilenanwendung übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="d4635-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="d4635-123">Die Ausgabe wird für den ersten Eintrag in der obigen Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d4635-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="d4635-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4635-124">See also</span></span>

- [<span data-ttu-id="d4635-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d4635-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d4635-126">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="d4635-126">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="d4635-127">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="d4635-127">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="d4635-128">Main()-Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="d4635-128">Main() Return Values</span></span>](./main-return-values.md)
