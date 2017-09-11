---
title: 'Gewusst wie: Anzeigen von Befehlszeilenargumenten (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cf8a57cce252b3596f0a19c9df643427615467c6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="abd76-102">Gewusst wie: Anzeigen von Befehlszeilenargumenten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="abd76-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="abd76-103">Auf die Argumente, die für eine ausführbare Datei in der Befehlszeile bereitgestellt wurden, können Sie über einen optionalen Parameter für `Main` zugreifen.</span><span class="sxs-lookup"><span data-stu-id="abd76-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="abd76-104">Die Argumente werden in Form eines Arrays von Zeichenfolgen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="abd76-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="abd76-105">Jedes Element des Arrays enthält ein Argument.</span><span class="sxs-lookup"><span data-stu-id="abd76-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="abd76-106">Leerzeichen zwischen Argumenten wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="abd76-106">White-space between arguments is removed.</span></span> <span data-ttu-id="abd76-107">Beachten Sie z.B. diese Befehlszeilenaufrufe einer fiktiven ausführbaren Datei:</span><span class="sxs-lookup"><span data-stu-id="abd76-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="abd76-108">Eingabe in der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="abd76-108">Input on Command-line</span></span>|<span data-ttu-id="abd76-109">An Main übergebenes Array von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="abd76-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="abd76-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="abd76-110">**executable.exe a b c**</span></span>|<span data-ttu-id="abd76-111">"a"</span><span class="sxs-lookup"><span data-stu-id="abd76-111">"a"</span></span><br /><br /> <span data-ttu-id="abd76-112">"b"</span><span class="sxs-lookup"><span data-stu-id="abd76-112">"b"</span></span><br /><br /> <span data-ttu-id="abd76-113">"c"</span><span class="sxs-lookup"><span data-stu-id="abd76-113">"c"</span></span>|  
|<span data-ttu-id="abd76-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="abd76-114">**executable.exe one two**</span></span>|<span data-ttu-id="abd76-115">"one"</span><span class="sxs-lookup"><span data-stu-id="abd76-115">"one"</span></span><br /><br /> <span data-ttu-id="abd76-116">"two"</span><span class="sxs-lookup"><span data-stu-id="abd76-116">"two"</span></span>|  
|<span data-ttu-id="abd76-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="abd76-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="abd76-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="abd76-118">"one two"</span></span><br /><br /> <span data-ttu-id="abd76-119">"three"</span><span class="sxs-lookup"><span data-stu-id="abd76-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="abd76-120">Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.</span><span class="sxs-lookup"><span data-stu-id="abd76-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="abd76-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="abd76-121">Example</span></span>  
 <span data-ttu-id="abd76-122">In diesem Beispiel werden die Befehlszeilenargumente gezeigt, die an eine Befehlszeilenanwendung übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="abd76-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="abd76-123">Die Ausgabe wird für den ersten Eintrag in der obigen Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="abd76-123">The output shown is for the first entry in the table above.</span></span>  
  
 <span data-ttu-id="abd76-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="abd76-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd76-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abd76-125">See Also</span></span>  
 <span data-ttu-id="abd76-126">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="abd76-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="abd76-127">[Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span><span class="sxs-lookup"><span data-stu-id="abd76-127">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span></span>  
 <span data-ttu-id="abd76-128">[Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="abd76-128">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="abd76-129">[Vorgehensweise: Zugreifen auf Befehlszeilenargumente mithilfe von foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span><span class="sxs-lookup"><span data-stu-id="abd76-129">[How to: Access Command-Line Arguments Using foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span></span>  
 [<span data-ttu-id="abd76-130">Main()-Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="abd76-130">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

