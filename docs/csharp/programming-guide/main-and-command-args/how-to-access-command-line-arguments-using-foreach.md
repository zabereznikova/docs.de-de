---
title: 'Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 15
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
ms.openlocfilehash: 766b5cd0879edec1dc409e07c4f62ee693fd615d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="c8920-102">Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c8920-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="c8920-103">Ein weiteres Verfahren zum Durchlaufen von Arrays wird im nachfolgenden Beispiel veranschaulicht: die Verwendung der [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c8920-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="c8920-104">Die `foreach`-Anweisung kann verwendet werden, um ein Array, eine .NET Framework-Auflistungsklasse oder eine beliebige Klasse bzw. Struktur zu durchlaufen, die die <xref:System.Collections.IEnumerable>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="c8920-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8920-105">Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.</span><span class="sxs-lookup"><span data-stu-id="c8920-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8920-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8920-106">Example</span></span>  
 <span data-ttu-id="c8920-107">In diesem Beispiel wird die Ausgabe der Befehlszeilenargumente mithilfe von `foreach` verdeutlicht.</span><span class="sxs-lookup"><span data-stu-id="c8920-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 <span data-ttu-id="c8920-108">[!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c8920-108">[!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]</span></span>  
  
 <span data-ttu-id="c8920-109">[!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c8920-109">[!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8920-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8920-110">See Also</span></span>  
 <span data-ttu-id="c8920-111"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="c8920-111"><xref:System.Array></span></span>   
 <span data-ttu-id="c8920-112"><xref:System.Collections></span><span class="sxs-lookup"><span data-stu-id="c8920-112"><xref:System.Collections></span></span>   
 <span data-ttu-id="c8920-113">[Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span><span class="sxs-lookup"><span data-stu-id="c8920-113">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span></span>  
 <span data-ttu-id="c8920-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c8920-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c8920-115">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="c8920-115">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 <span data-ttu-id="c8920-116">[Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="c8920-116">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="c8920-117">[Vorgehensweise: Anzeigen von Befehlszeilenargumenten](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="c8920-117">[How to: Display Command Line Arguments](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md) </span></span>  
 [<span data-ttu-id="c8920-118">Main()-Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="c8920-118">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

