---
title: 'Vorgehensweise: Anzeigen von Befehlszeilenargumenten – C#-Programmierleitfaden'
description: Erfahren Sie, wie Sie Befehlszeilenargumente anzeigen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 717e27c23724e63c03a38b028ef99dc6530b4745
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195479"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="bb3f8-104">Vorgehensweise: Anzeigen von Befehlszeilenargumenten (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="bb3f8-104">How to display command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="bb3f8-105">Auf die Argumente, die für eine ausführbare Datei in der Befehlszeile bereitgestellt werden, kann über einen optionalen Parameter für `Main` zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="bb3f8-105">Arguments provided to an executable on the command line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="bb3f8-106">Die Argumente werden in Form eines Arrays von Zeichenfolgen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bb3f8-106">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="bb3f8-107">Jedes Element des Arrays enthält ein Argument.</span><span class="sxs-lookup"><span data-stu-id="bb3f8-107">Each element of the array contains one argument.</span></span> <span data-ttu-id="bb3f8-108">Leerzeichen zwischen Argumenten wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="bb3f8-108">White-space between arguments is removed.</span></span> <span data-ttu-id="bb3f8-109">Beachten Sie z.B. diese Befehlszeilenaufrufe einer fiktiven ausführbaren Datei:</span><span class="sxs-lookup"><span data-stu-id="bb3f8-109">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="bb3f8-110">Eingabe in der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="bb3f8-110">Input on command line</span></span>|<span data-ttu-id="bb3f8-111">An Main übergebenes Array von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="bb3f8-111">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="bb3f8-112">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="bb3f8-112">**executable.exe a b c**</span></span>|<span data-ttu-id="bb3f8-113">"a"</span><span class="sxs-lookup"><span data-stu-id="bb3f8-113">"a"</span></span><br /><br /> <span data-ttu-id="bb3f8-114">"b"</span><span class="sxs-lookup"><span data-stu-id="bb3f8-114">"b"</span></span><br /><br /> <span data-ttu-id="bb3f8-115">"c"</span><span class="sxs-lookup"><span data-stu-id="bb3f8-115">"c"</span></span>|  
|<span data-ttu-id="bb3f8-116">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="bb3f8-116">**executable.exe one two**</span></span>|<span data-ttu-id="bb3f8-117">"one"</span><span class="sxs-lookup"><span data-stu-id="bb3f8-117">"one"</span></span><br /><br /> <span data-ttu-id="bb3f8-118">"two"</span><span class="sxs-lookup"><span data-stu-id="bb3f8-118">"two"</span></span>|  
|<span data-ttu-id="bb3f8-119">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="bb3f8-119">**executable.exe "one two" three**</span></span>|<span data-ttu-id="bb3f8-120">"one two"</span><span class="sxs-lookup"><span data-stu-id="bb3f8-120">"one two"</span></span><br /><br /> <span data-ttu-id="bb3f8-121">"three"</span><span class="sxs-lookup"><span data-stu-id="bb3f8-121">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="bb3f8-122">Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.</span><span class="sxs-lookup"><span data-stu-id="bb3f8-122">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb3f8-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb3f8-123">Example</span></span>  

 <span data-ttu-id="bb3f8-124">Dieses Beispiel zeigt die Befehlszeilenargumente, die an eine Befehlszeilenanwendung übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="bb3f8-124">This example displays the command-line arguments passed to a command-line application.</span></span> <span data-ttu-id="bb3f8-125">Die Ausgabe wird für den ersten Eintrag in der obigen Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bb3f8-125">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="bb3f8-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb3f8-126">See also</span></span>

- [<span data-ttu-id="bb3f8-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bb3f8-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bb3f8-128">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="bb3f8-128">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="bb3f8-129">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="bb3f8-129">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="bb3f8-130">Main()-Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="bb3f8-130">Main() Return Values</span></span>](./main-return-values.md)
