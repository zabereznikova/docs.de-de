---
title: 'Vorgehensweise: Zugreifen auf Befehlszeilenargumente mithilfe von „foreach“ – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 79c798bb6ec16fc639d37defc40da5af770e5bba
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242431"
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="5bf66-102">Vorgehensweise: Zugreifen auf Befehlszeilenargumente mithilfe von „foreach“ (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="5bf66-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="5bf66-103">Ein weiteres Verfahren zum Durchlaufen von Arrays wird im nachfolgenden Beispiel veranschaulicht: die Verwendung der [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5bf66-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="5bf66-104">Die `foreach`-Anweisung kann verwendet werden, um ein Array, eine .NET Framework-Auflistungsklasse oder eine beliebige Klasse bzw. Struktur zu durchlaufen, die die <xref:System.Collections.IEnumerable>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="5bf66-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bf66-105">Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.</span><span class="sxs-lookup"><span data-stu-id="5bf66-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bf66-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5bf66-106">Example</span></span>  
 <span data-ttu-id="5bf66-107">In diesem Beispiel wird die Ausgabe der Befehlszeilenargumente mithilfe von `foreach` verdeutlicht.</span><span class="sxs-lookup"><span data-stu-id="5bf66-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5bf66-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bf66-108">See Also</span></span>

- <xref:System.Array>  
- <xref:System.Collections>  
- [<span data-ttu-id="5bf66-109">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="5bf66-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
- [<span data-ttu-id="5bf66-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5bf66-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5bf66-111">foreach, in</span><span class="sxs-lookup"><span data-stu-id="5bf66-111">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
- [<span data-ttu-id="5bf66-112">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="5bf66-112">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [<span data-ttu-id="5bf66-113">Vorgehensweise: Anzeigen von Befehlszeilenargumenten</span><span class="sxs-lookup"><span data-stu-id="5bf66-113">How to: Display Command Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
- [<span data-ttu-id="5bf66-114">Main()-Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="5bf66-114">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
